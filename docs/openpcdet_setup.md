# OpenPCDet 설치 가이드

## 환경
- Base: CHEETAH torch2.3.0-py3.11-cuda12.1 컨테이너
- venv: ~/Dataset/envs/wemeet (PyTorch 2.3.0+cu121)
- numpy 2.4.4 (최신 버전, 충돌 없이 정상 작동 확인됨)

## 설치 순서
```bash
pip install spconv-cu121
cd ~/wemeet
git clone https://github.com/open-mmlab/OpenPCDet.git external/OpenPCDet
cd external/OpenPCDet
pip install -r requirements.txt
python setup.py develop
```

## 검증 방법
```python
import pcdet
import spconv.pytorch as spconv
# sparse conv 연산 테스트로 CUDA 빌드 확인
```

## 확인된 사항
- MIG 10GB 슬라이스에서 spconv sparse 연산 정상 작동 확인 (2026-07-06)
- PointPillars config: tools/cfgs/kitti_models/pointpillar.yaml 기준으로 커스터마이징 예정

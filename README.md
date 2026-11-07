# HD2 Skin Mod Windows 다운로드

최신 수정본: **0.12.3 — Blender 4.0의 python312.dll 충돌 수정**

[HD2SkinMod-0.12.3-Windows.zip 다운로드](https://github.com/aegirgymir/HD2-skin_mod/raw/refs/heads/downloads/HD2SkinMod-0.12.3-Windows.zip)

이전 EXE를 종료하고 ZIP을 새 폴더에 풀어 실행합니다. 기존 프로젝트를 선택하고 **설치된 Blender 선택**에서 기존 **Blender 4.0의 blender.exe**를 지정합니다. **전체 변환 검사** 후 **설정으로 실행·이어서 진행**을 누릅니다.

Blender 4.0과 SDK 애드온은 그대로 유지합니다. 별도 Python/pip 설치, DLL 삭제/교체, 프로젝트 재생성은 필요 없습니다. EXE에 Python·PMX/SDK 도구·DDS 변환기가 포함되며 Blender와 실제 모델/게임 자료는 포함되지 않습니다.

## 수정 내용

`blender_workspace_failed: Module use of python312.dll conflicts with this version of Python.`는 EXE의 Python3.12용 unicodedata.pyd를 Blender4.0의 Python3.10이 먼저 읽은 문제였습니다. Blender에 전달하는 순수 Python 소스와 검사 fixture를 EXE DLL/PYD 폴더와 분리했습니다. 모든 Blender 실행 단계의 Python/PyInstaller 환경·DLL/PATH·현재 폴더도 분리합니다.

4.0의 기본 형상/FK 가져오기 경로는 0.12.2에서 유지됩니다. 모프·IK·append-bone 제약·SDEF 전용 드라이버·물리는 가져오지 않습니다. SDEF 두 본 계수는 선형 웨이트로 전달되므로 검토가 필요합니다. 머리카락 head1.0 조정은 후속 명시적 웨이트 설정 단계에서 적용합니다. 실제 모델 작업은 **설정으로 실행·이어서 진행**으로 실행합니다. 검사 버튼은 포함된 합성 자료로 동작하며 게임 폴더를 바꾸지 않습니다.

## 검증 범위

- 이전 0.12.2 EXE 내용으로 WindowsPython3.10 under Wine에서 같은 오류 문구를 재현했습니다.
- 새 EXE의 원문51개와 source 일치·작업 소스 폴더에 DLL/PYD 부재를 확인했습니다.
- 새 EXE 추출물을 실제 WindowsPython3.12→3.10에서 실행해 3.10의 자체 unicodedata/_ctypes 사용·python312.dll 미로드·작업 모듈12개/PMX 파서 성공을 확인했습니다. 이 호출의 frozen marker와 오염된 DLL/env/cwd는 개발 launcher에서 모사했습니다.
- 실제 Blender4.3.2에서 4.0용 가져오기 선택 경로를 사용한 회귀231개·skipped0, 새 EXE 기본 자체 검사6범주·Unicode UI 두번 실행/프로젝트 재개를 Wine에서 통과했습니다.

**실제 Blender4.0 전체 실행, 실제 Windows 운영체제/Windows Blender 전체 변환·사용자 자산·인게임은 미검증입니다.** 공식 Blender 다운로드는 클라우드 정책으로 차단되어 있습니다. 합성 검사 성공은 게임 모드 완성을 뜻하지 않습니다.

`Blender 공식 버전 준비`는 4.3.2 다운로드 기능입니다. 4.0을 유지할 때는 `설치된 Blender 선택`을 사용하세요.

[SHA256.txt](SHA256.txt)로 ZIP 해시를 확인할 수 있습니다. 이전 파일도 보존합니다: [0.12.2](HD2SkinMod-0.12.2-Windows.zip), [0.12.1](HD2SkinMod-0.12.1-Windows.zip), [0.12.0](HD2SkinMod-0.12.0-Windows.zip).

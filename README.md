# HD2 Skin Mod Windows 테스트 빌드

최신 수정본: **0.12.1**

[Windows ZIP 다운로드](https://github.com/aegirgymir/HD2-skin_mod/raw/refs/heads/downloads/HD2SkinMod-0.12.1-Windows.zip)

ZIP 압축을 풀고 `HD2SkinMod-0.12.1-windows-x64.exe`를 실행하세요.

## Blender 4.0 / tomllib 오류 해결

Blender 4.0의 내장 Python 3.10에는 `tomllib`가 없습니다. **Blender 4.3.2를 준비한 뒤 ‘설치된 Blender 선택’으로 해당 blender.exe를 지정하세요.**
현재 선택한 프로젝트의 실행 경로에도 반영됩니다. PC의 일반 Python을 바꾸거나 pip로 설치하는 방식으로 Blender 내부 Python은 바뀌지 않습니다.

수정본은 호환성 사전 검사와 버전 안내, 기존 프로젝트의 Blender 경로 변경을 추가했습니다. Blender 4.0을 지원하는 버전은 아닙니다.
Python·MMD·SDK·Windows DDS 변환기는 포함되어 있으며 Blender는 설치본 선택 또는 공식 다운로드로 별도 준비해야 합니다.

기본 검사와 Wine 실행·프로젝트 재시작을 확인했습니다. 실제 Windows 운영체제/Windows Blender 전체 변환/게임 플레이는 아직 검증하지 않았습니다.
이전 0.12.0 ZIP은 기존 링크 보존을 위해 남겨 두었습니다. 파일 해시는 SHA256.txt에서 확인할 수 있습니다.

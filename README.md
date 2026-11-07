# HD2 Skin Mod Windows 다운로드

최신 수정본: **0.12.2 — Blender 4.0 유지용 호환 경로**

[HD2SkinMod-0.12.2-Windows.zip 다운로드](https://github.com/aegirgymir/HD2-skin_mod/raw/refs/heads/downloads/HD2SkinMod-0.12.2-Windows.zip)

ZIP을 풀고 EXE를 실행합니다. Python은 내장되어 있으며 Blender와 실제 모델/게임 자료는 포함하지 않습니다.

## Blender 4.0에서 tomllib 오류가 발생했다면

1. 기존 Blender 4.0과 HD2 SDK 애드온을 그대로 둡니다.
2. 새 0.12.2 EXE에서 기존 프로젝트를 선택합니다.
3. **설치된 Blender 선택**에서 기존 4.0의 `blender.exe`를 지정합니다.
4. **전체 변환 검사**로 이 PC의 Blender 연결을 확인한 뒤, **설정으로 실행·이어서 진행**을 누릅니다.

4.0 경로는 최신 MMD 애드온을 등록하지 않고 SHA 고정 독립 PMX 파서로 기본 형상·UV·재질/텍스처·원래 본 계수·FK 뼈대를 만듭니다. TOML 모듈이나 별도 pip 설치가 필요 없습니다. Python 3.10의 file_digest 부재와 Blender 4.0의 노멀/Alpha Clip API를 처리했습니다. Blender 4.2 이상은 기존 MMD 애드온 경로를 유지합니다. 사용자의 애드온·Blender 환경·입력 파일을 변경하지 않습니다.

이 경로는 모프·IK·append-bone 제약·SDEF 전용 드라이버·물리를 가져오지 않습니다. SDEF의 두 본 계수는 선형 웨이트로 전달되므로 검토가 필요합니다. 머리카락 head 1.0 조정은 후속 명시적 웨이트 설정 단계에 적용합니다.

검증: 실제 Windows Python 3.10 under Wine에서 tomllib/file_digest 없이 파서·SDK AST/archive API·Windows cp310 LZ4/DSAR를 확인했습니다. 실제 Blender 4.3.2에서 4.0용 가져오기 경로와 후속 변환/패치·배포 226개 회귀 검사를 통과했습니다. 새 Windows EXE 자체 검사 6개와 실제 UI 두 번 실행/프로젝트 재개도 Wine에서 통과했습니다. 기존 최신 MMD 가져오기 경로도 6개 검사를 통과했습니다.

**실제 Blender 4.0 바이너리 실행은 클라우드 다운로드 차단으로 아직 검증하지 못했습니다. 실제 Windows 운영체제/Windows Blender 전체 변환·사용자 자산·인게임도 미검증입니다.** 합성 검사 성공이 게임 모드 완성이나 모든 모델의 자동 변환을 뜻하지 않습니다.

`Blender 공식 버전 준비`는 4.3.2 다운로드 기능입니다. 4.0을 유지할 때는 `설치된 Blender 선택`을 사용하세요. 이전 0.12.1의 업그레이드 안내는 4.0 유지 요구에 맞지 않아 이번 버전에서 대체했습니다.

검증 해시는 [SHA256.txt](SHA256.txt)에 있습니다. Windows PowerShell의 `Get-FileHash .\HD2SkinMod-0.12.2-Windows.zip -Algorithm SHA256`으로 비교할 수 있습니다.

이전 파일은 보존합니다: [0.12.1](HD2SkinMod-0.12.1-Windows.zip), [0.12.0](HD2SkinMod-0.12.0-Windows.zip).

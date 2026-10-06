Shadowrun: Dragonfall - Director's Cut 한국어 패치
배포일: 2026-10-06

이 패치는 Windows Steam판 Shadowrun: Dragonfall - Director's Cut의 게임 내 텍스트를 한국어로 표시합니다. 게임 실행 파일과 수정 대상 원본 파일의 해시가 패치에서 지정한 버전과 일치할 때만 설치됩니다. 이미 다른 패치로 바뀐 파일에는 설치하지 않습니다.

설치 방법
1. 게임과 Steam의 다운로드/업데이트를 종료합니다.
2. ZIP을 모두 압축 해제합니다. 파일만 따로 옮기지 말고 폴더 구조를 유지합니다.
3. 압축을 푼 Shadowrun_Dragonfall_KR 폴더에서 PowerShell을 열고 다음 명령의 두 경로를 자신의 환경에 맞게 바꿉니다. 백업 경로는 아직 존재하지 않는 폴더이며 Dragonfall_Data 밖에 있어야 합니다.

$GameData = "게임 설치 폴더\Dragonfall_Data"
$Backup = "새 원본 백업 폴더"
powershell.exe -NoProfile -ExecutionPolicy Bypass -File ".\patch_files.ps1" -Action Install -Target $GameData -Backup $Backup

백업 없이 바로 설치하려면 위의 $Backup 줄과 설치 명령 대신 아래 명령을 사용합니다. 이 방식은 원본 파일을 보관하지 않으므로 복원하려면 Steam의 게임 파일 무결성 검사를 이용해야 합니다.

powershell.exe -NoProfile -ExecutionPolicy Bypass -File ".\patch_files.ps1" -Action Install -Target $GameData -NoBackup

4. 게임 설정의 언어 목록에서 한국어를 선택합니다.

설치 확인
powershell.exe -NoProfile -ExecutionPolicy Bypass -File ".\patch_files.ps1" -Action Verify -Target $GameData

원본으로 복원
게임을 종료하고, 설치 때 만든 백업 폴더를 지정합니다.
powershell.exe -NoProfile -ExecutionPolicy Bypass -File ".\patch_files.ps1" -Action Restore -Target $GameData -Backup $Backup

백업 설치에는 원본 파일 백업과 압축 해제에 여러 GB의 여유 공간이 필요합니다. 백업 없는 설치도 적용 중 임시 파일을 위한 여유 공간이 필요합니다. 설치 스크립트가 버전 또는 파일 해시 불일치를 알리면 강제로 덮어쓰지 마세요. 전체 캠페인의 모든 대화 분기를 실제 플레이로 검수하지는 않았습니다.

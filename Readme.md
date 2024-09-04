API 호출 예시 및 목록:

클라이언트 측 Socket.IO 사용 예시:
const socket = io('http://localhost:4000');

1. 초기화:
   socket.emit('initialize', { 
     tempNickname: 'Player1', 
     tempJobPosition: 'Developer', 
     selectedCharacterGlbNameIndex: 0 
   });

2. 이동:
   socket.emit('move', [10, 0, 5]);

3. 채팅 메시지 전송:
   socket.emit('newText', 'Hello, everyone!');

4. 개인 룸 변경:
   socket.emit('myRoomChange', { objects: [// 룸 객체 배열 //] });

   API 목록:
   - 'connection': 새 클라이언트 연결 (서버에서 자동 감지)
   - 'initialize': 플레이어 초기화
   - 'move': 플레이어 이동
   - 'newText': 새 채팅 메시지 전송
   - 'myRoomChange': 개인 룸 정보 업데이트
   - 'disconnecting': 연결 종료 직전 (서버에서 자동 감지)
   - 'disconnect': 연결 종료 (서버에서 자동 감지)
   
   서버에서 클라이언트로 보내는 이벤트:
   - 'players': 전체 플레이어 목록 업데이트
   - 'initialize': 초기화된 플레이어 정보 (개별 클라이언트에게)
   - 'enter': 새 플레이어 입장 알림
   - 'newText': 새 채팅 메시지 브로드캐스트
   - 'exit': 플레이어 퇴장 알림
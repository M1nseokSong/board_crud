# board_crud

# <요구 사항>
사용자는 이메일 주소, 비밀번호, 비밀번호 확인, 닉네임, 핸드폰번호, 주소, 상세주소를 입력해서 회원가입 진행한다.
회원가입이 성공적으로 이루어지면 로그인을 진행.
로그인 이메일과 패스워드로 로그인을 진행한다.

로그인에 성공하면 메인화면으로 이동한다.
메인화면에는 주간 Top3 게시글이 보인다.
주간 Top3의 경우 좋아요 순으로 정렬한다.

최신 게시물이 리스트 형식으로 출력된다.
한페이지에 5개씩 게시물이 보인다.
페이징 처리가 되며 최대 10 페이지까지 보이고 이전 섹션과 이후 섹션으로 이동하는 방향 버튼이 있다.3

인기 검색어가 우측에 존재하도록 한다.

상단에는 네비게이션 바가 있는데 네비게이션 바에서 검색을 할 수 있다.
또한 네비게이션 바에서 마이페이지로 이동할 수 있다.

마이페이지로 이동해서 프로필 사진 수정, 닉네임 수정, 마이페이지에서 게시물을 등록할 수 있다.
게시물 등록 시에는 제목, 내용, 사진, 동영상, 파일을 올릴 수 있다.

게시물 리스트에서 게시물을 선택하면 해당 게시물의 제목, 작성자, 작성자 프로필 사진, 작성일, 내용, 사진, 동영상, 파일 출력해준다.

만약 본인 게시물이라면 게시물을 수정할 수 있다.
게시물 수정은 제목, 내용, 사진, 동영상, 파일을 수정할 수 있다.
또한 본인 게시물이면 삭제도 가능하다.

본인 게시물이 아니면 좋아요를 할 수 있다.
게시물에 좋아요를 누른 유저의 프로필 사진과 닉네임이 모두 출력된다.

모든 게시물에 댓글을 작성 할 수 있다.
댓글은 내용만 작성한다.
댓글은 작성자, 작성자 프로필 사진, 작성일, 내용이 출력된다.
댓글은 한번에 3개만 출력되고 페이징이 최대 10페이지 까지 된다.
이전 섹션, 다음 섹션 버튼이 존재한다.

댓글 수와 좋아요 수가 게시물 상세에서 표시가 된다.

# <데이터베이스 테이블 설계>
User(user_email[PK], user_password, user_nickname, user_phone_number, user_address, user_profile)

Board(board_number[PK], board_title, board_content, board_image, board_video, board_file,
board_wirter, board_writer_profile, board_wirte_date,
board_like_count, board_like_profile, board_like_nickname,
board_comment_writer, board_comment_profile, board_comment_write_date, board_comment, board_comment_count)

PopularSearch(popular_term, popular_search, count)

User - Board 관계
1. User가 Board를 작성한다.
2. User가 Board에 좋아요를 누른다.
3. User가 Board에 댓글을 단다.


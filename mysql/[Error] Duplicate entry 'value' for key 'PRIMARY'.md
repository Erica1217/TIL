# Duplicate entry 'value' for key 'PRIMARY'

번역하면 
>'PRIMARY'키에 대한 'value'항목이 중복되었습니다.

이다.

PRIMARY key는 중복될 수 없는데, update문으로 변경하다보니 중복되는 값이 생겨서 나타나는 오류다.

# 해결
update문에 ignore을 사용해서 해결하였다.
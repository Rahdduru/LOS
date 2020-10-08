#LOS
=========
LORD OF SQL INJECTION 풀이
---------
gremlin
  if($result['id']) solve("gremlin"); 이 문장에 집중.
  만약, id의 값이 있으며녀 gremlin을 풀 수 있다.
  
  다만, 
  $query = "select id from prob_gremlin where id='{$_GET[id]}' and pw='{$_GET[pw]}'";
  위 쿼리문에 따르면 id와 pw값 모두 GET을 받아야 한다.
  
  id와 pw가 and로 묶여있기 때문에 id에 넣어준 값에 대한 pw가 참이 되게 해야한다.

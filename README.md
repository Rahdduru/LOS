#LOS
=========
LORD OF SQL INJECTION 풀이
---------
### #gremlin#

if($result['id']) solve("gremlin"); 이 문장에 집중.<br>
만약, id의 값이 있으며녀 gremlin을 풀 수 있다. <br><br>

다만,<br>
$query = "select id from prob_gremlin where id='{$_GET[id]}' and pw='{$_GET[pw]}'";<br>
위 쿼리문에 따르면 id와 pw값 모두 GET을 받아야 한다.<br>
id와 pw가 and로 묶여있기 때문에 id에 넣어준 값에 대한 pw가 참이 되게 해야한다. <br><br>

참이 되게하는 가장 기본적인 문장이 있다. <b>'pw=1' or '1=1'</b><br>
이 문장을 사용해 pw의 값이 참이되게 해준다.<br><br>

?id='admin'&&pw=1 or 1=1 <br><br>

조금 더 간단한 방법을 이용하자면 id의 값을 받은 뒤 pw가 있는 곳을 주석처리해버리면 된다.<br><br>

?id-'admin' # pw=''

### #cobolt#

if($result['id'] == 'admin') solve("cobolt");<br>
이 문장을 보면, id값이 admin일 때 cobolt를 풀 수 있다고 나와있다.<br><br>

$query = "select id from prob_cobolt where id='{$_GET[id]}' and pw=md5('{$_GET[pw]}')";<br>
위 커리문에 따르면, id의 값과 pw의 값을 모두 받을 수 있다.<br>
pw에 대한 조건이 주어지지 않았음으로, pw는 gremlin과 같은 방법으로 참을 만들어준다.<br>
다만, pw에는 md5('')를 무효화 시켜주기 위해 <br>
  
?id='admin'&&pw='1' or '1=1'<br><br>

또는 gremlin과 같이 pw를 주석처리해준다.<br><br>

?id=

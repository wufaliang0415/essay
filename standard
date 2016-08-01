##编码规范##
1. 类名和文件必须一致，一个文件的代码不能超过1000行，一个函数的代码不能超过100行，一个函数的参数不能超过6个。
2. 类需要注释，public函数放在文件的最上面，private函数放在文件的最下方。
3. private函数和变量必须以下划线开头。
4. 函数名、变量名、类型、文件名必须采用峰驼式，类名、文件名必须首字母大写，函数名和变量名必须首字母小写。
5. 对于变量名的要求，必须将变量类型写在名字前面，作为前缀。
	```
	$objUserMode = new UserMode();
	$strUserName = 'luce';
	$arrParams = array('name' => 'name1');
	$boolRes = true;
	$intUserId = 4;
	$jsonData = "['name':'name1']";
	```
6. 调用的函数或接口时，如果有返回值，必须对返回值进行处理。
7. 一个函数如果有返回值，必须在最后统一返回，禁止多个返回埋点。
8. 禁止使用绝对路径，可以考虑使用：_LIB_ROOT、_PATH_ROOT连接的方式。
9. 代码中禁止出现针对调整PHP错误级别的函数：error_reporting及时区的控制。
10. 代码中禁止出现明文的域名、IP、或端口， 全部走配置流来处理。
11. 关于空格的使用，见例子：
	```php
	class UserMode() {
	
	    private $_objAssetMode = null;
	
	    public function contruct() {
	        $_objAssetMode = core::Singleton("library.moduel.UserMode");
	    }
	
	    public function getUserInfo($intUserId, $strEmail) {
	        $arrUserInfo = $this->_objUserDb->select();
	    }
	
	    public function getUserList($arrWhere, $arrFiled = array()) {
	        $arrUserList = $this->_objUserDb->select();
	        if (!empty($arrUserList)) {
	            foreach ($arrUserList as $key => $value) {
	                $arrUserList[$key]['name'] = !empty($value) ? $value : 'default name';
	                if (1 == $value['status']) {
	                    $statusInfo = $this->_objStatus->getUserInfo($value['status']);
	                } elseif (2 == $value['status']) {
	                    //do that
	                } else {
	                    //do else
	                }
	            }
	        }
	        return $arrUserList;
	    }
	
	    private function _doUserInfoData($arrUserData) {
	
	    }
	}
	```
12. 代码中禁止直接拼接SQL的方式(特殊场景除外)。
13. 禁止关联表查询。
14. 每个C层的接口必须有一个与之相对应的私有的过滤函数，来处理参数过滤问题。（视情况而定，如果参数过少，可以在方法体内过滤）
15. vendor层不能操作DB。
16. module、job层不操作接口。

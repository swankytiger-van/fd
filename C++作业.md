### 2.23
不能判断，因为不知道指针是否有效。如果指针有效，可以在***指向对象中***添加是否合法的***标记***进行判断。
### 2.24
i是**int**类型的变量，p是**void**类型指针，可以指向任何类型，所以p***合法***。而lp应指向**long int**类型的变量，指向**int**型的i是非法的。
### 2.25
## a
ip是指向int类型的***指针***，i是int型的***变量***，r是int型的引用
## b
i是int型的***变量***，ip是***空指针***
## c
ip是指向int类型的***指针***，ip2是int类型的***变量***
### 2.35
j为**int**型，k为**const int&**型，p为**const int***型，j2为**const int**型，k2为 **const int&** 型
```
#include<iostream>
#include<typeinfo>
int main(){
    const int i = 42;
    auto j = i; const auto &k = i; auto *p = &i;
    const auto j2 = i, &k2 = i;
    std::cout << typeid(j).name() << std::endl;
    std::cout << typeid(k).name() << std::endl;
    std::cout << typeid(p).name() << std::endl;
    std::cout << typeid(j2).name() << std::endl;
    std::cout << typeid(k2).name() << std::endl;
    return 0;
}
```
### 3.4
```
#include <iostream>
#include <cstring>
using namespace std;
int main(){
    string s1 , s2;
    std::cin >> s1;
    std::cin >> s2;
    if ( s1 > s2 )
        std::cout << s1 << std::endl;
    else if( s1 < s2 )
        std::cout << s2 << std::endl;
    else
        std::cout << " They are equal " << std::endl;
    return 0;
}
```
ps.这里如果不加`using namespace std;`就会在`string s1,s2;`处报错，不知道为什么
```
#include <iostream>
#include <cstring>
using namespace std;
int main(){
    string s1 , s2;
    std::cin >> s1;
    std::cin >> s2;
    if ( s1.size() > s2.size() )
        std::cout << s1 << std::endl;
    else if( s1.size() < s2.size() )
        std::cout << s2 << std::endl;
    else
        std::cout << " They are equal " << std::endl;
    return 0;
}
```
### 3.5
```
#include <iostream>
#include <cstring>
using namespace std;
int main(){
    string s , sum;
    while(getline (std::cin , s)){
        sum + = s;
        std::cout << sum << std::endl;
    }
    return 0;
}
```
```
#include <iostream>
#include <cstring>
using namespace std;
int main(){
    string s , sum;
    while(getline (std::cin , s)){
        sum = sum + s + " ";
        std::cout << sum << std::endl;
    }
    return 0;
}
```
### 3.20
```
#include <iostream>
#include <string>
#include <vector>
#include <cstdio>
using namespace std;
int main(){
    vector<int> v;
    int p;
    while(scanf( "%d" , &p )!=EOF)
        v.push_back(p);
    for(int i = 0 ; i < v.size() ;i + = 2)
            std::cout << v[i] + v[i+1] << std::endl;
    return 0;
}
```
```
#include <iostream>
#include <string>
#include <vector>
#include <cstdio>
using namespace std;
int main(){
    vector<int> v;
    int p;
    while(scanf( "%d" , &p )!=EOF)
        v.push_back(p);
    int length = v.size();
    for(int i = 0 ;i < length/2 ; i++)
            std::cout << v[i] + v[length-i-1] << std::endl;
    return 0;
}
```
### 3.23
```
#include <iostream>
#include <string>
#include <vector>
#include <cstdio>
using namespace std;
int main(){
    vector<int> v(10,5);
    for (auto i = v.begin(); i != v.end(); i++){
        *i = *i * 2;
        std::cout << *i << std::endl;
    }
    return 0;
}
```
### 6.10
```
#include <iostream>
#include <string>
#include <vector>
using namespace std;
void exchange(int &val1, int &val2){
	val1 = val1 + val2;
	val2 = val1 - val2;
	val1 = val1 - val2;
}
int main(){
	int val1,val2;
	cin>>val1>>val2;
	cout<<"交换之前的两数："<<val1<<" "<<val2<<endl;
	exchange(val1,val2);
	cout<<"交换之后的两数："<<val1<<" "<<val2<<endl;
	return 0;
}
```
### 6.19

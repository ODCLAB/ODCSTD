##### English | [简体中文](https://github.com/ODCLAB/ODCSTD/blob/main/zh-cn/源码排版.md)

## ✒Name

***prefix + main name + suffix***

> Example using `cpp`, applicable to any programming language or refer it.

### Main Name

<table>
	<tr>
    	<th>Pascal-Case</th>
        <td>class(function pointer type member & method), struct, union, namespace, enum, function</td>
    </tr>    
    <tr>
    	<th>Camel-Case</th>
        <td>class(normal member), var, parameter, object</td>
    </tr>
    <tr>
    	<th>Capitalize the First Letter with Google-Style</th>
        <td>macro, constant, enum<br/><code>#define CONSTANT_VALUE</code></td>
    </tr>	
</table>



- Hungarian notation for main names related to Windows APIs.

<table>
	<tr>
		<th>Prefix</th>
		<th>Mean</th>
	</tr>
    <tr>
    	<td>a</td>
        <td>array</td>
    </tr>
    <tr>
    	<td>b</td>
        <td>boolean</td>
    </tr>
    <tr>
    	<td>by</td>
        <td>unsigned char(byte)</td>
    </tr>
    <tr>
    	<td>c</td>
        <td>char</td>
    </tr>
    <tr>
    	<td>ch</td>
        <td>tchar</td>
    </tr>
    <tr>
    	<td>cb</td>
        <td>cout of bytes</td>
    </tr>
    <tr>
    	<td>f</td>
        <td>flags（usually multiple bit values）</td>
    </tr>
    <tr>
    	<td>fn</td>
        <td>function</td>
    </tr>
    <tr>
    	<td>h</td>
        <td>handle</td>
    </tr>
    <tr>
    	<td>i</td>
        <td>integer</td>
    </tr>
     <tr>
    	<td>n</td>
        <td>short int</td>
    </tr>
    <tr>
    	<td>l</td>
        <td>long</td>
    </tr>
        <tr>
    	<td>u</td>
        <td>unsigned int</td>
    </tr>
    <tr>
    	<td>ul</td>
        <td>unsigned long</td>
    </tr>
    <tr>
    	<td>w</td>
        <td>WORD(unsigned short)</td>
    </tr>
    <tr>
    	<td>dw</td>
        <td>DWORD（unsigned long）</td>
    </tr>
    <tr>
    	<td>p</td>
        <td>pointer</td>
    </tr>
    <tr>
    	<td>lp</td>
        <td>long pointer</td>
    </tr>
    <tr>
    	<td>s</td>
        <td>string</td>
    </tr>
    <tr>
    	<td>sz</td>
        <td>zero terminated string</td>
    </tr>
    <tr>
    	<td>tm</td>
        <td>text metric</td>
    </tr>
    <tr>
    	<td>x, y...</td>
        <td>coordinates（short）</td>
    </tr>
    <tr>
    	<td>v</td>
        <td>void</td>
    </tr>
</table>


- By default, the loop var uses `i`, `j`, `k`

### Suffix

- Same Body Different Type

    After main name, `-` followed by a suffix.

    | Types  | Suffix  |
    | ------ | ------- |
    | int    | _int    |
    | char   | _char   |
    | float  | _float  |
    | double | _double |
    | string | _str    |
    | point  | _p      |

- Same Body Different Status

    After main name, `-`  is followed by the status.

    ```cpp
    int repository;
    int repository_lock;
    ```

### Prefix

- Class

    ```cpp
    class C_Class{
        int m_member; //normal member
        void (*m_Member);
        ...
    
        void Function{
            ...
        } //method
            ...
    }
    ```

- Struct

    ```cpp
    struct S_Struct{
        ...
    }
    ```

- Union

    ```cpp
    union U_Union{
        ...
    }
    ```

- Namespace

    ```cpp
    namespace N_Namespace{
        ...
    }
    ```

- Enum

    ```cpp
    enum E_Enum{
        ...
    }
    ```

- Function

    ```cpp
    void Funtion{
        ...
    }
    ```

- Object

    <table>
        <tr>
            <th>Class</td>
            <td><code>C_Class c_object;</code></td>
        </tr>
        <tr>
            <th>Struct</th>
            <td><code>S_Struct s_object;</code></td>
        </tr>
        <tr>
            <th>Union</th>
            <td><code>U_Union u_object;</code></td>
        </tr>
        <tr>
            <th>Enum</th>
            <td><code>E_Enum e_object;</code></td>
        </tr>
    </table>
    
- Var

    ```cpp
    int var;
    // Abbreviation：
    int id; //Act as first word in all lowercase.
    int varID; //Do not act as the first word in all caps.
    ```

    <table>
        <tr>
            <th>Gobol</th>
            <td><code>int g_var;</code></td>
        </tr>
    </table>



## 💾Preprocessing

```mermaid
graph LR
A["#include"] --> B["#define"]
C{"#define"} --> D["numeric constant macro"] --> E["string constant macro"] --> F["parameterized constant macros"]
```



## 📗Import

```mermaid
graph LR
A[standard library/built-in library] --> B[project-made library]
C{Cpp} --> D[associated header] --> E[C std header] --> F[C++ std header] --> G[third-party header] --> H[project other header]   
```

## 💬Notes

- Comments are only in English. 

- Leave a space between the comment symbol and the code.

- When you find that you need to be excluded or there are hidden dangers in the code, if you do not solve it immediately, you should immediately mark the `TODO:` comment next to the code.

    ```cpp
    void GetStates(char* users,char* operatingSystem="Windows10"); \\TODO:param<operatingSystem>:Must be devepended on users devices, maybe need to construct a function to judge the users operating system.
    ```

- If the third-party library contained in the referenced library is required in the main source code, then a comment declaration is required in the main source code, immediately after the `#include` section.

    ```cpp
    //header.hpp
    #include <iostream>
    ```

    ```cpp
    //main.cpp
    #include "./header.hpp"
    
    /*
    #include <iostream>
    */
    
    int main(){
        std::cout << "Hello world!" << std::endl;
        return 0;
    }
    ```


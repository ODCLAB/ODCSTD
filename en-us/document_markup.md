##### English | [简体中文](https://github.com/ODCLAB/ODCSTD/blob/main/zh-cn/文档标记.md)

## 🔖Symbol

- Word

    | Shape | Mean                | Explain                                   |
    | ----- | ------------------- | ----------------------------------------- |
    | %%    | var                 | something enclosed is the var description |
    | +     | link                | leave blank before and after              |
    | “”    | unchanged or stress |                                           |
    | =>    | enlarge detail      | leave blank before and after              |

    

- Graph

  | Shape                     | Mean                     |
  | ------------------------- | ------------------------ |
  | single line without arrow | equal-level relationship |
  | pointer with arrow        | affiliated relationship  |
  
  
  
- Omit relevant content in code blocks.

  ```
  ...
  ```
  
  

## 📌Stamp

**Record document metadata**.

- Created Time

  | Location      | Format                                                       | Remark                                                       |
  | ------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
  | Word Document | 【Created Time】%year%-%month%-%day% %hour%:%minute%<br/>——————————————————————————————————————— | appears in the top row and top grid<br/>font size: 5<br/>font color: #0c0c0 |
  | Markdown      | <!--%year%-%month%-%day% %hour%:%minute%-->                  | appears in the top row and top grid                          |

- Copyright Notice

  **%copyright symbol% + %declarative body% + %additional statement%**.

  <table>
      <tr>
      	<th>Location</th>
          <th>Copyright Symbol</th>
          <th>Declarative Body</th>
          <th>Additional Statement</th>
      </tr>
      <tr>
      	<td>document</td>
          <td>Copyright ©</td>
          <td rowspan="2">%Year of copyright%-%Year of latest release% %organize% - %author%.</td>
          <td rowspan="2">All rights reserved.<br/>Something rights reserved.</td>
      </tr>
      <tr>
      	<td>code comment</td>
          <td>Copyright (C)</td>
      </tr>
  </table>



## Layout

- Latin

    <table>
        <tr>
            <th>Phrase</th>
            <td>no need<code>.</code>ending</td>
            <td>when making a title, capitalize the first letter of every word</td>
        </tr>
        <tr>
            <th>Sentence</th>
            <td>need<code>.</code>ending</td>
            <td>when making a title, capitalize the first letter</td>
        </tr>
    </table>

- Markdown

  ```markdown
  # Document Title - Subtitle
  
  ![label pattern]()
  
  ##### %current language% | [%other languages%](%corresponding document link%)
  
  ...
  
  ## Theme Title
  
  ...
  ```

- Tables for non-special cases, no periods, all phrases.

## 📝OMA-Object Description

**%operate% %modify%<%object name or content%>:%additional statement%**, multi-level relationships are represented by `()` to contain

- For Git commit information.

    | Condition            | Spacer Symbol               |
    | -------------------- | --------------------------- |
    | multiple files       | `,`<br/>close front to back |
    | different operations | `;`<br/>back space          |

    | Modifier | Value（General Structure）                       | Mean                                 |
    | -------- | ------------------------------------------------ | ------------------------------------ |
    | New      | %file name%                                      | new file                             |
    | Update   | %file name%:%describe%(%Keyword%<%object name%>) | add new features                     |
    | Rebuild  | %file name%:%change%(%Keyword%<%object name%>)   | override or modify existing features |
    | Fixed    | %file name%:%error%(%Keyword%<%object name%>)    | fix bugs                             |
    | Delete   | %file name%                                      | delete file                          |

    | Keyword  |
    | -------- |
    | var      |
    | function |
    | class    |
    | error    |
    | todo     |
    | param    |

	> Supplement of keywords：%keyword% => %keyword%:%supplement%
	
	For example:
	
	```
	New example.txt; Update example.cpp:Rename (var:float)<varFloat> from (var:int)<varInt>
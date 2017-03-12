---
title: "&lt;list&gt; (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "list"
  - "<list>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<item> (C#-XML-Tag)"
  - "<list> (C#-XML-Tag)"
  - "<listheader> (C#-XML-Tag)"
  - "item (C#-XML-Tag)"
  - "list (C#-XML-Tag)"
  - "listheader (C#-XML-Tag)"
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# &lt;list&gt; (C#-Programmierhandbuch)
## Syntax  
  
```  
<list type="bullet" | "number" | "table">  
    <listheader>  
        <term>term</term>  
        <description>description</description>  
    </listheader>  
    <item>  
        <term>term</term>  
        <description>description</description>  
    </item>  
</list>  
```  
  
#### Parameter  
 `term`  
 Ein zu definierender Term, der in `description` definiert wird.  
  
 `description`  
 ein Element in einer Aufzählung oder nummerierten Liste oder die Definition eines `term`s.  
  
## Hinweise  
 Der \<listheader\>\-Block wird zur Definition der Überschriftenzeile einer Tabelle oder einer Definitionsliste verwendet.  Wenn eine Tabelle definiert wird, muss nur ein Eintrag für "term" in der Überschrift angegeben werden.  
  
 Jedes Element der Liste wird mit einem \<item\>\-Block angegeben.  Beim Erstellen einer Definitionsliste müssen Sie sowohl `term` als auch `description` angeben.  Für eine Tabelle, eine Aufzählung oder eine nummerierte Liste muss jedoch nur ein Eintrag für `description` angegeben werden.  
  
 Eine Liste oder Tabelle kann so viele \<item\>\-Blöcke enthalten, wie benötigt werden.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
## Beispiel  
 [!code-cs[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/list_1.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
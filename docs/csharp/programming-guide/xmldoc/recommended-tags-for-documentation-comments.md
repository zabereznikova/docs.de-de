---
title: "Empfohlene Tags f&#252;r Dokumentationskommentare (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "XML [C#], Tags"
  - "XML-Dokumentation [C#], Tags"
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Empfohlene Tags f&#252;r Dokumentationskommentare (C#-Programmierhandbuch)
Der C\#\-Compiler verarbeitet Dokumentationskommentare im Code und formatiert sie als XML in einer Datei, deren Namen Sie mit der Befehlszeilenoption **\/doc** angeben können.  Um die endgültige Dokumentation auf Grundlage der vom Compiler generierte Datei zu erstellen, können Sie ein benutzerdefiniertes Tool erstellen, oder verwenden Sie ein Tool wie [Sandburg](http://shfb.codeplex.com/).  
  
 Tags werden für Codekonstrukte wie Typen und Typenmember verarbeitet.  
  
> [!NOTE]
>  Dokumentationskommentare können nicht für einen Namespace übernommen werden.  
  
 Der Compiler verarbeitet jedes Tag, das gültiges XML darstellt.  Die folgenden Tags stellen in Benutzerdokumentationen häufig verwendete Funktionen bereit:  
  
## Tags  
  
||||  
|-|-|-|  
|[\<c\>](../../../csharp/programming-guide/xmldoc/code-inline.md)|[\<para\>](../../../csharp/programming-guide/xmldoc/para.md)|[\<see\>](../../../csharp/programming-guide/xmldoc/see.md)\*|  
|[\<code\>](../../../csharp/programming-guide/xmldoc/code.md)|[\<param\>](../../../csharp/programming-guide/xmldoc/param.md)\*|[\<seealso\>](../../../csharp/programming-guide/xmldoc/seealso.md)\*|  
|[\<example\>](../../../csharp/programming-guide/xmldoc/example.md)|[\<paramref\>](../../../csharp/programming-guide/xmldoc/paramref.md)|[\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md)|  
|[\<exception\>](../../../csharp/programming-guide/xmldoc/exception.md)\*|[\<permission\>](../../../csharp/programming-guide/xmldoc/permission.md)\*|[\<typeparam\>](../../../csharp/programming-guide/xmldoc/typeparam.md)\*|  
|[\<include\>](../../../csharp/programming-guide/xmldoc/include.md)\*|[\<remarks\>](../../../csharp/programming-guide/xmldoc/remarks.md)|[\<typeparamref\>](../../../csharp/programming-guide/xmldoc/typeparamref.md)|  
|[\<list\>](../../../csharp/programming-guide/xmldoc/list.md)|[\<returns\>](../../../csharp/programming-guide/xmldoc/returns.md)|[\<value\>](../../../csharp/programming-guide/xmldoc/value.md)|  
  
 \(\* zeigt an, dass der Compiler die Syntax überprüft.\)  
  
 Wenn Sie spitze Klammern im Text eines Dokumentationskommentars haben möchten, verwenden Sie `<` und `>`, wie im folgenden Beispiel gezeigt.  
  
```xml  
/// <summary cref="C < T >">  
/// </summary>  
```  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [\/doc \(Process Documentation Comments\)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)   
 [XML\-Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
---
title: "&lt;value&gt; (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<value>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<value> (C#-XML-Tag)"
  - "value (C#-XML-Tag)"
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# &lt;value&gt; (C#-Programmierhandbuch)
## Syntax  
  
```  
<value>property-description</value>  
```  
  
#### Parameter  
 `property-description`  
 Eine Beschreibung für die Eigenschaft.  
  
## Hinweise  
 Mit dem \<value\>\-Tag kann man den Wert einer Eigenschaft beschreiben.  Wenn Sie in der Visual Studio .NET\-Entwicklungsumgebung eine Eigenschaft über den Code\-Assistenten hinzufügen, wird für die neue Eigenschaft ein [\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md)\-Tag hinzugefügt.  Sie sollten dann manuell ein \<value\>\-Tag hinzufügen, um den Wert zu beschreiben, den die Eigenschaft darstellt.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
## Beispiel  
 [!code-cs[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
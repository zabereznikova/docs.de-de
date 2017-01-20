---
title: "&lt;param&gt; (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "param"
  - "<param>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<param> C#-XML-Tag"
  - "param (C#-XML-Tag)"
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# &lt;param&gt; (C#-Programmierhandbuch)
## Syntax  
  
```  
<param name="name">description</param>  
```  
  
#### Parameter  
 `name`  
 der Name des Methodenparameters.  Der Name muss in doppelte Anführungszeichen \(**" "**\) eingeschlossen werden.  
  
 `description`  
 eine Beschreibung für den Parameter.  
  
## Hinweise  
 Das \<param\>\-Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um einen der Parameter der Methode zu beschreiben.  Um mehrere Parameter zu dokumentieren, verwenden Sie mehrere \<param\>\-Tags.  
  
 Der Text des \<param\>\-Tags wird in IntelliSense, im Objektkatalog und im Webbericht über Codekommentare angezeigt.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit ["\/doc"](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
## Beispiel  
 [!code-cs[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
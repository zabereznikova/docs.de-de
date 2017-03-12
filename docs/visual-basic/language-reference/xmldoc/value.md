---
title: "&lt;value&gt; (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "<value> XML tag"
  - "value XML tag"
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# &lt;value&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Gibt die Beschreibung einer Eigenschaft an.  
  
## Syntax  
  
```  
<value>property-description</value>  
```  
  
#### Parameter  
 `property-description`  
 Eine Beschreibung für die Eigenschaft.  
  
## Hinweise  
 Verwenden Sie das `<value>`\-Tag, um eine Eigenschaft zu beschreiben.  Wenn Sie in der Visual Studio\-Entwicklungsumgebung über den Code\-Assistenten eine Eigenschaft hinzufügen, wird für die neue Eigenschaft ein [\<summary\>](../../../visual-basic/language-reference/xmldoc/summary.md)\-Tag hinzugefügt.  Fügen Sie dann manuell ein `<value>`\-Tag hinzu, um den Wert zu beschreiben, den die Eigenschaft darstellt.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## Beispiel  
 In diesem Beispiel wird mithilfe des `<value>`\-Tags beschrieben, welchen Wert die `Counter`\-Eigenschaft enthält.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/visualbasic/value_1.vb)]  
  
## Siehe auch  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
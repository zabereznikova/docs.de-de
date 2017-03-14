---
title: "Recommended XML Tags for Documentation Comments (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlDocComment"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "tags, XML"
  - "XML comments, recommended tags [Visual Basic]"
  - "comments, recommended XML tags"
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Recommended XML Tags for Documentation Comments (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Compiler kann Dokumentationskommentare im Code zu einer XML\-Datei verarbeiten.  Sie können zusätzliche Tools verwenden, um die XML\-Datei zu Dokumentationsmaterial zu verarbeiten.  
  
 XML\-Kommentare sind für Codekonstrukte wie Typen und Typenmember zulässig.  Bei partiellen Typen kann nur ein Teil des Typs über XML\-Kommentare verfügen. Allerdings gibt es keine Einschränkungen für das Kommentieren seiner Member.  
  
> [!NOTE]
>  Dokumentationskommentare können nicht auf Namespaces angewendet werden.  Dies liegt daran, dass sich ein Namespace über mehrere Assemblys erstrecken kann. Außerdem müssen nicht alle Assemblys gleichzeitig geladen werden.  
  
 Der Compiler verarbeitet jedes Tag, das gültiges XML darstellt.  Die folgenden Tags stellen in Benutzerdokumentationen häufig verwendete Funktionen bereit:  
  
||||  
|-|-|-|  
|[\<c\>](../../../visual-basic/language-reference/xmldoc/c.md)|[\<code\>](../../../visual-basic/language-reference/xmldoc/code.md)|[\<example\>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|[\<exception\>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup>|[\<include\>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup>|[\<list\>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[\<para\>](../../../visual-basic/language-reference/xmldoc/para.md)|[\<param\>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup>|[\<paramref\>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|[\<permission\>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup>|[\<remarks\>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[\<returns\>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|[\<see\>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup>|[\<seealso\>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup>|[\<summary\>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|[\<typeparam\>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup>|[\<value\>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 \(<sup>1</sup> Der Compiler überprüft Syntax.\)  
  
> [!NOTE]
>  Wenn ein Dokumentationskommentar spitze Klammern enthalten soll, verwenden Sie `<` und `>`.  So wird zum Beispiel die Zeichenfolge `"<text in angle brackets>"` als `<text in angle` `brackets>` angezeigt.  
  
## Siehe auch  
 [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)   
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)   
 [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
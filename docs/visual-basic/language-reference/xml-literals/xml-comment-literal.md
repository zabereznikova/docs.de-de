---
title: "XML Comment Literal (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlLiteralComment"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "comment literal [Visual Basic]"
  - "XML comments, adding [Visual Basic]"
  - "XML comment literal [Visual Basic]"
  - "XML literals [Visual Basic], comment"
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# XML Comment Literal (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Ein Literal, das ein <xref:System.Xml.Linq.XComment>\-Objekt darstellt.  
  
## Syntax  
  
```  
<!-- content -->  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`<!--`|Erforderlich.  Kennzeichnet den Anfang des XML\-Kommentars.|  
|`content`|Erforderlich.  Text, der im XML\-Kommentar angezeigt werden soll.  Darf keine zwei aufeinander folgende Bindestriche enthalten \(\-\-\) oder mit einem Bindestrich enden, der an ein Endtag grenzt.|  
|`-->`|Erforderlich.  Kennzeichnet das Ende des XML\-Kommentars.|  
  
## Rückgabewert  
 Ein <xref:System.Xml.Linq.XComment>\-Objekt.  
  
## Hinweise  
 XML\-Kommentarliterale enthalten keinen Dokumentinhalt. Sie enthalten Informationen über das Dokument.  Der XML\-Kommentarabschnitt endet mit der Sequenz "\-\-\>".  Dies impliziert folgende Punkte:  
  
-   In einem XML\-Kommentarliteral können keine eingebetteten Ausdrücke verwendet werden, da die Trennzeichen für eingebettete Ausdrücke gültiger Inhalt von XML\-Kommentaren sind.  
  
-   XML\-Kommentarabschnitte können nicht geschachtelt werden, da `content` nicht den Wert "\-\-\>" enthalten darf.  
  
 Ein XML\-Kommentarliteral kann einer Variablen zugewiesen oder in einem XML\-Elementliteral eingeschlossen werden.  
  
> [!NOTE]
>  Ein XML\-Literal kann mehrere Zeilen umfassen, ohne Zeilenfortsetzungszeichen zu verwenden.  Mit diesem Feature können Sie den Inhalt eines XML\-Dokuments kopieren und direkt in ein [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Programm einfügen.  
  
 Der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Compiler konvertiert das XML\-Kommentarliteral in einen Aufruf des <xref:System.Xml.Linq.XComment.%23ctor%2A>\-Konstruktors.  
  
## Beispiel  
 Im folgenden Beispiel wird ein XML\-Kommentar erstellt, der den Text "This is a comment" enthält.  
  
 [!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## Siehe auch  
 <xref:System.Xml.Linq.XComment>   
 [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
---
title: "&lt;include&gt; (Visual Basic) | Microsoft Docs"
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
  - "include XML tag"
  - "<include> XML tag"
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# &lt;include&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Verweist auf eine andere Datei, in der die Typen und Member im Quellcode beschrieben werden.  
  
## Syntax  
  
```  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### Parameter  
 `filename`  
 Erforderlich.  der Name der Datei, die die Dokumentation enthält.  Der Dateiname kann mit einem Pfad gekennzeichnet sein.  `filename` muss in doppelte Anführungszeichen \(" "\) eingeschlossen werden.  
  
 `tagpath`  
 Erforderlich.  Der Pfad der Tags in `filename`, der zum `name`\-Tag führt.  Der Pfad muss in doppelte Anführungszeichen \(" "\) eingeschlossen werden.  
  
 `name`  
 Erforderlich.  Der Namensbezeichner in dem Tag, das sich vor den Kommentaren befindet.  `Name` weist eine `id` auf.  
  
 `id`  
 Erforderlich.  die ID für das Tag, das sich vor den Kommentaren befindet.  Die ID muss in einfache Anführungszeichen \(' '\) eingeschlossen werden.  
  
## Hinweise  
 Mit dem `<include>`\-Tag kann auf Kommentare in anderen Dateien verwiesen werden, die die Typen und Member im Quellcode beschreiben.  Dies stellt eine Alternative zum direkten Positionieren der Dokumentationskommentare in Quellcodedateien dar.  
  
 Das `<include>`\-Tag entspricht der Empfehlung der W3C XML Path Language \(XPath\), Version 1.0.  Weitere Informationen zu Möglichkeiten, die `<include>`\-Verwendung anzupassen, finden Sie unter der Adresse http:\/\/www.w3.org\/TR\/xpath.  
  
## Beispiel  
 In diesem Beispiel wird das `<include>`\-Tag verwendet, um Memberdokumentationskommentare aus einer Datei mit dem Namen `commentFile.xml` zu importieren.  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 Die Datei `commentFile.xml` hat folgendes Format.  
  
```  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## Siehe auch  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
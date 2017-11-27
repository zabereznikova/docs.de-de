---
title: '&lt;umfassen&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 22eebaa8da8ef082e132cfdf8cb68498bfe16d73
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltincludegt-visual-basic"></a>&lt;umfassen&gt; (Visual Basic)
Bezieht sich auf eine andere Datei, die die Typen und Member im Quellcode beschreibt.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a>Parameter  
 `filename`  
 Erforderlich. Der Name der Datei mit der Dokumentation. Der Dateiname kann mit einem Pfad qualifiziert werden. Schließen Sie `filename` in doppelte Anführungszeichen ("").  
  
 `tagpath`  
 Erforderlich. Der Pfad der Tags in `filename`, der zum Tag `name` führt. Schließen Sie den Pfad in doppelte Anführungszeichen ("").  
  
 `name`  
 Erforderlich. Der Namensbezeichner in dem Tag, das die Kommentare vorausgeht. `Name`weist ein `id`.  
  
 `id`  
 Erforderlich. Die ID für das Tag, das sich vor den Kommentaren befindet. Die ID muss in einfache Anführungszeichen ("").  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `<include>` -Tag zum Verweisen auf Kommentare in einer anderen Datei, die beschreiben, die Typen und Member im Quellcode. Dies ist eine Alternative zum direkten Platzieren von Dokumentationskommentaren in der Quellcodedatei.  
  
 Die `<include>` Tag verwendet die Empfehlung der W3C XML Path Language (XPath) Version 1.0. Weitere Informationen zu Methoden zum Anpassen Ihrer `<include>` Verwendung finden Sie unter http://www.w3.org/TR/xpath.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<include>` Tag Dokumentationskommentare Mitglied aus einer Datei namens importieren `commentFile.xml`.  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 Das Format der `commentFile.xml` lautet wie folgt.  
  
```xml  
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
  
## <a name="see-also"></a>Siehe auch  
 [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)

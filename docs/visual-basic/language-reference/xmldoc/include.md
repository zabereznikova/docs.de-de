---
title: '&lt;umfassen&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: 1cd992ae12e21b3d7fe29aff5a15b280c663d13b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693067"
---
# <a name="ltincludegt-visual-basic"></a>&lt;umfassen&gt; (Visual Basic)
Bezieht sich auf eine andere Datei, die die Typen und Member im Quellcode beschreibt.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a>Parameter  
 `filename`  
 Erforderlich. Der Name der Datei, die die Dokumentation enthält. Der Dateiname kann mit einem Pfad qualifiziert werden. Schließen Sie `filename` in doppelte Anführungszeichen ("").  
  
 `tagpath`  
 Erforderlich. Der Pfad der Tags in `filename`, der zum Tag `name` führt. Schließen Sie den Pfad in doppelte Anführungszeichen ("").  
  
 `name`  
 Erforderlich. Der Namensbezeichner in dem Tag, das vor den Kommentaren befindet. `Name` hat eine `id`.  
  
 `id`  
 Erforderlich. Die ID für das Tag, das sich vor den Kommentaren befindet. Die ID muss in einfache Anführungszeichen ("").  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `<include>` -Tag zum Verweisen auf Kommentare in einer anderen Datei, die beschreiben, die Typen und Member im Quellcode. Dies ist eine Alternative zum direkten Platzieren von Dokumentationskommentaren in der Quellcodedatei.  
  
 Die `<include>` Tag verwendet die Empfehlung des W3C XML Path Language (XPath) Version 1.0. Weitere Informationen zu Möglichkeiten zum Anpassen Ihrer `<include>` finden Sie unter <https://www.w3.org/TR/xpath>.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<include>` Tag zum Importieren von Dokumentationskommentaren Member aus einer Datei namens `commentFile.xml`.  
  
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
- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)

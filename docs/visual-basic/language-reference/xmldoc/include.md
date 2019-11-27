---
title: <include>
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: 2f2bebfd06d4614f05cb66834cc5bef40524ce3b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348460"
---
# <a name="include-visual-basic"></a>\<include > (Visual Basic)
Verweist auf eine andere Datei, in der die Typen und Member im Quellcode beschrieben werden.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a>Parameter  
 `filename`  
 Erforderlich Der Name der Datei, die die Dokumentation enthält. Der Dateiname kann mit einem Pfad qualifiziert werden. Schließen Sie `filename` in doppelte Anführungszeichen ("") ein.  
  
 `tagpath`  
 Erforderlich Der Pfad der Tags in `filename`, der zum Tag `name` führt. Schließen Sie den Pfad in doppelte Anführungszeichen ("") ein.  
  
 `name`  
 Erforderlich Der namensspezifizierer im-Tag, der den Kommentaren vorangestellt ist. `Name` verfügen über eine `id`.  
  
 `id`  
 Erforderlich Die ID für das Tag, das sich vor den Kommentaren befindet. Schließen Sie die ID in einfache Anführungszeichen (' ') ein.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie das `<include>`-Tag, um auf Kommentare in einer anderen Datei zu verweisen, in der die Typen und Member im Quellcode beschrieben werden. Dies ist eine Alternative zum direkten Platzieren von Dokumentationskommentaren in der Quellcodedatei.  
  
 Das `<include>`-Tag verwendet die W3C-Empfehlung XPath (XML Path Language), Version 1,0. Weitere Informationen zu Möglichkeiten zum Anpassen Ihrer `<include>` finden Sie unter <https://www.w3.org/TR/xpath>.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das `<include>`-Tag verwendet, um Member-Dokumentations Kommentare aus einer Datei namens `commentFile.xml`zu importieren.  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
 Das Format des `commentFile.xml` lautet wie folgt.  
  
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

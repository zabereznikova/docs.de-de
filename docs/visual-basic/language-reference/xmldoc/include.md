---
title: <include>
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: 78a10624107cea349b01f484c641190a945dbd7e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400110"
---
# <a name="include-visual-basic"></a>\<include> (Visual Basic)
Verweist auf eine andere Datei, in der die Typen und Member im Quellcode beschrieben werden.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a>Parameter  
 `filename`  
 Erforderlich. Der Name der Datei, die die Dokumentation enthält. Der Dateiname kann mit einem Pfad qualifiziert werden. Schließen Sie `filename` in doppelte Anführungszeichen ("") ein.  
  
 `tagpath`  
 Erforderlich. Der Pfad der Tags in `filename`, der zum Tag `name` führt. Schließen Sie den Pfad in doppelte Anführungszeichen ("") ein.  
  
 `name`  
 Erforderlich. Der namensspezifizierer im-Tag, der den Kommentaren vorangestellt ist. `Name`verfügt über einen `id` .  
  
 `id`  
 Erforderlich. Die ID für das Tag, das sich vor den Kommentaren befindet. Schließen Sie die ID in einfache Anführungszeichen (' ') ein.  
  
## <a name="remarks"></a>Bemerkungen  
 Verwenden Sie das- `<include>` Tag, um auf Kommentare in einer anderen Datei zu verweisen, die die Typen und Member im Quellcode beschreiben. Dies ist eine Alternative zum direkten Platzieren von Dokumentationskommentaren in der Quellcodedatei.  
  
 Das- `<include>` Tag verwendet die W3C-Empfehlung XPath (XML Path Language), Version 1,0. Weitere Informationen zu Möglichkeiten zum Anpassen Ihrer `<include>` Verwendung finden Sie unter <https://www.w3.org/TR/xpath> .  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das- `<include>` Tag verwendet, um Member-Dokumentations Kommentare aus einer Datei namens zu importieren `commentFile.xml` .  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
 Das Format von `commentFile.xml` lautet wie folgt.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [XML-Kommentartags](index.md)

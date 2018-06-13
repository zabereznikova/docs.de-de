---
title: '&lt;seealso&gt; (C#-Programmierhandbuch)'
ms.date: 07/20/2015
f1_keywords:
- cref
- <seealso>
- seealso
helpviewer_keywords:
- cref [C#], see also
- seealso C# XML tag
- cref [C#]
- cross-references [C#], tags
- <seealso> C# XML tag
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
ms.openlocfilehash: e3c9d68884e5cd4f5a4f81580f60cdde775458a3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349134"
---
# <a name="ltseealsogt-c-programming-guide"></a>&lt;seealso&gt; (C#-Programmierhandbuch)
## <a name="syntax"></a>Syntax  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a>Parameter  
 cref = " `member`"  
 Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann. Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe.`member` muss in doppelte Anführungszeichen („“) gesetzt werden.  
  
 Weitere Informationen zum Erstellen eines cref-Verweises auf einen generischen Typ finden Sie unter [\<see>](../../../csharp/programming-guide/xmldoc/see.md).  
  
## <a name="remarks"></a>Hinweise  
 Mit dem \<seealso>-Tag kann der Text angegeben werden, der im Abschnitt „Siehe auch“ angezeigt werden sollen. Mit [\<see>](../../../csharp/programming-guide/xmldoc/see.md) kann ein Link im Text angegeben werden.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel für die Verwendung von \<seealso> finden Sie unter [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Empfohlene Tags für Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

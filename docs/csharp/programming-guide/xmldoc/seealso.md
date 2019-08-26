---
title: <seealso> – C#-Programmierhandbuch
ms.custom: seodec18
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
ms.openlocfilehash: 3ddaa7efec2b4bf5ffa53971aa6f380a1be9bad8
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587659"
---
# <a name="seealso-c-programming-guide"></a>\<seealso> (C#-Programmierhandbuch)
## <a name="syntax"></a>Syntax  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a>Parameter  
 cref = " `member`"  
 Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann. Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe.`member` muss in doppelte Anführungszeichen („“) gesetzt werden.  
  
 Weitere Informationen zum Erstellen eines cref-Verweises auf einen generischen Typ finden Sie unter [\<see>](./see.md).  
  
## <a name="remarks"></a>Anmerkungen  
 Mit dem \<seealso>-Tag kann der Text angegeben werden, der im Abschnitt „Siehe auch“ angezeigt werden sollen. Mit [\<see>](./see.md) kann ein Link im Text angegeben werden.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel für die Verwendung von \<seealso> finden Sie unter [\<summary>](./summary.md).  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)

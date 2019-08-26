---
title: <permission> – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: e9eb50394f01072a194d3f746577707f89ba65dd
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587883"
---
# <a name="permission-c-programming-guide"></a>\<permission> (C#-Programmierhandbuch)
## <a name="syntax"></a>Syntax  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a>Parameter  
 cref = " `member`"  
 Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann. Der Compiler prüft, ob das angegebene Codeelement vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen. *member* muss in doppelte Anführungszeichen (" ") gesetzt werden.  
  
 Weitere Informationen zum Erstellen eines cref-Verweises auf einen generischen Typ finden Sie unter [\<see>](./see.md).  
  
 `description`  
 Eine Beschreibung des Zugriffs auf den Member  
  
## <a name="remarks"></a>Anmerkungen  
 Mit dem \<permission>-Tag können Sie den Zugriff auf einen Member dokumentieren. Mit der <xref:System.Security.PermissionSet>-Klasse können Sie den Zugriff auf ein Member angeben.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)

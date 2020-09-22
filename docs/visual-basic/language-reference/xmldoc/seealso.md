---
title: <seealso>
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: f435fa2ab86d81053cd185f5d90ec22996a1458d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869411"
---
# <a name="seealso-visual-basic"></a>\<seealso> (Visual Basic)

Gibt einen Link an, der im Abschnitt "Siehe auch" angezeigt wird.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a>Parameter  

 `member`  
 Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann. Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe. `member` muss in doppelte Anführungszeichen (" ") gesetzt werden.  
  
## <a name="remarks"></a>Bemerkungen  

 Verwenden Sie das- `<seealso>` Tag, um den Text anzugeben, der in einem Abschnitt Siehe auch angezeigt werden soll. Mit [\<see>](see.md) kann ein Link im Text angegeben werden.  
  
 Kompilieren Sie mit [-doc](../../reference/command-line-compiler/doc.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird das- `<seealso>` Tag im Abschnitt "Hinweise" verwendet `DoesRecordExist` , um auf die-Methode zu verweisen `UpdateRecord` .  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Weitere Informationen

- [XML-Kommentartags](index.md)

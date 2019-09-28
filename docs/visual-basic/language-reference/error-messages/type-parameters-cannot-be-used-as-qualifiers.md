---
title: Typparameter können nicht als Qualifizierer verwendet werden.
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 88b5f365c47b98964d9f5a0d22a941d85dcfb95f
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592138"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a>Typparameter können nicht als Qualifizierer verwendet werden.
Ein Programmier Element wird mit einer Qualifikations Zeichenfolge qualifiziert, die einen Typparameter enthält.  
  
 Ein Typparameter stellt eine Anforderung für einen Typ dar, der beim Konstruieren des generischen Typs bereitgestellt werden soll. Sie stellt keinen bestimmten definierten Typ dar. Eine Qualifizierungs Zeichenfolge darf nur Elemente enthalten, die zur Kompilierzeit definiert werden.  
  
 Dieser Fehler kann durch die folgenden Anweisungen generiert werden.  
  
```vb  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 **Fehler-ID:** BC32098  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Entfernen Sie den Typparameter aus der Qualifikations Zeichenfolge, oder ersetzen Sie ihn durch einen definierten Typ.  
  
2. Wenn Sie einen konstruierten Typ verwenden müssen, um das zu qualifizierte Programmier Element zu suchen, müssen Sie zusätzliche Programmlogik verwenden.  
  
## <a name="see-also"></a>Siehe auch

- [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Typliste](../../../visual-basic/language-reference/statements/type-list.md)

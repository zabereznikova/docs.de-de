---
title: Typparameter können nicht als Qualifizierer verwendet werden.
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: ba7348ae50965ffcf2719b20934451916c8fa95a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296354"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a>Typparameter können nicht als Qualifizierer verwendet werden.
Ein Programmierelement wird mit einem Qualifizierungspfad qualifiziert, die einen Typparameter enthält.  
  
 Einen Typparameter darstellt, eine Anforderung für einen Typ, der bereitgestellt werden, wenn der generische Typ konstruiert wird. Es stellt keinen bestimmten definierten Typ dar. Ein Qualifizierungspfad muss es sich um nur Elemente enthalten, die zum Zeitpunkt der Kompilierung definiert sind.  
  
 Dieser Fehler kann durch die folgenden Anweisungen generiert werden.  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 **Fehler-ID:** BC32098  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Entfernen Sie den Typparameter in der qualifizierungszeichenfolge oder Ersetzen Sie ihn durch einen definierten Typ.  
  
2. Wenn Sie einen konstruierten Typ zu verwenden, um die qualifizierenden Programmierelements suchen möchten, müssen Sie zusätzliche Programmlogik verwenden.  
  
## <a name="see-also"></a>Siehe auch

- [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Type List](../../../visual-basic/language-reference/statements/type-list.md)

---
title: MustOverride
ms.date: 07/20/2015
f1_keywords:
- vb.MustOverride
- MustOverride
helpviewer_keywords:
- virtual elements [Visual Basic], pure
- elements [Visual Basic], pure virtual
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- overriding, MustOverride keyword
- procedures [Visual Basic], redefining
- pure virtual elements [Visual Basic]
- MustOverride keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
ms.openlocfilehash: 1b20108a2d42e82c0af7598fde8d60a08fea28ec
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396193"
---
# <a name="mustoverride-visual-basic"></a>MustOverride (Visual Basic)
Gibt an, dass eine Eigenschaft oder Prozedur nicht in dieser Klasse implementiert wird und in einer abgeleiteten Klasse überschrieben werden muss, bevor Sie verwendet werden kann.  
  
## <a name="remarks"></a>Bemerkungen  
 Sie können `MustOverride` nur in einer Deklarations Anweisung für eine Eigenschaft oder Prozedur verwenden. Die Eigenschaft oder Prozedur, die angibt, `MustOverride` muss ein Member einer Klasse sein, und die Klasse muss als [MustInherit](mustinherit.md)gekennzeichnet sein.  
  
## <a name="rules"></a>Regeln  
  
- **Unvollständige Deklaration.** Wenn Sie angeben `MustOverride` , geben Sie keine zusätzlichen Codezeilen für die Eigenschaft oder Prozedur an, nicht sogar die- `End Function` ,- `End Property` oder- `End Sub` Anweisung.  
  
- **Kombinierte Modifizierer.** Sie können nicht `MustOverride` mit `NotOverridable` , `Overridable` oder `Shared` in derselben Deklaration angeben.  
  
- **Shadowing und Überschreiben.** Sowohl das Shadowing als auch das Überschreiben definieren ein geerbtes Element neu, es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen. Weitere Informationen finden Sie unter [shadowingin Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).  
  
- **Alternative Begriffe.** Ein Element, das nur in einer außer Kraft Setzung verwendet werden kann, wird manchmal als *reines virtuelles* Element bezeichnet.  
  
 Der `MustOverride`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Function-Anweisung](../statements/function-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Sub-Anweisung](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [NotOverridable](notoverridable.md)
- [Overrides](overridable.md)
- [Überschreibt](overrides.md)
- [MustInherit](mustinherit.md)
- [Schlüsselwörter](../keywords/index.md)
- [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)

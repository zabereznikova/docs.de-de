---
title: MustOverride (Visual Basic)
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
ms.openlocfilehash: fedebf3ee791fbab02ace2ba2dc121590a241c53
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627329"
---
# <a name="mustoverride-visual-basic"></a>MustOverride (Visual Basic)
Gibt an, dass eine Eigenschaft oder Prozedur nicht in dieser Klasse implementiert ist und in einer abgeleiteten Klasse überschrieben werden muss, bevor sie verwendet werden kann.  
  
## <a name="remarks"></a>Hinweise  
 Sie können `MustOverride` nur in einer Eigenschaft oder einer Prozedurdeklarationsanweisung verwenden. Die Eigenschaft oder Prozedur, der angibt, `MustOverride` muss ein Member einer Klasse, und die Klasse muss markiert sein [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).  
  
## <a name="rules"></a>Regeln  
  
-   **Unvollständige Deklaration.** Beim Angeben von `MustOverride`, Sie sind keine zusätzlichen Codezeilen für die Eigenschaft oder Prozedur, angeben, nicht auch auf dem `End Function`, `End Property`, oder `End Sub` Anweisung.  
  
-   **Kombinierte Modifizierer.** Sie können keine angeben `MustOverride` zusammen mit `NotOverridable`, `Overridable`, oder `Shared` in der gleichen Deklaration.  
  
-   **Shadowing und überschreiben.** Sowohl das Shadowing als auch das Überschreiben definieren ein geerbtes Element neu, es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen. Weitere Informationen finden Sie unter [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
-   **Alternative Begriffe.** Ein Element, das nur in einer Überschreibung verwendet werden kann bezeichnet ein *rein virtuellen* Element.  
  
 Der `MustOverride`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch
- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)
- [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
- [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)

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
ms.openlocfilehash: dc6a153a604fd0e5cee9d7d46ebcd63294f33628
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351486"
---
# <a name="mustoverride-visual-basic"></a>MustOverride (Visual Basic)
Gibt an, dass eine Eigenschaft oder Prozedur nicht in dieser Klasse implementiert wird und in einer abgeleiteten Klasse überschrieben werden muss, bevor Sie verwendet werden kann.  
  
## <a name="remarks"></a>Hinweise  
 Sie können `MustOverride` nur in einer Eigenschaft oder Prozedur Deklarations Anweisung verwenden. Die Eigenschaft oder Prozedur, die angibt, `MustOverride` muss ein Member einer Klasse sein, und die Klasse muss als [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)markiert werden.  
  
## <a name="rules"></a>Regeln  
  
- **Unvollständige Deklaration.** Wenn Sie `MustOverride`angeben, geben Sie keine zusätzlichen Codezeilen für die Eigenschaft oder Prozedur an, nicht sogar für die `End Function`, `End Property`oder `End Sub` Anweisung.  
  
- **Kombinierte modifiziererer.** Sie können `MustOverride` nicht mit `NotOverridable`, `Overridable`oder `Shared` in derselben Deklaration angeben.  
  
- **Shadogerichteten und überschreiben.** Sowohl das Shadowing als auch das Überschreiben definieren ein geerbtes Element neu, es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen. Weitere Informationen finden Sie unter [shadowingin Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
- **Alternative Begriffe.** Ein Element, das nur in einer außer Kraft Setzung verwendet werden kann, wird manchmal als *reines virtuelles* Element bezeichnet.  
  
 Der `MustOverride`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch

- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)
- [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
- [Shadodown in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)

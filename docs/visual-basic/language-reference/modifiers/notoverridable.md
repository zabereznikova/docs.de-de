---
title: NotOverridable
ms.date: 07/20/2015
f1_keywords:
- vb.NotOverridable
- NotOverridable
helpviewer_keywords:
- sealed methods [Visual Basic]
- NotOverridable keyword [Visual Basic]
- properties [Visual Basic], redefining
- elements [Visual Basic], sealed
- sealed [elements VB]
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- methods [Visual Basic], sealed
- properties [Visual Basic], overriding
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
ms.openlocfilehash: c55d57bb3008b2825fe5382844908ea32f0d500c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351447"
---
# <a name="notoverridable-visual-basic"></a>NotOverridable (Visual Basic)
Gibt an, dass eine Eigenschaft oder Prozedur in einer abgeleiteten Klasse nicht überschrieben werden kann.  
  
## <a name="remarks"></a>Hinweise  
 Der `NotOverridable` Modifizierer verhindert, dass eine Eigenschaft oder Methode in einer abgeleiteten Klasse überschrieben wird.  Der [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) -Modifizierer ermöglicht, dass eine Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse überschrieben wird. Weitere Informationen finden Sie unter [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Wenn die `Overridable` oder `NotOverridable` Modifizierer nicht angegeben ist, hängt die Standardeinstellung davon ab, ob die Eigenschaft oder Methode eine Basisklassen Eigenschaft oder-Methode überschreibt. Wenn die Eigenschaft oder Methode eine Basisklassen Eigenschaft oder-Methode überschreibt, ist die Standardeinstellung `Overridable`. Andernfalls ist es `NotOverridable`.  
  
 Ein Element, das nicht überschrieben werden kann, wird manchmal als *versiegeltes* Element bezeichnet.  
  
 Sie können `NotOverridable` nur in einer Eigenschaft oder Prozedur Deklarations Anweisung verwenden. Sie können `NotOverridable` nur für eine Eigenschaft oder Prozedur angeben, die eine andere Eigenschaft oder Prozedur überschreibt, d. h. nur in Kombination mit `Overrides`.  
  
## <a name="combined-modifiers"></a>Kombinierte modifiziererer  
 Sie können `Overridable` oder `NotOverridable` nicht für eine `Private` Methode angeben.  
  
 Sie können `NotOverridable` nicht mit `MustOverride`, `Overridable`oder `Shared` in derselben Deklaration angeben.  
  
## <a name="usage"></a>Verwendung  
 Der `NotOverridable`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch

- [Modifizierer](../../../visual-basic/language-reference/modifiers/index.md)
- [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
- [Shadodown in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)

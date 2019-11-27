---
title: Overridable
ms.date: 07/20/2015
f1_keywords:
- Overridable
- vb.Overridable
helpviewer_keywords:
- elements [Visual Basic], concrete
- properties [Visual Basic], redefining
- overriding, Overridable keyword
- elements [Visual Basic], virtual
- virtual [elements VB]
- procedures [Visual Basic], overriding
- concrete [elements VB]
- procedures [Visual Basic], redefining
- Overridable keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 612581e7-8a4c-4a5d-beff-3402fffa6f35
ms.openlocfilehash: 9c639665fd92a56de6fb6e5147cda873ef457b45
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351402"
---
# <a name="overridable-visual-basic"></a>Overridable (Visual Basic)
Gibt an, dass eine Eigenschaft oder Prozedur durch eine identisch benannte Eigenschaft oder Prozedur in einer abgeleiteten Klasse überschrieben werden kann.  
  
## <a name="remarks"></a>Hinweise  
 Der `Overridable` Modifizierer ermöglicht, dass eine Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse überschrieben wird. Der [nodeverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) -Modifizierer verhindert, dass eine Eigenschaft oder Methode in einer abgeleiteten Klasse überschrieben wird.  Weitere Informationen finden Sie unter [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Wenn die `Overridable` oder `NotOverridable` Modifizierer nicht angegeben ist, hängt die Standardeinstellung davon ab, ob die Eigenschaft oder Methode eine Basisklassen Eigenschaft oder-Methode überschreibt. Wenn die Eigenschaft oder Methode eine Basisklassen Eigenschaft oder-Methode überschreibt, ist die Standardeinstellung `Overridable`. Andernfalls ist es `NotOverridable`.  
  
 Sie können einen Schatten oder überschreiben, um ein geerbtes Element neu zu definieren, aber es gibt bedeutende Unterschiede zwischen den beiden Ansätzen. Weitere Informationen finden Sie unter [shadowingin Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
 Ein Element, das überschrieben werden kann, wird manchmal als *Virtuelles* Element bezeichnet. Wenn Sie überschrieben werden kann, aber nicht sein muss, wird Sie manchmal auch als *konkretes* Element bezeichnet.  
  
 Sie können `Overridable` nur in einer Eigenschaft oder Prozedur Deklarations Anweisung verwenden.  
  
## <a name="combined-modifiers"></a>Kombinierte modifiziererer  
 Sie können `Overridable` oder `NotOverridable` nicht für eine `Private` Methode angeben.  
  
 Sie können `Overridable` nicht mit `MustOverride`, `NotOverridable`oder `Shared` in derselben Deklaration angeben.  
  
 Da ein überschreibendes Element implizit überschreibbar ist, können Sie `Overridable` nicht mit `Overrides` kombinieren.  
  
## <a name="usage"></a>Verwendung  
 Der `Overridable`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch

- [Modifizierer](../../../visual-basic/language-reference/modifiers/index.md)
- [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
- [Shadodown in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)

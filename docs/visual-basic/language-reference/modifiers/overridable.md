---
title: Overridable (Visual Basic)
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
ms.openlocfilehash: 4844bf7f3ecf23335715b950a96be15e54ebc601
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603768"
---
# <a name="overridable-visual-basic"></a>Overridable (Visual Basic)
Gibt an, dass eine Eigenschaft oder Prozedur von einer gleichnamigen Eigenschaft oder Prozedur in einer abgeleiteten Klasse überschrieben werden kann.  
  
## <a name="remarks"></a>Hinweise  
 Die `Overridable` Modifizierer ermöglicht einer Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse überschrieben werden. Die [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md) Modifizierer verhindert, dass eine Eigenschaft oder Methode in einer abgeleiteten Klasse überschrieben wird.  Weitere Informationen finden Sie unter [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Wenn die `Overridable` oder `NotOverridable` Modifizierer nicht angegeben wird, hängt von der Standardeinstellung gibt an, ob die Eigenschaft oder Methode einer Basisklasse-Eigenschaft oder Methode überschreibt. Wenn die Eigenschaft oder Methode einer Basisklasse-Eigenschaft oder Methode überschreibt, die Standardeinstellung ist `Overridable`ist, andernfalls ist er `NotOverridable`.  
  
 Sie können zu überschatten oder überschreiben, um ein geerbtes Element neu definieren allerdings bestehen bedeutende Unterschiede zwischen den beiden Ansätzen. Weitere Informationen finden Sie unter [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
 Ein Element, das überschrieben werden kann wird manchmal als bezeichnet eine *virtuellen* Element. Kann überschrieben werden, jedoch keine sein, ist es auch manchmal bezeichnet eine *konkrete* Element.  
  
 Sie können `Overridable` nur in einer Eigenschaft oder einer Prozedurdeklarationsanweisung verwenden.  
  
## <a name="combined-modifiers"></a>Kombinierte Modifizierer  
 Sie können keine angeben `Overridable` oder `NotOverridable` für eine `Private` Methode.  
  
 Sie können keine angeben `Overridable` zusammen mit `MustOverride`, `NotOverridable`, oder `Shared` in der gleichen Deklaration.  
  
 Da ein überschreibendes Element implizit überschreibbar ist, können Sie `Overridable` nicht mit `Overrides` kombinieren.  
  
## <a name="usage"></a>Verwendung  
 Der `Overridable`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Modifizierer](../../../visual-basic/language-reference/modifiers/index.md)  
 [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)  
 [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)

---
title: NotOverridable (Visual Basic)
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
ms.openlocfilehash: 41c08a48fdb7501081e887fb5cf9f99c334c72ac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920652"
---
# <a name="notoverridable-visual-basic"></a>NotOverridable (Visual Basic)
Gibt an, dass eine Eigenschaft oder Prozedur kann nicht in einer abgeleiteten Klasse überschrieben werden.  
  
## <a name="remarks"></a>Hinweise  
 Die `NotOverridable` Modifizierer verhindert, dass eine Eigenschaft oder Methode in einer abgeleiteten Klasse überschrieben wird.  Die [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) Modifizierers können Sie eine Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse überschrieben werden. Weitere Informationen finden Sie unter [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Wenn die `Overridable` oder `NotOverridable` Modifizierer ist nicht angegeben wird, hängt von der Standardeinstellung gibt an, ob die Eigenschaft oder Methode einer Basisklasse-Eigenschaft oder Methode überschreibt. Wenn die Eigenschaft oder Methode einer Basisklasse-Eigenschaft oder Methode überschreibt, die Standardeinstellung ist `Overridable`ist, andernfalls ist `NotOverridable`.  
  
 Ein Element, das nicht überschrieben werden bezeichnet ein *versiegelten* Element.  
  
 Sie können `NotOverridable` nur in einer Eigenschaft oder einer Prozedurdeklarationsanweisung verwenden. Sie können angeben, `NotOverridable` nur auf eine Eigenschaft oder Prozedur, die eine andere Eigenschaft oder Prozedur, d. h. nur in Kombination mit überschreibt `Overrides`.  
  
## <a name="combined-modifiers"></a>Kombinierte Modifizierer  
 Sie können keine angeben `Overridable` oder `NotOverridable` für eine `Private` Methode.  
  
 Sie können keine angeben `NotOverridable` zusammen mit `MustOverride`, `Overridable`, oder `Shared` in der gleichen Deklaration.  
  
## <a name="usage"></a>Verwendung  
 Der `NotOverridable`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch

- [Modifizierer](../../../visual-basic/language-reference/modifiers/index.md)
- [Grundlagen der Vererbung](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)
- [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
- [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)

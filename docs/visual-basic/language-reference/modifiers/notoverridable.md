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
ms.openlocfilehash: 8eec54a12c7fb748df46e8c48a8b07eab983cc72
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867862"
---
# <a name="notoverridable-visual-basic"></a>NotOverridable (Visual Basic)

Gibt an, dass eine Eigenschaft oder Prozedur in einer abgeleiteten Klasse nicht überschrieben werden kann.  
  
## <a name="remarks"></a>Bemerkungen  

 Der- `NotOverridable` Modifizierer verhindert, dass eine Eigenschaft oder Methode in einer abgeleiteten Klasse überschrieben wird.  Der [Overridable](overridable.md) -Modifizierer ermöglicht, dass eine Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse überschrieben wird. Weitere Informationen finden Sie unter [Grundlagen der Vererbung](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Wenn der `Overridable` - `NotOverridable` Modifizierer oder der-Modifizierer nicht angegeben wird, ist die Standardeinstellung davon abhängig, ob die Eigenschaft oder Methode eine Basisklassen Eigenschaft oder-Methode überschreibt. Wenn die Eigenschaft oder Methode eine Basisklassen Eigenschaft oder-Methode überschreibt, ist die Standardeinstellung `Overridable` . andernfalls ist Sie `NotOverridable` .  
  
 Ein Element, das nicht überschrieben werden kann, wird manchmal als *versiegeltes* Element bezeichnet.  
  
 Sie können `NotOverridable` nur in einer Deklarations Anweisung für eine Eigenschaft oder Prozedur verwenden. Sie können `NotOverridable` nur für eine Eigenschaft oder Prozedur angeben, die eine andere Eigenschaft oder Prozedur überschreibt, d. h. nur in Kombination mit `Overrides` .  
  
## <a name="combined-modifiers"></a>Kombinierte modifiziererer  

 Sie können `Overridable` oder `NotOverridable` für eine `Private` Methode nicht angeben.  
  
 Sie können nicht `NotOverridable` mit `MustOverride` , `Overridable` oder `Shared` in derselben Deklaration angeben.  
  
## <a name="usage"></a>Verwendung  

 Der `NotOverridable`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Function-Anweisung](../statements/function-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Sub-Anweisung](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Modifizierer](index.md)
- [Grundlagen der Vererbung](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](mustoverride.md)
- [Overrides](overridable.md)
- [Überschreibt](overrides.md)
- [Schlüsselwörter](../keywords/index.md)
- [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)

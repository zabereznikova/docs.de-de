---
title: Overrides
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
ms.openlocfilehash: 8506aba7e64f2dbd975cc275cefb7b5bb1aefda5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875008"
---
# <a name="overridable-visual-basic"></a>Overridable (Visual Basic)

Gibt an, dass eine Eigenschaft oder Prozedur durch eine identisch benannte Eigenschaft oder Prozedur in einer abgeleiteten Klasse überschrieben werden kann.  
  
## <a name="remarks"></a>Bemerkungen  

 Der- `Overridable` Modifizierer ermöglicht, dass eine Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse überschrieben wird. Der [nodeverridable](notoverridable.md) -Modifizierer verhindert, dass eine Eigenschaft oder Methode in einer abgeleiteten Klasse überschrieben wird.  Weitere Informationen finden Sie unter [Grundlagen der Vererbung](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Wenn der `Overridable` - `NotOverridable` Modifizierer oder der-Modifizierer nicht angegeben wird, ist die Standardeinstellung davon abhängig, ob die Eigenschaft oder Methode eine Basisklassen Eigenschaft oder-Methode überschreibt. Wenn die Eigenschaft oder Methode eine Basisklassen Eigenschaft oder-Methode überschreibt, ist die Standardeinstellung `Overridable` . andernfalls ist Sie `NotOverridable` .  
  
 Sie können einen Schatten oder überschreiben, um ein geerbtes Element neu zu definieren, aber es gibt bedeutende Unterschiede zwischen den beiden Ansätzen. Weitere Informationen finden Sie unter [shadowingin Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).  
  
 Ein Element, das überschrieben werden kann, wird manchmal als *Virtuelles* Element bezeichnet. Wenn Sie überschrieben werden kann, aber nicht sein muss, wird Sie manchmal auch als *konkretes* Element bezeichnet.  
  
 Sie können `Overridable` nur in einer Deklarations Anweisung für eine Eigenschaft oder Prozedur verwenden.  
  
## <a name="combined-modifiers"></a>Kombinierte modifiziererer  

 Sie können `Overridable` oder `NotOverridable` für eine `Private` Methode nicht angeben.  
  
 Sie können nicht `Overridable` mit `MustOverride` , `NotOverridable` oder `Shared` in derselben Deklaration angeben.  
  
 Da ein überschreibendes Element implizit überschreibbar ist, können Sie `Overridable` nicht mit `Overrides` kombinieren.  
  
## <a name="usage"></a>Verwendung  

 Der `Overridable`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Function-Anweisung](../statements/function-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Sub-Anweisung](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Modifizierer](index.md)
- [Grundlagen der Vererbung](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](mustoverride.md)
- [NotOverridable](notoverridable.md)
- [Überschreibt](overrides.md)
- [Schlüsselwörter](../keywords/index.md)
- [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)

---
title: Overridable (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f7d5dd33f8591be1b4305e954e55e035882626c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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

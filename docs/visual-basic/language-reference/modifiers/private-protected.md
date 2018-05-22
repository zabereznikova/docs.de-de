---
title: Private, Protected (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 23fd6583182a1fee544d0458dc3fc390aed86b9f
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="private-protected-visual-basic"></a>Private, Protected (Visual Basic)

Die Schlüsselwortkombination `Private Protected` ist ein Zugriffsmodifizierer für Member. Ein `Private Protected` angehört, zugegriffen werden kann, durch alle Elemente in der enthaltenden Klasse und von Typen, die von der enthaltenden Klasse abgeleitet, jedoch nur, wenn sie in der enthaltenden Assembly gefunden werden. 

Sie können angeben, `Private Protected` nur auf Member von Klassen; können nicht angewendet `Private Protected` zu Membern einer Struktur da Strukturen können nicht vererbt werden.

Die `Private Protected` Zugriffsmodifizierer wird von Visual Basic 15.5 und höher unterstützt. Um es zu verwenden, können Sie das folgende Element der Visual Basic-Projektdatei (*.vbproj) hinzufügen. Wie lange wie Visual Basic 15.5 oder höher auf Ihrem System installiert ist, können sie alle von der neuesten Version von Visual Basic-Compiler unterstützt Sprachfunktionen zu nutzen:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> Wählen Sie in Visual Studio F1-Hilfe auf `private protected` enthält die Hilfe für entweder [private](private.md) oder [geschützt](protected.md). Die IDE wählt der einzelnen Tokens, das unter den Cursor und nicht als zusammengesetztes Wort.

## <a name="rules"></a>Regeln

- **Deklarationskontext.** Sie können `Private Protected` nur auf Klassenebene. Dies bedeutet, dass der Deklarationskontext für eine `Protected` Element muss eine Klasse sein, und eine Quelldatei, Namespace, Schnittstelle, Modul, Struktur oder Prozedur nicht möglich.

## <a name="behavior"></a>Verhalten

- **Zugriffsebene.** Der gesamte Code in einer Klasse kann ihre Elemente zugreifen. Code in einer Klasse, die von einer Basisklasse abgeleitet ist und in derselben Assembly enthalten ist, kann auf alle zugreifen die `Private Protected` Elemente der Basisklasse. Jedoch nicht der Code in einer Klasse, die von einer Basisklasse abgeleitet ist und in einer anderen Assembly enthalten ist die Basisklasse der Klasse zugreifen `Private Protected` Elemente.

- **Zugriffsmodifizierer.** Die Schlüsselwörter, die Zugriffsebene angeben heißen *Zugriffsmodifizierer*. Einen Vergleich der Zugriffsmodifizierer, finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).
  
 Der `Private Protected`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md) einer geschachtelten Klasse  
  
 [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) eines Delegaten, die in einer Klasse geschachtelt sind  
  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md) von einer Eumeration, die in einer Klasse geschachtelt sind 
  
 [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md) einer Schnittstelle, die in einer Klasse geschachtelt sind 
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Struktur der Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md) einer Struktur geschachtelt werden, in einer Klasse 
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch

[Public](../../../visual-basic/language-reference/modifiers/public.md)  
[Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
["Friend"](friend.md)   
[Private](../../../visual-basic/language-reference/modifiers/private.md)  
[Protected Friend](./protected-friend.md)   
[Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)

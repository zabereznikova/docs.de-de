---
title: Private Protected
ms.date: 05/10/2018
f1_keywords:
- vb.PrivateProtected
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 8ad1509da71bc80b33700d363ddd4569a0965dff
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303464"
---
# <a name="private-protected-visual-basic"></a>Privat geschützt (Visual Basic)

Die Schlüsselwortkombination `Private Protected` ist ein Zugriffsmodifizierer für Member. Auf einen `Private Protected` Member kann von allen Membern in der enthaltenden Klasse sowie von Typen, die von der enthaltenden Klasse abgeleitet sind, zugegriffen werden. Dies ist jedoch nur möglich, wenn Sie in der enthaltenden Assembly gefunden werden.

Sie können `Private Protected` nur für Member von Klassen angeben. Sie können nicht auf Member einer Struktur anwenden, `Private Protected` da Strukturen nicht vererbt werden können.

Der `Private Protected` Zugriffsmodifizierer wird von Visual Basic 15,5 und höher unterstützt. Um es zu verwenden, können Sie das folgende-Element der Visual Basic Project- \* Datei (. vbproj) hinzufügen. Solange Visual Basic 15,5 oder höher auf Ihrem System installiert ist, können Sie alle sprach Features nutzen, die von der neuesten Version des Visual Basic Compilers unterstützt werden:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Weitere Informationen finden Sie [unter Festlegen der Visual Basic Sprachversion](../configure-language-version.md).

> [!NOTE]
> Wenn Sie in Visual Studio die F1-Hilfe in auswählen, `private protected` finden Sie Hilfe für [Privat](private.md) oder [geschützt](protected.md). Die IDE wählt anstelle des Verbund Worts das einzelne Token unter dem Cursor aus.

## <a name="rules"></a>Regeln

- **Deklarationskontext.** Sie können `Private Protected` nur auf Klassenebene verwenden. Dies bedeutet, dass der Deklarations Kontext für ein `Protected` -Element eine-Klasse sein muss und keine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Struktur oder eine Prozedur sein darf.

## <a name="behavior"></a>Verhalten

- **Zugriffsebene.** Der gesamte Code in einer Klasse kann auf seine Elemente zugreifen. Code in jeder Klasse, die von einer Basisklasse abgeleitet ist und in derselben Assembly enthalten ist, kann auf alle `Private Protected` Elemente der Basisklasse zugreifen. Allerdings kann der Code in jeder Klasse, die von einer Basisklasse abgeleitet ist und in einer anderen Assembly enthalten ist, nicht auf die Basisklassen `Private Protected` Elemente zugreifen.

- **Zugriffsmodifizierer** Die Schlüsselwörter für die Zugriffsebene werden als *Zugriffsmodifizierer*bezeichnet. Einen Vergleich der Zugriffsmodifizierer finden Sie unter [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

Der `Private Protected`-Modifizierer kann in folgenden Kontexten verwendet werden:

- [Class-Anweisung](../statements/class-statement.md) einer "netsted"-Klasse

- [Const-Anweisung](../statements/const-statement.md)

- [Declare Statement](../statements/declare-statement.md)

- [Delegatanweisung](../statements/delegate-statement.md) eines Delegaten, der in einer Klasse eingebettet ist

- [Dim-Anweisung](../statements/dim-statement.md)

- [Enumerationsanweisung](../statements/enum-statement.md) einer Enumeration, die in einer Klasse eingefügt ist

- [Event-Anweisung](../statements/event-statement.md)

- [Function-Anweisung](../statements/function-statement.md)

- [Interface-Anweisung](../statements/interface-statement.md) einer Schnittstelle, die in einer Klasse eingebettet ist

- [Property Statement](../statements/property-statement.md)

- [Structure-Anweisung](../statements/structure-statement.md) einer Struktur, die in einer Klasse eingebettet ist

- [Sub-Anweisung](../statements/sub-statement.md)

## <a name="see-also"></a>Weitere Informationen

- [Öffentlich](public.md)
- [Gebieten](protected.md)
- [Kollegen](friend.md)
- [Privat](private.md)
- [Protected Friend](./protected-friend.md)
- [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Vorgehensweisen](../../programming-guide/language-features/procedures/index.md)
- [Strukturen](../../programming-guide/language-features/data-types/structures.md)
- [Objekte und Klassen](../../programming-guide/language-features/objects-and-classes/index.md)

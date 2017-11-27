---
title: Automatische Verallgemeinerung (F#)
description: "Erfahren Sie, wie f# automatisch die Argumente und Funktionstypen verallgemeinert, damit sie mit verschiedenen möglichst zusammenarbeiten."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 14a3554c-3fad-4eba-a93d-8ba07d1245b4
ms.openlocfilehash: d60831084cef76ce29f64322362b4920520f71d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="automatic-generalization"></a>Automatische Verallgemeinerung

F# verwendet Typrückschluss die Arten von Funktionen und Ausdrücke auswerten. In diesem Thema wird beschrieben, wie f# automatisch die Argumente und Funktionstypen verallgemeinert, damit sie mit verschiedenen zusammenarbeiten, wenn dies möglich ist.


## <a name="automatic-generalization"></a>Automatische Verallgemeinerung
F#-Compiler, bestimmt Wenn sie den Typrückschluss für eine Funktion ausführt, ob es sich bei angegebenem Parameter generisch sein kann. Der Compiler überprüft jeden Parameter und bestimmt, ob die Funktion eine Abhängigkeit für den spezifischen Typ der Parameter verfügt. Wenn dies nicht der Fall ist, wird der Typ abgeleitet, generisch sein.

Das folgende Codebeispiel veranschaulicht eine Funktion, die der Compiler leitet um generisch sein.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

Der Typ wird davon ausgegangen werden `'a -> 'a -> 'a`.

Der Typ gibt an, dass dies eine Funktion akzeptiert zwei Argumente vom gleichen unbekannten Typ und gibt einen Wert desselben Typs zurück. Einer der Gründe, die der previous-Funktion kann generisch ist, das größer-als-Operator (`>`) generisch. Größer-als Operator hat eine Signatur `'a -> 'a -> bool`. Nicht alle Operatoren sind generisch, und wenn der Code in einer Funktion einen Parametertyp zusammen mit einer nicht generischen Funktion or -Operator verwendet, kann nicht, Parametertyp verallgemeinert werden.

Da `max` ist generisch, er kann verwendet werden mit Typen wie z. B. `int`, `float`usw., wie in den folgenden Beispielen gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

Allerdings müssen der zwei Argumente vom gleichen Typ sein. Die Signatur ist `'a -> 'a -> 'a`, nicht `'a -> 'b -> 'a`. Aus diesem Grund generiert der folgende Code einen Fehler, da die Datentypen nicht übereinstimmen.

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

Die `max` Funktion funktioniert auch mit jedem Typ, der größer unterstützt-als-Operator. Aus diesem Grund auch können er auf eine Zeichenfolge ist, Sie wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet104.fs)]
    
## <a name="value-restriction"></a>Wertebeschränkung
Der Compiler führt automatische Verallgemeinerung nur für vollständige Funktionsdefinitionen, die expliziten Argumente verfügen, und klicken Sie auf einfache unveränderliche Werte.

Dies bedeutet, dass der Compiler einen Fehler ausgibt, wenn Sie versuchen, den Code zu kompilieren, die nicht ausreichend für einen bestimmten Typ eingeschränkt ist, jedoch ist auch nicht generalisierbar. Die Fehlermeldung für dieses Problem bezieht sich auf diese Einschränkung auf automatische Verallgemeinerung für Werte als die *Wert Einschränkung*.

In der Regel tritt auf, der Wert Einschränkung Fehler, wenn ein Konstrukt generisch sein sollen, aber der Compiler hat nicht genügend Informationen, um ihn zu verallgemeinern oder wenn Sie unbeabsichtigt genügend Typinformationen in einem nicht generischen Konstrukt auslassen. Die Lösung mit dem Wert Einschränkung Fehler besteht darin, expliziter Anmeldeinformationen um Problem mithilfe eines Rückschlusses "Typ" in einem der folgenden Methoden ausführlicher zu beschränken:


- Beschränken eines Typs für nicht generische werden durch einen Wert oder einen Parameter eine expliziten typanmerkung hinzugefügt.

- Wenn das Problem ein Konstrukt verallgemeinerbaren definieren Sie eine generische Funktion, z. B. eine funktionskomposition verwenden oder nicht vollständig mit Currying Funktionsargumente angewendet wurde ist, versucht die Funktion wie die Definition einer gewöhnlichen Funktion schreiben.

- Wenn das Problem ein Ausdruck ist, der ist zu komplex werden generalisiert, stellen es in eine Funktion durch einen zusätzlichen, nicht verwendeten Parameter hinzufügen.

- Fügen Sie explizite generische Typparameter hinzu. Diese Option wird selten verwendet.

- Die folgenden Codebeispiele veranschaulichen jedes dieser Szenarien.

Fall 1: Zu komplexer Ausdruck. In diesem Beispiel wird die Liste `counter` erhebt auf `int option ref`, aber es ist nicht als einfache unveränderliche Wert definiert.

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

Fall 2: Verwenden eines Konstrukts verallgemeinerbaren eine generische Funktion definieren. In diesem Beispiel wird das Konstrukt verallgemeinerbaren, da hierbei partielle Anwendung von Funktionsargumenten.

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

Fall 3: Hinzufügen eines zusätzlichen, nicht verwendeten Parameters. Da dieser Ausdruck nicht einfach genug für Verallgemeinerung ist, gibt der Compiler den Wert Einschränkung Fehler an.

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

Fall 4: Hinzufügen von Typparametern.

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

Im letzten Fall wird der Wert einer Typfunktion, die verwendet werden können, um Werte verschiedener Typen, z. B. wie folgt erstellen:

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a>Siehe auch
[Typableitung](../type-inference.md)

[Generika](index.md)

[Statisch aufgelöste Typparameter](statically-resolved-type-parameters.md)

[Einschränkungen](constraints.md)


---
title: Neues in F# 4,7- F# Guide
description: Verschaffen Sie sich einen Überblick über die neuen Features F# , die in 4,7 verfügbar sind.
ms.date: 11/27/2019
ms.openlocfilehash: 203b258466cb9f1f50215ecf8884e92e7e86416b
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74644121"
---
# <a name="whats-new-in-f-47"></a>Neuerungen in F# 4,7

F#4,7 fügt der F# Sprache mehrere Verbesserungen hinzu.

## <a name="get-started"></a>Erste Schritte

F#4,7 ist in allen .net Core-Distributionen und Visual Studio-Tools verfügbar. [Beginnen Sie mit F# ](../get-started/index.md) den ersten Schritten, um mehr zu erfahren.

## <a name="language-version"></a>Sprachversion

Der F# 4,7-Compiler führt die Möglichkeit ein, ihre effektive Sprachversion über eine Eigenschaft in der Projektdatei festzulegen:

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

Sie können Sie auf die Werte `4.6`, `4.7`, `latest`und `preview`festlegen. Der Standardwert ist `latest`.

Wenn Sie `preview`festlegen, aktiviert der Compiler alle F# Vorschau Features, die in Ihrem Compiler implementiert werden.

## <a name="implicit-yields"></a>Implizite Ergebnisse

Sie müssen das `yield`-Schlüsselwort nicht mehr in Arrays, Listen, Sequenzen oder Berechnungs Ausdrücken anwenden, in denen der Typ abgeleitet werden kann. Im folgenden Beispiel benötigen beide Ausdrücke die `yield`-Anweisung für jeden Eintrag vor F# 4,7:

```fsharp
let s = seq { 1; 2; 3; 4; 5 }

let daysOfWeek includeWeekend =
    [ 
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then 
            "Saturday"
            "Sunday"
    ] 
```

Wenn Sie ein einzelnes `yield`-Schlüsselwort einführen, muss für jedes andere Element ebenfalls `yield` angewendet werden.

Implizite Ergebnisse werden nicht aktiviert, wenn Sie in einem Ausdruck verwendet werden, der auch `yield!` verwendet, um eine Sequenz zu vereinfachen. In diesen Fällen müssen Sie `yield` noch heute verwenden.

## <a name="wildcard-identifiers"></a>Platzhalter Bezeichner

In F# Code, der Klassen einschließt, muss der Self-Identifier in Element Deklarationen immer explizit sein. In Fällen, in denen der selbst Bezeichner niemals verwendet wird, war es jedoch üblich, einen doppelten unterstrich zu verwenden, um einen namenlosen Self-Identifier anzugeben. Sie können nun einen einzelnen Unterstrich verwenden:

```fsharp
type C() =
    member _.M() = ()
```

Dies gilt auch für `for` Schleifen:

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a>Einrückungen

Vor F# 4,7 erforderten die Einzugs Anforderungen für primäre Konstruktoren und statische Member-Argumente einen übermäßigen Einzug. Sie benötigen jetzt nur einen einzelnen Einzugsbereich:

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```

---
title: Neuerungen in F- 4.7 - F-Leitfaden
description: Verschaffen Sie sich einen Überblick über die neuen Funktionen, die in F- 4.7 verfügbar sind.
ms.date: 11/27/2019
ms.openlocfilehash: 7a6e744a398719bcb55d168dd700459e0b122dd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185875"
---
# <a name="whats-new-in-f-47"></a>Neuerungen in F- 4.7

F-4.7 fügt der Sprache F- 4.7 mehrere Verbesserungen hinzu.

## <a name="get-started"></a>Erste Schritte

Die F-4.7 ist in allen .NET Core-Verteilungen und Visual Studio-Tools verfügbar. [Beginnen Sie mit f',](../get-started/index.md) um mehr zu erfahren.

## <a name="language-version"></a>Sprachversion

Der Compiler "F- 4.7" bietet die Möglichkeit, Ihre effektive Sprachversion über eine Eigenschaft in der Projektdatei festzulegen:

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

Sie können sie auf `4.6` `4.7`die `latest`Werte `preview`, , und festlegen. Der Standardwert lautet `latest`.

Wenn Sie es `preview`auf festlegen, aktiviert der Compiler alle F-Vorschaufeatures, die in Ihrem Compiler implementiert sind.

## <a name="implicit-yields"></a>Implizite Erträge

Sie müssen das `yield` Schlüsselwort nicht mehr in Arrays, Listen, Sequenzen oder Berechnungsausdrücken anwenden, aus denen der Typ abgeleitet werden kann. Im folgenden Beispiel erforderten `yield` beide Ausdrücke die Anweisung für jeden Eintrag vor F.4.7:

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

Wenn Sie ein `yield` einzelnes Schlüsselwort einführen, muss auch jedes andere Element darauf angewendet haben. `yield`

Implizite Erträge werden nicht aktiviert, wenn `yield!` sie in einem Ausdruck verwendet werden, der auch verwendet wird, um so etwas wie eine Sequenz abzuflachen. In diesen Fällen `yield` müssen Sie auch heute noch verwenden.

## <a name="wildcard-identifiers"></a>Platzhalterbezeichner

In F-Code, der Klassen enthält, muss die Selbstbezeichnerin immer explizit in Memberdeklarationen sein. Aber in Fällen, in denen die Selbstbezeichnernie nie verwendet wird, ist es traditionell eine Konvention, einen Doppelunterstrich zu verwenden, um eine namenlose Selbstkennung anzugeben. Sie können jetzt einen einzelnen Unterstrich verwenden:

```fsharp
type C() =
    member _.M() = ()
```

Dies gilt `for` auch für Schleifen:

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a>Einzugsentspannungen

Vor F-4.7 erforderten die Einzugsanforderungen für primäre Konstruktor- und statische Memberargumente einen übermäßigen Einzug. Sie benötigen jetzt nur noch einen einzigen Einzugsbereich:

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```

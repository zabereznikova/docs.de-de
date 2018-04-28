---
title: Abstrakte Klassen (F#)
description: Erfahren Sie mehr über f# abstrakte Klassen, die einige oder alle Member, die nicht implementiert lassen und allgemeine Funktionen, die einen unterschiedlichen Satz von Objekttypen darzustellen.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 0d7ca996de89c44a5cfb9197c1b515741a2303df
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="abstract-classes"></a>Abstrakte Klassen

*Abstrakte Klassen* sind Klassen, die einige oder alle Member, die nicht implementiert ist, lassen, damit Implementierungen von abgeleiteten Klassen bereitgestellt werden können.

## <a name="syntax"></a>Syntax

```fsharp
// Abstract class syntax.
[<AbstractClass>]
type [ accessibility-modifier ] abstract-class-name =
[ inherit base-class-or-interface-name ]
[ abstract-member-declarations-and-member-definitions ]

// Abstract member syntax.
abstract member member-name : type-signature
```

## <a name="remarks"></a>Hinweise
In einer objektorientierten Programmierung ist eine abstrakte Klasse dient als Basisklasse einer Hierarchie und stellt allgemeine Funktionen, die einen unterschiedlichen Satz von Objekttypen. Wie "Abstract" der Name schon sagt, entsprechen abstrakte Klassen häufig nicht direkt auf konkrete Entitäten in der Problemdomäne. Sie stellen jedoch dar, was viele unterschiedliche konkrete Entitäten gemeinsam haben.

Abstrakte Klassen benötigen die `AbstractClass` Attribut. Sie können implementiert und nicht implementierte Member haben. Die Verwendung des Begriffs *abstrakte* bei Anwendung auf eine Klasse ist dasselbe wie bei anderen; allerdings die Verwendung des Begriffs *abstrakte* bei Anwendung auf Methoden (und Eigenschaften) ist ein wenig anders in f# aus seiner in anderen .NET-Sprachen verwenden. In F# erläutert werden, wenn eine Methode mit gekennzeichnet ist die `abstract` -Schlüsselwort, dies gibt an, dass ein Member einen Eintrag, der sogenannten verfügt eine *virtuellen Dispatch-Slot*, in der internen Tabelle virtueller Funktionen für diesen Typ. Anders ausgedrückt, ist die Methode virtuell ist, obwohl die `virtual` Schlüsselwort wird nicht in der Sprache f# verwendet. Das Schlüsselwort `abstract` dient für virtuelle Methoden unabhängig davon, ob die Methode implementiert wird. Die Deklaration einer virtuellen Dispatch-Slots ist getrennt von der Definition einer Methode für diesen Dispatchslot. Aus diesem Grund f# eine virtuelle Methodendeklaration und Definition in einer anderen .NET-Sprache entspricht eine Kombination von einer abstrakten Methodendeklaration und eine separate Definition, entweder mit der `default` Schlüsselwort oder der `override` Schlüsselwort. Weitere Informationen und Beispiele finden Sie unter [Methoden](members/methods.md).

Eine Klasse gilt als abstrakte nur, wenn es sind abstrakte Methoden, die deklariert, aber nicht definiert. Daher sind Klassen, die abstrakte Methoden verfügen über nicht zwangsläufig abstrakte Klassen. Es sei denn, eine Klasse abstrakte Methoden nicht definiert wurde, verwenden Sie nicht die **AbstractClass** Attribut.

In der vorherigen Syntax *Zugriffsmodifizierer* kann `public`, `private` oder `internal`. Weitere Informationen finden Sie unter [Zugriffssteuerung](access-control.md).

Wie bei anderen Arten können abstrakte Klassen eine Basisklasse und eine oder mehrere Basisschnittstellen haben. Jede Basisklasse oder Schnittstelle wird angezeigt, in einer separaten Zeile zusammen mit dem `inherit` Schlüsselwort.

Die Typdefinition einer abstrakten Klasse kann vollständig definierte Elemente enthalten, aber es kann auch abstrakte Member enthalten. Die Syntax für abstrakte Member wird in der vorherigen Syntax separat angezeigt. In dieser Syntax der *Typsignatur* eines Members ist eine Liste mit den Parametertypen in der Reihenfolge und die Rückgabetypen, getrennt durch `->` Token und/oder `*` Token nach Bedarf, um Curry und Tupel Parameter. Die Syntax für Typsignaturen abstrakten Member ist identisch mit, die in der Signatur verwendet und, die von IntelliSense in Visual Studio Code Editor angezeigt.

Das folgende Codebeispiel veranschaulicht eine abstrakte Klasse Form, die zwei nicht abstrakte abgeleitete Klassen, Square und Kreis hat. Im Beispiel wird gezeigt, wie abstrakte Klassen, Methoden und Eigenschaften verwendet wird. Im Beispiel stellt die abstrakte Klasse Form die gemeinsamen Elemente von den konkreten Entitäten Kreis oder ein Quadrat. Die allgemeinen Funktionen aller Formen (in einem zweidimensionalen Koordinatensystem) werden in der Form "-Klasse abstrahiert: die Position im Raster, einen Drehwinkel um sowie die Bereichs- und Umkreis-Eigenschaften. Diese können, mit Ausnahme der Position, die das Verhalten außer Kraft gesetzt werden der einzelne Formen ändern können.

Die Drehungsmethode kann überschrieben werden, wie die Kreis-Klasse, die Drehung invariante aufgrund ihrer Symmetrie ist. Daher wird in die Kreis-Klasse, die Drehungsmethode mit einer anderen Methode ersetzt, die keine Aktionen ausführt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

**Ausgabe:**

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a>Siehe auch
[Klassen](classes.md)

[Mitglieder](members/index.md)

[Methoden](members/methods.md)

[Eigenschaften](members/Properties.md)

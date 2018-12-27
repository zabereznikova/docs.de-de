---
title: Abstrakte Klassen
description: Erfahren Sie mehr über F# abstrakte Klassen, die einige oder alle Member nicht implementiert lassen, und stellen allgemeine Funktionen einem unterschiedlichen Satz von Objekttypen dar.
ms.date: 05/16/2016
ms.openlocfilehash: fecd3b2d550c6b8f59fa614f5d00c5f730a4896a
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613478"
---
# <a name="abstract-classes"></a>Abstrakte Klassen

*Abstrakte Klassen* sind Klassen, die einige oder alle Member nicht implementiert lassen, sodass Implementierungen von abgeleiteten Klassen bereitgestellt werden können.

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

In der objektorientierten Programmierung eine abstrakte Klasse dient als Basisklasse einer Hierarchie und einen unterschiedlichen Satz von Objekttypen häufig verwendeten Funktionen darstellt. Wie "abstrakt" der Name schon sagt, entsprechen abstrakte Klassen häufig nicht direkt auf konkrete Entitäten in der Problemdomäne. Allerdings bedeuten sie, wie viele unterschiedliche konkrete Entitäten Gemeinsamkeit aufweisen.

Abstrakte Klassen müssen die `AbstractClass` Attribut. Sie können implementiert und nicht die Member implementiert haben. Die Verwendung des Begriffs *abstrakte* bei Anwendung auf eine Klasse ist der gleiche wie in anderen, jedoch die Verwendung des Begriffs *abstrakte* bei Anwendung auf Methoden (und Eigenschaften) ist ein wenig anders in F# von der Verwenden Sie in anderen .NET-Sprachen. In F#, wenn eine Methode gekennzeichnet ist, mit der `abstract` -Schlüsselwort, dies gibt an, dass ein Element auf einen Eintrag, bekannt als hat eine *virtueller Dispatch-Slot*, in die interne Tabelle der virtuellen Funktionen für diesen Typ. Das heißt, die Methode virtuell ist, obwohl die `virtual` -Schlüsselwort nicht in der Sprache F# verwendet. Das Schlüsselwort `abstract` wird verwendet, auf die virtuellen Methoden, unabhängig davon, ob die Methode implementiert wird. Die Deklaration ein virtueller Dispatch-Slot unterscheidet sich von der Definition einer Methode für diesen Slot verteilen. Aus diesem Grund F# eine virtuelle Methodendeklaration und Definition in einer anderen .NET-Sprache, entspricht einer Kombination aus einer abstrakten Methodendeklaration und eine separate Definition, entweder mit der `default` Schlüsselwort oder `override` Schlüsselwort. Weitere Informationen und Beispiele finden Sie unter [Methoden](members/methods.md).

Eine Klasse gilt als abstrakte nur, wenn es sind abstrakte Methoden, die deklariert, aber nicht definiert. Aus diesem Grund sind Klassen, die abstrakte Methoden verfügen über nicht zwangsläufig abstrakte Klassen. Es sei denn, eine Klasse, nicht die abstrakte Methoden definiert wurde, verwenden Sie nicht die **AbstractClass** Attribut.

In der vorherigen Syntax *Zugriffsmodifizierer* kann `public`, `private` oder `internal`. Weitere Informationen finden Sie unter [Zugriffssteuerung](access-control.md).

Wie bei anderen Typen können abstrakte Klassen eine Basisklasse und einer oder mehrere Basisschnittstellen haben. Jede Basisklasse oder Schnittstelle wird angezeigt, in einer separaten Zeile zusammen mit den `inherit` Schlüsselwort.

Die Typendefinition einer abstrakten Klasse kann vollständig definierte Elemente enthalten, aber sie können auch abstrakte Member enthalten. Die Syntax für die abstrakten Member wird separat in der vorherigen Syntax angezeigt. In dieser Syntax der *Typsignatur* eines Elements wird eine Liste mit den Parametertypen in der Reihenfolge und die Rückgabetypen, getrennt durch `->` Token und/oder `*` Token nach Bedarf, um Curry und Tupel-Funktionswerts Parameter. Die Syntax für Typsignaturen abstrakten Member ist identisch mit, dass in der Signatur verwendet und dass die von IntelliSense in Visual Studio Code-Editor angezeigt.

Der folgende Code veranschaulicht eine abstrakte Klasse Shape, das zwei nicht abstrakte abgeleitete Klassen, Quadrat und den Kreis ist. Das Beispiel zeigt, wie Sie abstrakte Klassen, Methoden und Eigenschaften verwenden. Im Beispiel stellt die abstrakte Klasse Form der gemeinsame Elemente der konkreten Entitäten Kreis und Quadrat dar. Die gemeinsamen Funktionen aller Formen (in einem zweidimensionalen Koordinatensystem) werden in der Shape-Klasse abstrahiert: die Position im Raster und einen Drehwinkel um die Fläche und Umfang-Eigenschaften. Diese können mit Ausnahme der Position, die das Verhalten überschrieben werden, von denen nicht einzelne Formen ändern können.

Die Drehungsmethode kann überschrieben werden, wie in der Kreis-Klasse, die Drehung invariante aufgrund ihrer Symmetrie ist. Daher wird in der Kreis-Klasse, die Drehungsmethode mit einer anderen Methode ersetzt, die keine Aktionen ausführt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

**Ausgabe:**

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a>Siehe auch

- [Klassen](classes.md)
- [Mitglieder](members/index.md)
- [Methoden](members/methods.md)
- [Eigenschaften](members/Properties.md)
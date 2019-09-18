---
title: Abstrakte Klassen
description: Erfahren Sie F# mehr über abstrakte Klassen, bei denen einige oder alle Member nicht implementiert werden und allgemeine Funktionen eines unterschiedlichen Satzes von Objekttypen darstellen.
ms.date: 05/16/2016
ms.openlocfilehash: d7fc87178cff7c5c824992c97198b49f87025f00
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71082950"
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

Bei der objektorientierten Programmierung wird eine abstrakte Klasse als Basisklasse einer Hierarchie verwendet und stellt die allgemeine Funktionalität eines unterschiedlichen Satzes von Objekttypen dar. Wie der Name "abstract" impliziert, Stimmen abstrakte Klassen häufig nicht direkt auf konkrete Entitäten in der Problemdomäne überein. Sie stellen jedoch dar, welche zahlreichen unterschiedlichen konkreten Entitäten gemeinsam sind.

Abstrakte Klassen müssen über das `AbstractClass` -Attribut verfügen. Sie können über implementierte und nicht implementierte Member verfügen. Die Verwendung des Begriffs *abstrakte* bei Anwendung auf eine Klasse ist der gleiche wie in anderen, jedoch die Verwendung des Begriffs *abstrakte* bei Anwendung auf Methoden (und Eigenschaften) ist ein wenig anders in F# von der Verwenden Sie in anderen .NET-Sprachen. Wenn F#eine Methode in mit dem `abstract` -Schlüsselwort markiert ist, weist dies darauf hin, dass ein Member einen Eintrag, der als *virtueller dispatchslot*bezeichnet wird, in der internen Tabelle der virtuellen Funktionen für diesen Typ enthält. Das heißt, die Methode virtuell ist, obwohl die `virtual` -Schlüsselwort nicht in der Sprache F# verwendet. Das- `abstract` Schlüsselwort wird für virtuelle Methoden verwendet, unabhängig davon, ob die Methode implementiert ist. Die Deklaration eines virtuellen dispatchslots ist von der Definition einer Methode für diesen dispatchslot getrennt. Aus diesem Grund F# eine virtuelle Methodendeklaration und Definition in einer anderen .NET-Sprache, entspricht einer Kombination aus einer abstrakten Methodendeklaration und eine separate Definition, entweder mit der `default` Schlüsselwort oder `override` Schlüsselwort. Weitere Informationen und Beispiele finden Sie unter [Methoden](./members/methods.md).

Eine Klasse gilt nur als abstrakt, wenn abstrakte Methoden deklariert sind, aber nicht definiert sind. Daher sind Klassen, die abstrakte Methoden haben, nicht notwendigerweise abstrakte Klassen. Verwenden Sie nicht das **abstractclass** -Attribut, es sei denn, eine Klasse hat nicht definierte abstrakte Methoden.

In der vorherigen Syntax kann `public`der Zugriffsmodifizierer `internal`, `private` oder sein. Weitere Informationen finden Sie unter [Zugriffssteuerung](access-control.md).

Wie bei anderen Typen können abstrakte Klassen über eine Basisklasse und eine oder mehrere Basis Schnittstellen verfügen. Jede Basisklasse oder Schnittstelle wird in einer separaten Zeile mit dem `inherit` -Schlüsselwort angezeigt.

Die Typdefinition einer abstrakten Klasse kann vollständig definierte Member enthalten, kann aber auch abstrakte Member enthalten. Die Syntax für abstrakte Member wird separat in der vorherigen Syntax angezeigt. In dieser Syntax ist die *Typsignatur* eines Members eine Liste, die die Parametertypen in der Reihenfolge und die Rückgabe Typen enthält, getrennt `->` durch Token und/ `*` oder Token, je nach Bedarf für currried-und Tupel-Parameter. Die Syntax für die Signaturen abstrakter Member ist identisch mit der Syntax, die in Signatur Dateien verwendet wird und die von IntelliSense im Visual Studio Code-Editor angezeigt wird.

Der folgende Code veranschaulicht eine abstrakte Klassen Form, die zwei nicht abstrakte abgeleitete Klassen hat, Square und Circle. Das Beispiel zeigt, wie abstrakte Klassen, Methoden und Eigenschaften verwendet werden. Im Beispiel stellt die Form abstrakte Klasse die allgemeinen Elemente der konkreten Entitäten Circle und Square dar. Die allgemeinen Funktionen aller Formen (in einem zweidimensionalen Koordinatensystem) werden in die Shape-Klasse abstrahiert: die Position im Raster, ein Drehungs Winkel und die Bereichs-und Umkreis Eigenschaften. Diese können außer der Position überschrieben werden, das Verhalten, mit dem sich einzelne Formen nicht ändern können.

Die Rotations Methode kann überschrieben werden, wie in der Circle-Klasse, bei der es sich um eine Drehung aufgrund ihrer Symmetrie handelt. Daher wird die Rotations Methode in der Klasse "Circle" durch eine Methode ersetzt, die nichts bewirkt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

**Ausgabe:**

```console
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a>Siehe auch

- [Klassen](classes.md)
- [Mitglieder](./members/index.md)
- [Methoden](./members/methods.md)
- [Eigenschaften](./members/Properties.md)

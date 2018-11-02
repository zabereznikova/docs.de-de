---
title: Zugriffssteuerung (F#)
description: Informationen Sie zum Steuern des Zugriffs auf Programmierelemente wie Typen, Methoden und Funktionen, die in der Programmiersprache f#.
ms.date: 05/16/2016
ms.openlocfilehash: 66a260d326acf07391e3775e5a7853654b4feee4
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "43803973"
---
# <a name="access-control"></a>Zugriffssteuerung

*Steuerung des Zugriffs* bezieht sich auf die deklarieren, welche Clients bestimmte Programmelemente, z. B. Typen, Methoden und Funktionen verwenden können.

## <a name="basics-of-access-control"></a>Grundlagen der Zugriffssteuerung

In f#, Steuern der Zugriff Spezifizierer `public`, `internal`, und `private` kann auf Module, Typen, Methoden, wertedefinitionen, Funktionen, Eigenschaften und explizite Felder angewendet werden.

- `public` Gibt an, dass die Entität, die von allen Aufrufern zugegriffen werden kann.

- `internal` Gibt an, dass die Entität, die nur von der gleichen Assembly zugegriffen werden kann.

- `private` Gibt an, dass die Entität nur aus dem einschließenden Typ oder Modul zugegriffen werden kann.

>[!NOTE]
Der Zugriffsspezifizierer `protected` wird nicht in f# verwendet, obwohl es akzeptabel ist, bei Verwendung von Typen, die in Sprachen, unterstützen erstellte `protected` Zugriff. Wenn Sie eine geschützte Methode überschreiben, bleibt die Methode aus diesem Grund nur innerhalb der Klasse und ihrer untergeordneten Klassen zugegriffen werden kann.

Der Bezeichner wird in der Regel vor dem Namen der Entität, außer wenn versetzt einen `mutable` oder `inline` Bezeichner verwendet wird, die nach dem Zugriffsspezifizierer-Steuerelement angezeigt werden.

Wenn keine Zugriffsspezifizierer verwendet wird, wird der Standardwert ist `public`, mit Ausnahme von `let` Bindungen in einem Typ, der immer `private` in den Typ.

Signaturen in F#-Geben Sie einen anderen Mechanismus zur Steuerung des Zugriffs auf Programmelemente in f#. Signaturen sind nicht erforderlich, für die Zugriffssteuerung. Weitere Informationen finden Sie unter [Signaturen](signatures.md).

## <a name="rules-for-access-control"></a>Regeln für die Zugriffssteuerung

Die Zugriffssteuerung ist gemäß den folgenden Regeln:

- , Vererbungsdeklarationen (, also die Verwendung von `inherit` auf eine Basisklasse für eine Klasse angeben), Schnittstellendeklarationen (das ist, gibt an, dass eine Klasse eine Schnittstelle implementiert) und abstrakten Member verfügen immer über den gleichen Zugriff wie der einschließende Typ. Aus diesem Grund kann ein Steuerelement-Zugriffsspezifizierer auf diese Konstrukte verwendet werden.

- Zugriff auf einzelne Fälle, in eine Unterscheidungs-Union wird durch den Zugriff auf die Unterscheidungs-Union selbst bestimmt. Ein bestimmter union-Fall ist, also nicht weniger zugreifbar als die Union selbst.

- Barrierefreiheit für einzelne Felder eines Datensatztyps nicht möglich, der durch den Zugriff auf den Datensatz selbst bestimmt wird. Eine Bezeichnung bestimmten Datensatz ist, also nicht kleiner als der Datensatz selbst zugegriffen werden kann.

## <a name="example"></a>Beispiel

Der folgende Code veranschaulicht die Verwendung von Steuerelement-Zugriffsspezifizierer. Es gibt zwei Dateien im Projekt `Module1.fs` und `Module2.fs`. Jede Datei ist implizit ein Modul. Aus diesem Grund sind die beiden Module, `Module1` und `Module2`. Ein privater Typ und einen internen Typ sind in definiert `Module1`. Der private Typ kann nicht zugegriffen werden, von `Module2`, aber Sie können der interne Typ.

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]

Der folgende Code überprüft den Zugriff auf die Typen, die im erstellten `Module1.fs`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Signaturen](signatures.md)

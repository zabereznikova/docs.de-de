---
description: In diesem Artikel werden die impliziten und expliziten Konvertierungen zwischen den integrierten numerischen Typen in C# erläutert.
title: Integrierte numerische Konvertierungen – C#-Referenz
ms.date: 10/22/2019
helpviewer_keywords:
- implicit numeric conversions [C#]
- explicit numeric conversion [C#]
- numeric conversions [C#], implicit
- numeric conversions [C#], explicit
- conversions [C#], implicit numeric
- conversions [C#], explicit numeric
ms.openlocfilehash: ee5def3b5e0e067919a8c8335db701dbb6dd4d88
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142244"
---
# <a name="built-in-numeric-conversions-c-reference"></a>Integrierte numerische Konvertierungen (C#-Referenz)

C# bietet eine Reihe von [integralen numerischen Typen](integral-numeric-types.md) und [numerischen Gleitkommatypen](floating-point-numeric-types.md). Es gibt eine Konvertierung zwischen zwei beliebigen numerischen Typen, entweder implizit oder explizit. Sie müssen einen [Cast-Ausdruck](../operators/type-testing-and-cast.md#cast-expression) verwenden, um eine explizite Konvertierung durchzuführen.

## <a name="implicit-numeric-conversions"></a>Implizite numerische Konvertierungen

Folgende Tabelle veranschaulicht vordefinierte implizite Konvertierungen zwischen integrierten numerischen Typen:

|Von|Beschreibung|
|----------|--------|
|[sbyte](integral-numeric-types.md)|`short`, `int`, `long`, `float`, `double` oder `decimal`|
|[byte](integral-numeric-types.md)|`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`|
|[short](integral-numeric-types.md)|`int`, `long`, `float`, `double` oder `decimal`|
|[ushort](integral-numeric-types.md)|`int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`|
|[int](integral-numeric-types.md)|`long`, `float`, `double` oder `decimal`|
|[uint](integral-numeric-types.md)|`long`, `ulong`, `float`, `double` oder `decimal`|
|[long](integral-numeric-types.md)|`float`, `double`oder `decimal`|
|[ulong](integral-numeric-types.md)|`float`, `double`oder `decimal`|
|[float](floating-point-numeric-types.md)|`double`|

> [!NOTE]
> Die impliziten Konvertierungen von `int`, `uint`, `long` oder `ulong` in `float` und von `long` oder `ulong` in `double` können zu einem Verlust an Genauigkeit führen, aber nie zu einem Verlust in einer Größenordnung. Die anderen impliziten numerischen Konvertierungen verlieren nie Informationen.

Beachten Sie außerdem:

- Jeder [integrale numerische Typ](integral-numeric-types.md) ist implizit in jeden [numerischen Gleitkommatypen](floating-point-numeric-types.md) konvertierbar.

- Es gibt keine impliziten Konvertierungen in die Typen `byte` und `sbyte`. Es gibt keine impliziten Konvertierungen aus den Typen `double` und `decimal`.

- Es gibt keine impliziten Konvertierungen zwischen dem Typ `decimal` und dem Typ `float` oder `double`.

- Ein Wert eines konstanten Ausdrucks vom Typ `int` (z. B. ein Wert, der durch ein ganzzahliges Literal dargestellt wird), kann implizit in `sbyte`, `byte`, `short`, `ushort`, `uint` oder `ulong` konvertiert werden, wenn er sich im Bereich des Zieltyps befindet:

  ```csharp
  byte a = 13;
  byte b = 300;  // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

  Wie das vorherige Beispiel zeigt, tritt der Compilerfehler [CS0031](../../misc/cs0031.md) auf, wenn der konstante Wert nicht innerhalb des Bereichs des Zieltyps liegt.

## <a name="explicit-numeric-conversions"></a>Explizite numerische Konvertierungen

Folgende Tabelle veranschaulicht vordefinierte explizite Konvertierungen zwischen integrierten numerischen Typen, für die es keine [implizite Konvertierung](#implicit-numeric-conversions) gibt:

|Von|Beschreibung|
|----------|--------|
|[sbyte](integral-numeric-types.md)|`byte`, `ushort`, `uint` oder `ulong`|
|[byte](integral-numeric-types.md)|`sbyte`|
|[short](integral-numeric-types.md)|`sbyte`, `byte`, `ushort`, `uint` oder `ulong`|
|[ushort](integral-numeric-types.md)|`sbyte`, `byte`oder `short`|
|[int](integral-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `uint` oder `ulong`|
|[uint](integral-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort` oder `int`|
|[long](integral-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint` oder `ulong`|
|[ulong](integral-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint` oder `long`|
|[float](floating-point-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong` oder `decimal`|
|[double](floating-point-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float` oder `decimal`|
|[decimal](floating-point-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float` oder `double`|

> [!NOTE]
> Eine explizite numerische Konvertierung kann zu Datenverlust führen oder eine Ausnahme auslösen, typischerweise ein <xref:System.OverflowException>.

Beachten Sie außerdem:

- Wenn Sie einen Wert von einem integralen Typ in einen anderen integralen Typ konvertieren, ist das Ergebnis vom [Kontext der Überlaufprüfung](../keywords/checked-and-unchecked.md) abhängig. Die Konvertierung in einem geprüften Kontext ist erfolgreich, wenn der Quellwert sich innerhalb des Bereichs des Zieltyps befindet. Andernfalls wird eine <xref:System.OverflowException> ausgelöst. In einem ungeprüften Kontext ist die Konvertierung immer erfolgreich, und sie verläuft wie folgt:

  - Wenn der Quelltyp größer als der Zieltyp ist, wird der Quellwert abgeschnitten, indem die wichtigsten „zusätzlichen“ Teile verworfen werden. Das Ergebnis wird dann als Wert des Zieltyps behandelt.

  - Wenn der Quelltyp kleiner als der Zieltyp ist, ist der Quellwert entweder signaturerweitert oder mit Null erweitert, sodass er die gleiche Größe wie der Zieltyp hat. Die Vorzeichenerweiterung wird verwendet, wenn der Quelltyp mit einem Vorzeichen versehen ist. Die Erweiterung mit Nullen (0) wird verwendet, wenn der Quelltyp mit keinem Vorzeichen versehen ist. Das Ergebnis wird dann als Wert des Zieltyps behandelt.

  - Wenn der Quelltyp die gleiche Größe wie der Zieltyp aufweist, wird der Quellwert als Wert vom Zieltyp behandelt.

- Wenn Sie einen `decimal`-Wert in einen integralen Typ konvertieren, wird dieser Wert Richtung 0 (null) auf den nächsten Integralwert gerundet. Wenn der erzeugte Integralwert sich außerhalb des Bereichs des Zieltyps befindet, wird eine <xref:System.OverflowException> ausgelöst.

- Wenn Sie einen `double`- oder`float`-Wert in einen integralen Typ konvertieren, wird dieser Wert Richtung 0 (null) auf den nächsten Integralwert gerundet. Wenn der resultierende Integralwert sich außerhalb des Bereichs des Zieltyps befindet, hängt das Ergebnis vom [Kontext der Überlaufprüfung](../keywords/checked-and-unchecked.md) ab. In einem geprüften Kontext wird eine <xref:System.OverflowException> ausgelöst, während das Ergebnis in einem ungeprüften Kontext ein nicht angegebener Wert des Zieltyps ist.

- Wenn Sie `double` in `float` konvertieren, wird der `double`-Wert auf den nächsten `float`-Wert gerundet. Wenn der `double`-Wert zu klein oder zu groß ist, um in den `float`-Typ zu passen, ist das Ergebnis 0 (null) oder unendlich.

- Wenn Sie `float` oder `double` in `decimal` konvertieren, wird der Quellwert in eine `decimal`-Darstellung konvertiert und bei Bedarf auf die nächste Zahl nach der achtundzwanzigsten Dezimalstelle gerundet. Je nach Wert des Quellwerts kann eines der folgenden Ergebnisse auftreten:

  - Wenn der Quellwert zu klein ist, als dass er als `decimal` dargestellt werden könnte, ist das Ergebnis 0 (null).

  - Wenn der Quellwert NaN (nicht numerisch), unendlich oder zu groß ist, um als `decimal` dargestellt zu werden, wird eine <xref:System.OverflowException> ausgelöst.

- Wenn Sie `decimal` in `float` oder `double` konvertieren, wird der Quellwert in den nächsten `float`- oder `double`-Wert konvertiert.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):

- [Implizite numerische Konvertierungen](~/_csharplang/spec/conversions.md#implicit-numeric-conversions)
- [Explizite numerische Konvertierungen](~/_csharplang/spec/conversions.md#explicit-numeric-conversions)

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [Umwandlung und Typkonvertierungen](../../programming-guide/types/casting-and-type-conversions.md)

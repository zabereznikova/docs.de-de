---
title: Date-Datentyp
ms.date: 07/20/2015
f1_keywords:
- vb.Date
helpviewer_keywords:
- Date data type
- dates [Visual Basic], Visual Basic data types
- times [Visual Basic], Date data type
- Date literals [Visual Basic]
- data values [Visual Basic]
- times [Visual Basic], Visual Basic data types
- dates [Visual Basic], Date data type
- data types [Visual Basic], assigning
- literals [Visual Basic], Date
- '# specifier for Date literals'
ms.assetid: d9edf5b0-e85e-438b-a1cf-1f321e7c831b
ms.openlocfilehash: 972df72874753a0f1213f3a4942468c59e3913ce
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344025"
---
# <a name="date-data-type-visual-basic"></a>Date-Datentyp (Visual Basic)

Enthält IEEE-64-Bit(8-Byte)-Werte, die Datumsangaben im Bereich vom 1. Januar des Jahres 0001 bis zum 31. Dezember des Jahres 9999 und Uhrzeiten von 00:00:00 Uhr (Mitternacht) bis 23:59:59.9999999 Uhr darstellen. Jedes Inkrement stellt 100 Nanosekunden verstrichener Zeit seit Beginn des 1. Januar des Jahres 1 im gregorianischen Kalender dar. Der maximale Wert stellt 100 Nanosekunden vor Beginn des 1. Januar des Jahres 10000 dar.

## <a name="remarks"></a>Hinweise

Verwenden Sie den `Date`-Datentyp, um Datumswerte, Uhrzeitwerte oder Datums-und Uhrzeitwerte einzuschließen.

Der Standardwert von `Date` ist 0:00:00 (Mitternacht) am 1. Januar 0001.

Sie erhalten das aktuelle Datum und die aktuelle Uhrzeit aus der <xref:Microsoft.VisualBasic.DateAndTime>-Klasse.

## <a name="format-requirements"></a>Formatanforderungen

Sie müssen einen `Date`-Literal zwischen Nummernzeichen (`# #`) einschließen. Sie müssen den Datumswert im Format M/T/JJJJ angeben, z. B. `#5/31/1993#`, oder JJJJ-MM-TT, z. B. `#1993-5-31#`. Wenn Sie das Jahr zuerst angeben, können Sie Schrägstriche verwenden.  Dies gilt unabhängig vom Gebietsschema und den Formateinstellungen für Datum und Uhrzeit Ihres Computers.

Der Grund für diese Einschränkung ist, dass sich die Bedeutung des Codes nicht je nach dem Gebietsschema, in dem die Anwendung ausgeführt wird, ändern soll. Angenommen, Sie möchten ein `Date`-Literal von `#3/4/1998#` als vordefinierten Code aufnehmen und die Bedeutung 4. März 1998 festlegen. In einem Gebietsschema, das MM/TT/JJJJ verwendet, wird 3/4/1998 wie gewünscht kompiliert. Angenommen, Sie stellen die Anwendung in vielen Ländern/Regionen bereit. In einem Gebietsschema, das TT/MM/JJJJ verwendet, würde das als vordefinierter Code aufgenommene Literal als 3. April 1998 kompiliert. In einem Gebietsschema, das JJJJ/MM/TT verwendet, wäre das Literal ungültig (1998. April 0003) und würde einen Compilerfehler verursachen.

## <a name="workarounds"></a>Problemumgehung

Um ein `Date`-Literal in das Format Ihres Gebietsschemas oder in ein benutzerdefiniertes Format zu konvertieren, müssen Sie das Literal für die <xref:Microsoft.VisualBasic.Strings.Format%2A>-Funktion bereitstellen und entweder ein vordefiniertes oder ein benutzerdefiniertes Datumsformat angeben. Dies wird im folgenden Beispiel veranschaulicht:

```vb
MsgBox("The formatted date is " & Format(#5/31/1993#, "dddd, d MMM yyyy"))
```

Alternativ können Sie einen der überladenen Konstruktoren der <xref:System.DateTime>-Struktur verwenden, um einen Datums- und Uhrzeitwert zu assemblieren. Im folgenden Beispiel wird ein Wert für den 31. Mai 1993 um 12:14 Uhr nachmittags erstellt.

```vb
Dim dateInMay As New System.DateTime(1993, 5, 31, 12, 14, 0)
```

## <a name="hour-format"></a>Stundenformat

Sie können den Zeitwert im 12- oder 24-Stunden-Format angeben, z. B. `#1:15:30 PM#` oder `#13:15:30#`. Wenn Sie allerdings weder Minuten noch Sekunden angeben, müssen Sie AM oder PM angeben.

## <a name="date-and-time-defaults"></a>Standardwerte für Datum und Uhrzeit

Wenn Sie in einem Datum-/Uhrzeit-Literal kein Datum angeben, legt Visual Basic den Datumsteil des Werts auf den 1. Januar 0001 fest. Wenn Sie in einem Datum-/Uhrzeit-Literal keine Uhrzeit angeben, legt Visual Basic den Uhrzeitteil des Werts auf den Beginn des Tages, d. h. Mitternacht (0:00:00) fest.

## <a name="type-conversions"></a>Typkonvertierungen

Beim Konvertieren eines `Date`-Werts in den `String`-Typ, gibt Visual Basic das Datum gemäß dem kurzen Datumsformat wieder, das vom Laufzeitgebietsschema angegeben wird, und die Uhrzeit gemäß dem Zeitformat (entweder 12- oder 24-Stunden-Format), das vom Laufzeitgebietsschema angegeben wird.

## <a name="programming-tips"></a>Programmiertipps

- **Interop-Überlegungen.** Wenn Sie Komponenten anbinden, die nicht für .NET Framework geschrieben wurden (z. B. Automatisierungs- oder COM-Objekte), müssen Sie beachten, dass Datums-/Uhrzeittypen in anderen Umgebungen nicht zum `Date`-Typ von Visual Basic kompatibel sind. Wenn Sie ein Datums-/Uhrzeitargument an eine solche Komponente übergeben, deklarieren Sie es im neuen Visual Basic-Code als `Double` und nicht als `Date`, und verwenden Sie die Konvertierungsmethoden <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> und <xref:System.DateTime.ToOADate%2A?displayProperty=nameWithType>.

- **Geben Sie Zeichen ein.** `Date` hat kein Literaltyp Zeichen oder Bezeichnertyp Zeichen. Der Compiler behandelt jedoch Literale, die in Nummernzeichen (`# #`) eingeschlossen sind, als `Date`.

- **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.DateTime?displayProperty=nameWithType>-Struktur.

## <a name="example"></a>Beispiel

Eine Variable oder Konstante des `Date`-Datentyps enthält das Datum und die Uhrzeit. Das folgende Beispiel veranschaulicht dies.

```vb
Dim someDateAndTime As Date = #8/13/2002 12:14 PM#
```

## <a name="see-also"></a>Siehe auch

- <xref:System.DateTime?displayProperty=nameWithType>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Standard Date and Time Format Strings](../../../standard/base-types/standard-date-and-time-format-strings.md)
- [Custom Date and Time Format Strings](../../../standard/base-types/custom-date-and-time-format-strings.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

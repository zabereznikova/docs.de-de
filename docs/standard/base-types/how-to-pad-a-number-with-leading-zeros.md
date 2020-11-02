---
title: 'Vorgehensweise: Auffüllen einer Zahl mit führenden Nullen'
description: Erfahren Sie, wie Sie eine Zahl mit führenden Nullen auffüllen. Fügen Sie führende Nullen zu ganzen Zahlen oder numerischen Werten bis zu einer bestimmten Gesamtlänge oder einer bestimmten Anzahl führender Nullen hinzu.
ms.date: 02/25/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET]
- formatting [.NET], numbers
- number formatting [.NET]
- numbers [.NET], format strings
ms.assetid: 0b2c2cb5-c580-4891-8d81-cb632f5ec384
ms.openlocfilehash: 7c3ee376fde34663ee0599c0b1ae654871a71206
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888455"
---
# <a name="how-to-pad-a-number-with-leading-zeros"></a>Vorgehensweise: Auffüllen einer Zahl mit führenden Nullen

Führende Nullen können Sie mithilfe der [numerischen Standardformatzeichenfolge](standard-numeric-format-strings.md) „D“ zusammen mit einem Genauigkeitsbezeichner zu einer Ganzzahl hinzufügen. Ganz- und Gleitkommazahlen können Sie führende Nullen mithilfe einer [benutzerdefinierten numerischen Formatzeichenfolge](custom-numeric-format-strings.md) hinzufügen. In diesem Artikel lernen Sie beide Methoden zum Auffüllen einer Zahl mit führenden Nullen kennen.

## <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a>Ganzzahl bis zu einer bestimmten Länge mit führenden Nullen auffüllen

1. Bestimmen Sie die Mindestanzahl an Ziffern, die der Ganzzahlwert anzeigen soll. Schließen Sie alle führenden Ziffern in diese Zahl ein.

1. Bestimmen Sie, ob die Ganzzahl als Dezimalwert oder als Hexadezimalwert angezeigt werden soll.

    - Um sie als Dezimalwert anzuzeigen, rufen Sie ihre `ToString(String)`-Methode auf, und übergeben Sie die Zeichenfolge "D *n* " als Wert des `format`-Parameters, wobei *n* die minimale Länge der Zeichenfolge darstellt.

    - Um die ganze Zahl als Hexadezimalwert anzuzeigen, rufen Sie ihre `ToString(String)`-Methode auf, und übergeben Sie die Zeichenfolge „X *n* “ als Wert des format-Parameters, wobei *n* die Mindestlänge der Zeichenfolge darstellt.

Sie können auch die Formatzeichenfolge in einer interpolierten Zeichenfolge sowohl in [C#](../../csharp/language-reference/tokens/interpolated.md) als auch [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) verwenden, oder Sie können eine Methode aufrufen, z. B. <xref:System.String.Format%2A?displayProperty=nameWithType> oder <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, die [kombinierte Formatierung](composite-formatting.md) verwendet.

Im folgenden Beispiel sind mehrere Ganzzahlwerte so mit führenden Nullen formatiert, dass die Gesamtlänge der formatierten Zahl mindestens acht Zeichen beträgt.

[!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
[!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]

## <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a>Ganzzahl mit einer bestimmten Anzahl führender Nullen auffüllen

1. Bestimmen Sie, wie viele führende Nullen der Ganzzahlwert anzeigen soll.

1. Bestimmen Sie, ob die Ganzzahl als Dezimalwert oder als Hexadezimalwert angezeigt werden soll.

    - Das Formatieren der Ganzzahl als Dezimalwert erfordert die Verwendung des Standardformatbezeichners „D“.

    - Das Formatieren der Ganzzahl als Hexadezimalwert erfordert die Verwendung des Standardformatbezeichners „X“.

1. Bestimmen Sie die Länge der noch nicht mit Nullen aufgefüllten numerischen Zeichenfolge, indem Sie die `ToString("D").Length`- oder die `ToString("X").Length`-Methode des Ganzzahlwerts aufrufen.

1. Fügen Sie die Anzahl der führenden Nullen, die in die formatierte Zeichenfolge eingefügt werden sollen, zur Länge der nicht aufgefüllten numerischen Zeichenfolge hinzu. Durch Hinzufügen der Anzahl der führenden Nullen wird die Gesamtlänge der aufgefüllten Zeichenfolge definiert.

1. Rufen Sie die `ToString(String)`-Methode des Ganzzahlwerts auf, und übergeben Sie die Zeichenfolge „D *n* “ für Dezimalzeichenfolgen und „X *n* “ für Hexadezimalzeichenfolgen, wobei *n* die Gesamtlänge der aufgefüllten Zeichenfolge darstellt. Sie können die Formatzeichenfolge „D *n* “ oder „X *n* “ auch in Methoden verwenden, die die kombinierte Formatierung unterstützen.

Im folgenden Beispiel wird ein Ganzzahlwert mit fünf führenden Nullen aufgefüllt.

[!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
[!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]

## <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a>Numerischen Wert bis zu einer bestimmten Länge mit führenden Nullen auffüllen

1. Bestimmen Sie, über wie viele Ziffern links des Dezimaltrennzeichens die Zeichenfolgendarstellung der Zahl verfügen soll. Schließen Sie alle führenden Nullen in diese Gesamtzahl der Ziffern ein.

1. Definieren Sie eine benutzerdefinierte numerische Formatzeichenfolge, in der die Mindestanzahl an Nullen mit dem Null-Platzhalter („0“) dargestellt wird.

1. Rufen Sie die `ToString(String)`-Methode der Zahl auf und übergeben sie die benutzerdefinierte Formatzeichenfolge. Sie können die benutzerdefinierte Formatzeichenfolge auch mit Zeichenfolgeninterpolation oder mit Methoden verwenden, die kombinierte Formatierung unterstützen.

Im folgenden Beispiel werden mehrere numerische Werte mit führenden Nullen formatiert. Daher beträgt die Gesamtlänge der formatierten Zahl links vom Dezimaltrennzeichen mindestens acht Ziffern.

[!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
[!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]

## <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a>Numerischen Wert mit einer bestimmten Anzahl führender Nullen auffüllen

1. Bestimmen Sie, über wie viele führende Nullen der numerische Wert verfügen soll.

1. Bestimmen Sie die Anzahl der Ziffern links des Dezimaltrennzeichens in der nicht aufgefüllten numerischen Zeichenfolge:

    1. Bestimmen Sie, ob die Zeichenfolgendarstellung der Zahl ein Symbol für das Dezimaltrennzeichen beinhaltet.

    1. Wenn sie ein Dezimaltrennzeichen enthält, bestimmen Sie die Anzahl der Zeichen links des Dezimaltrennzeichens.

         - oder -

         Wenn sie kein Dezimaltrennzeichen enthält, bestimmen Sie die Länge der Zeichenfolge.

1. Erstellen Sie eine benutzerdefinierte Formatzeichenfolge, die Folgendes verwendet:

    - Den Nullplatzhalter „0“ für jede der führenden Nullen, die in der Zeichenfolge enthalten sein soll.

    - Entweder den Nullplatzhalter oder den Ziffernplatzhalter „#“ zur Darstellung der einzelnen Ziffern in der Standardzeichenfolge.

1. Übergeben Sie die benutzerdefinierte Formatzeichenfolge als Parameter an die `ToString(String)`-Methode der Zahl oder an eine Methode, die kombinierte Formatierung unterstützt.

Im folgenden Beispiel werden zwei <xref:System.Double>-Werte mit fünf führenden Nullen aufgefüllt.

[!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
[!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]

## <a name="see-also"></a>Siehe auch

- [Benutzerdefinierte Zahlenformatzeichenfolgen](custom-numeric-format-strings.md)
- [Standardmäßige Zahlenformatzeichenfolgen](standard-numeric-format-strings.md)
- [Kombinierte Formatierung](composite-formatting.md)

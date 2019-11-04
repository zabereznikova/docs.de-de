---
title: 'Vorgehensweise: Konvertieren einer Zeichenfolge in eine Zahl – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 02/11/2019
helpviewer_keywords:
- conversions [C#]
- conversions [C#], string to int
- converting strings to int [C#]
- strings [C#], converting to int
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
ms.openlocfilehash: c39602afbece4faaf6599a5c76f5746defffe03a
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73417643"
---
# <a name="how-to-convert-a-string-to-a-number-c-programming-guide"></a>Vorgehensweise: Konvertieren einer Zeichenfolge in eine Zahl (C#-Programmierhandbuch)

Sie können eine [Zeichenfolge](../../language-reference/builtin-types/reference-types.md) in eine Zahl umwandeln, indem Sie die Methode `Parse` oder `TryParse` in den verschiedenen numerischen Typen (`int`, `long`, `double` usw.) oder Methoden in der <xref:System.Convert?displayProperty=nameWithType>-Klasse aufrufen.  
  
 Bei einer Zeichenfolge ist es etwas effizienter und einfacher, eine `TryParse`-Methode (beispielsweise [`int.TryParse("11", out number)`](xref:System.Int32.TryParse%2A)) oder eine `Parse`-Methode (beispielsweise [`var number = int.Parse("11")`](xref:System.Int32.Parse%2A)) aufzurufen.  Die Verwendung einer <xref:System.Convert>-Methode eignet sich eher für allgemeine Objekte, die <xref:System.IConvertible> implementieren.  
  
 Sie können die Methode `Parse` oder `TryParse` für den numerischen Typ verwenden, den Sie in der Zeichenfolge erwarten, beispielsweise den <xref:System.Int32?displayProperty=nameWithType>-Typ.  Die <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>-Methode verwendet <xref:System.Int32.Parse%2A> intern.  Die `Parse`-Methode gibt die konvertierte Zahl zurück, und die `TryParse`-Methode gibt einen <xref:System.Boolean>-Wert zurück, der angibt, ob die Konvertierung erfolgreich war. Anschließend wird die konvertierte Zahl in einem [`out`-Parameter](../../language-reference/keywords/out.md) zurückgegeben. Wenn die Zeichenfolge in keinem gültigen Format vorliegt, löst `Parse` eine Ausnahme aus, während `TryParse` [false](../../language-reference/keywords/false-literal.md) zurückgibt. Beim Aufrufen einer `Parse`-Methode sollten Sie grundsätzlich die Ausnahmebehandlung zum Abfangen einer <xref:System.FormatException> verwenden, falls beim Analysevorgang ein Fehler auftritt.  
  
## <a name="calling-the-parse-and-tryparse-methods"></a>Aufrufen der Methoden „Parse“ und „TryParse“

Die Methoden `Parse` und `TryParse` ignorieren Leerraum am Anfang und am Ende der Zeichenfolge. Alle anderen Zeichen müssen jedoch Zeichen sein, die den entsprechenden numerischen Typ bilden (`int`, `long`, `ulong`, `float`, `decimal` usw.).  Leerraum innerhalb der Zeichenfolge, die die Zahl bildet, führt zu einem Fehler.  Beispielsweise können Sie `decimal.TryParse` verwenden, um „10“, „10.3“ oder „  10  “ zu analysieren. Sie können diese Methode jedoch nicht verwenden, um 10 aus „10X“, „1 0“ (beachten Sie das eingebettete Leerzeichen), „10 .3“ (beachten Sie das eingebettete Leerzeichen), „10e1“ (`float.TryParse` funktioniert in diesem Fall) usw. zu analysieren. Darüber hinaus kann eine Zeichenfolge, deren Wert `null` oder <xref:System.String.Empty?displayProperty=nameWithType> lautet, nicht erfolgreich analysiert werden. Durch Aufruf der <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType>-Methode können Sie auf eine NULL-Zeichenfolge oder eine leere Zeichenfolge prüfen, bevor Sie den Analyseversuch starten. 

Das folgende Beispiel zeigt sowohl erfolgreiche als auch nicht erfolgreiche Aufrufe von `Parse` und `TryParse`.  
  
[!code-csharp[Parse and TryParse](~/samples/snippets/csharp/programming-guide/string-to-number/parse-tryparse/program.cs)]  

Das folgende Beispiel veranschaulicht einen Ansatz zum Analysieren einer Zeichenfolge, die führende numerische Zeichen (einschließlich Hexadezimalzeichen) und nachstehende nicht numerische Zeichen enthalten soll. Vor dem Aufruf der <xref:System.Int32.TryParse%2A>-Methode werden gültige Zeichen vom Anfang einer Zeichenfolge einer neuen Zeichenfolge zugewiesen. Da die zu analysierenden Zeichenfolgen eine geringe Anzahl von Zeichen enthalten, wird im Beispiel zu diesem Zweck die <xref:System.String.Concat%2A?displayProperty=nameWithType>-Methode aufgerufen. Für eine umfangreichere Zeichenfolge kann stattdessen die <xref:System.Text.StringBuilder>-Klasse verwendet werden. 
  
[!code-csharp[Removing invalid characters](~/samples/snippets/csharp/programming-guide/string-to-number/parse-tryparse2/program.cs)]  

## <a name="calling-the-convert-methods"></a>Aufrufen der Convert-Methoden

In der folgenden Tabelle werden einige der Methoden aus der <xref:System.Convert>-Klasse aufgelistet, die Sie zum Konvertieren einer Zeichenfolge in eine Zahl verwenden können.  
  
|Numerischer Typ|Methode|  
|------------------|------------|  
|`decimal`|<xref:System.Convert.ToDecimal%28System.String%29>|  
|`float`|<xref:System.Convert.ToSingle%28System.String%29>|  
|`double`|<xref:System.Convert.ToDouble%28System.String%29>|  
|`short`|<xref:System.Convert.ToInt16%28System.String%29>|  
|`int`|<xref:System.Convert.ToInt32%28System.String%29>|  
|`long`|<xref:System.Convert.ToInt64%28System.String%29>|  
|`ushort`|<xref:System.Convert.ToUInt16%28System.String%29>|  
|`uint`|<xref:System.Convert.ToUInt32%28System.String%29>|  
|`ulong`|<xref:System.Convert.ToUInt64%28System.String%29>|  
  
 In diesem Beispiel wird die <xref:System.Convert.ToInt32%28System.String%29?displayProperty=nameWithType>-Methode aufgerufen, um eine Eingabezeichenfolge in einen [int](../../language-reference/builtin-types/integral-numeric-types.md)-Typ zu konvertieren. Das Beispiel fängt die zwei häufigsten Ausnahmen ab, die von dieser Methode ausgelöst werden können: <xref:System.FormatException> und <xref:System.OverflowException>. Wenn die resultierende Zahl schrittweise erhöht werden kann, ohne <xref:System.Int32.MaxValue?displayProperty=nameWithType> zu überschreiten, fügt der Beispielcode dem Ergebnis 1 hinzu und zeigt die Ausgabe an.  
  
[!code-csharp[Parsing with Convert methods](~/samples/snippets/csharp/programming-guide/string-to-number/convert/program.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [Typen](./index.md)
- [Vorgehensweise: Bestimmen, ob eine Zeichenfolge einen numerischen Wert darstellt](../strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
- [Beispiel: .NET Core-Hilfsprogramm zur Formatierung von WinForms (C#)](https://docs.microsoft.com/samples/dotnet/samples/winforms-formatting-utility-cs)

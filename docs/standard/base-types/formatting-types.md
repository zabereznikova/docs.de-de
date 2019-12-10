---
title: Formatieren von Typen in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data formatting [.NET Framework]
- dates [.NET Framework], formatting
- date formatting [.NET Framework]
- number formatting [.NET Framework]
- ToString method
- custom cultural settings [.NET Framework]
- numbers [.NET Framework], formatting
- formatting strings [.NET Framework]
- time [.NET Framework], formatting
- currency [.NET Framework], formatting
- types [.NET Framework], formatting
- format specifiers [.NET Framework]
- times [.NET Framework], formatting
- culture [.NET Framework], formatting
- formatting [.NET Framework], types supported
- base types [.NET Framework], formatting
- custom formatting [.NET Framework]
- strings [.NET Framework], formatting
ms.assetid: 0d1364da-5b30-4d42-8e6b-03378343343f
ms.openlocfilehash: 20aa7ecd354ef1a8982ae75eda87275c80cdaaf6
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802465"
---
# <a name="format-types-in-net"></a>Formatieren von Typen in .NET

Bei der Formatierung wird eine Instanz einer Klasse, Struktur oder eines Enumerationswerts in die entsprechende Zeichenfolgendarstellung konvertiert. Die resultierende Zeichenfolge kann dann häufig Benutzern angezeigt oder sie kann deserialisiert werden, um den ursprünglichen Datentyp wiederherzustellen. Diese Konvertierung kann eine Reihe von Problemen beinhalten:

- Die Art, wie diese Werte intern gespeichert werden, spiegelt nicht notwendigerweise die Art wider, wie die Benutzer sie anzeigen möchten. Eine Telefonnummer könnte beispielsweise wie folgt gespeichert werden: 8009999999. Dies ist jedoch wenig benutzerfreundlich. Stattdessen sollte die Telefonnummer wie folgt angezeigt werden: 800-999-9999. Ein Beispiel für die Formatierung einer Zahl auf diese Weise finden Sie im Abschnitt [Benutzerdefinierte Formatzeichenfolgen](#custom-format-strings) .

- Manchmal ist die Konvertierung eines Objekts in seine Zeichenfolgendarstellung nicht intuitiv. Beispielsweise ist nicht klar, wie die Zeichenfolgendarstellung eines Temperature-Objekts oder eines Person-Objekts aussehen sollte. Ein Beispiel für die Formatierung eines Temperature-Objekts auf verschiedene Weise finden Sie im Abschnitt [Standardformatzeichenfolgen](#standard-format-strings) .

- Oft ist für Werte eine kulturabhängige Formatierung erforderlich. In einer Anwendung, die zum Darstellen von Währungswerten Zahlen verwendet, sollten numerische Zeichenfolgen beispielsweise das Währungssymbol der aktuellen Kultur, das Gruppentrennzeichen (in den meisten Kulturen das Tausendertrennzeichen) und das Dezimaltrennzeichen einschließen. Ein Beispiel finden Sie im Abschnitt [Kulturabhängige Formatierung mit Formatanbietern](#culture-sensitive-formatting-with-format-providers).

- Unter Umständen muss ein Wert in einer Anwendung auf unterschiedliche Arten angezeigt werden. Beispielsweise stellt eine Anwendung einen Enumerationsmember möglicherweise dar, indem eine Zeichenfolgendarstellung des Namens oder des zugrunde liegende Werts angezeigt wird. Ein Beispiel für die Formatierung eines Members der <xref:System.DayOfWeek> -Enumeration auf unterschiedliche Weise finden Sie im Abschnitt [Standardformatzeichenfolgen](#standard-format-strings) .

> [!NOTE]
> Durch das Formatieren wird der Wert eines Typs in eine Zeichenfolgendarstellung konvertiert. Die Analyse ist die Umkehroperation zum Formatieren. In einem Analysevorgang wird eine Instanz eines Datentyps aus seiner Zeichenfolgendarstellung erstellt. Informationen zum Konvertieren von Zeichenfolgen in andere Datentypen finden Sie unter [Parsing Strings](../../../docs/standard/base-types/parsing-strings.md).

.NET bietet eine umfangreiche Formatierungsunterstützung, die es Entwicklern ermöglicht, diese Anforderungen zu erfüllen.

## <a name="formatting-in-net"></a>Formatierung in .NET

Der grundlegende Mechanismus für die Formatierung ist die Standardimplementierung der <xref:System.Object.ToString%2A?displayProperty=nameWithType>-Methode, die im Abschnitt [Standardformatierung mit der ToString-Methode](#default-formatting-using-the-tostring-method) später in diesem Thema erläutert wird. .NET bietet jedoch mehrere Möglichkeiten, die Standardformatierungsunterstützung zu ändern und zu erweitern. Hierzu gehört Folgendes:

- Überschreiben der <xref:System.Object.ToString%2A?displayProperty=nameWithType> -Methode, um eine benutzerdefinierte Zeichenfolgendarstellung für den Wert eines Objekts zu definieren. Weitere Informationen erhalten Sie im Abschnitt [Überschreiben der ToString-Methode](#override-the-tostring-method) weiter unten in diesem Thema.

- Definieren von Formatbezeichnern, die es ermöglichen, dass die Zeichenfolgendarstellung des Werts eines Objekts mehrere Formate annehmen kann. Der Formatbezeichner "X" in der folgenden Anweisung konvertiert beispielsweise eine ganze Zahl in die Zeichenfolgendarstellung eines Hexadezimalwerts.

     [!code-csharp[Conceptual.Formatting.Overview#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/specifier1.cs#3)]
     [!code-vb[Conceptual.Formatting.Overview#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/specifier1.vb#3)]

     Weitere Informationen zu Formatbezeichnern finden Sie im Abschnitt [ToString-Methode und Formatzeichenfolgen](#the-tostring-method-and-format-strings) .

- Verwenden von Formatanbietern, die Formatierungskonventionen einer bestimmten Kultur nutzen. Beispielsweise zeigt die folgende Anweisung einen Währungswert unter Verwendung der Formatierungskonventionen der Kultur en-US an.

     [!code-csharp[Conceptual.Formatting.Overview#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/specifier1.cs#10)]
     [!code-vb[Conceptual.Formatting.Overview#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/specifier1.vb#10)]

     Weitere Informationen zum Formatieren mit Formatanbietern finden Sie im Abschnitt [Formatanbieter](#culture-sensitive-formatting-with-format-providers).

- Implementieren der <xref:System.IFormattable> -Schnittstelle zur Unterstützung der Zeichenfolgenkonvertierung mit der <xref:System.Convert> -Klasse sowie der kombinierten Formatierung. Weitere Informationen finden Sie im Abschnitt [IFormattable-Schnittstelle](#the-iformattable-interface) .

- Verwenden der kombinierten Formatierung, um die Zeichenfolgendarstellung eines Werts in einer größeren Zeichenfolge einzubetten. Weitere Informationen finden Sie im Abschnitt [Kombinierte Formatierung](#composite-formatting) .

- Implementieren von <xref:System.ICustomFormatter> und <xref:System.IFormatProvider> , um eine vollständige benutzerdefinierte Formatierungslösung bereitzustellen. Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte Formatierung mit ICustomFormatter](#custom-formatting-with-icustomformatter) .

In den folgenden Abschnitten werden diese Methoden zum Konvertieren eines Objekts in seine Zeichenfolgendarstellung ausführlicher erläutert.

## <a name="default-formatting-using-the-tostring-method"></a>Standardformatierung mit der ToString-Methode

Jeder von <xref:System.Object?displayProperty=nameWithType> abgeleitete Typ erbt automatisch eine parameterlose `ToString` -Methode, die standardmäßig den Namen des Typs zurückgibt. Das folgende Beispiel veranschaulicht die `ToString` -Standardmethode. Dabei wird eine Klasse mit dem Namen `Automobile` ohne Implementierung definiert. Wenn die Klasse instanziiert und die zugehörige `ToString` -Methode aufgerufen wird, wird der Typname angezeigt. Beachten Sie, dass die `ToString` -Methode im Beispiel nicht explizit aufgerufen wird. Die <xref:System.Console.WriteLine%28System.Object%29?displayProperty=nameWithType> -Methode ruft implizit die `ToString` -Methode des Objekts auf, das ihr als Argument übergeben wird.

[!code-csharp[Conceptual.Formatting.Overview#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/default1.cs#1)]
[!code-vb[Conceptual.Formatting.Overview#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/default1.vb#1)]

> [!WARNING]
> Ab Windows 8.1 enthält die Windows-Runtime eine Schnittstelle <xref:Windows.Foundation.IStringable> mit einer einzelnen Methode, [IStringable.ToString](xref:Windows.Foundation.IStringable.ToString%2A), die eine standardmäßige Formatierungsunterstützung bereitstellt. Es wird jedoch empfohlen, dass verwaltete Typen die `IStringable` -Schnittstelle nicht implementieren. Weitere Informationen finden Sie im Abschnitt „Die Windows-Runtime und die `IStringable`-Schnittstelle“ auf der <xref:System.Object.ToString%2A?displayProperty=nameWithType>-Referenzseite.

Da alle anderen Typen außer Schnittstellen von <xref:System.Object>abgeleitet werden, wird diese Funktionalität automatisch für die benutzerdefinierten Klassen oder Strukturen bereitgestellt. Aber die von der standardmäßigen `ToString`-Methode gebotene Funktionalität ist beschränkt: Zwar identifiziert sie den Typ, liefert jedoch keine Informationen zu einer Instanz des Typs. Um eine Zeichenfolgendarstellung eines Objekts bereitzustellen, die Informationen zum Objekt enthält, müssen Sie die `ToString` -Methode überschreiben.

> [!NOTE]
> Strukturen erben vom <xref:System.ValueType>, der von <xref:System.Object>abgeleitet wird. Auch wenn <xref:System.ValueType> von <xref:System.Object.ToString%2A?displayProperty=nameWithType>überschrieben wird, ist die Implementierung identisch.

## <a name="override-the-tostring-method"></a>Überschreiben der ToString-Methode

Das Anzeigen des Namens eines Typs ist oft nur von geringem Nutzen und ermöglicht Consumern der Typen keine Unterscheidung zwischen den einzelnen Instanzen. Sie können jedoch die `ToString` -Methode überschreiben, um eine nützlichere Darstellung eines Objektwerts bereitzustellen. Im folgenden Beispiel wird ein `Temperature` -Objekt definiert und die `ToString` -Methode wird überschrieben, um die Temperatur in Grad Celsius anzuzeigen.

[!code-csharp[Conceptual.Formatting.Overview#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/overrides1.cs#2)]
[!code-vb[Conceptual.Formatting.Overview#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/overrides1.vb#2)]

In .NET wurde die `ToString`-Methode jedes primitiven Werttyps überschrieben, um den Wert des Objekts statt seines Namens anzuzeigen. In der folgenden Tabelle wird die Überschreibung für den jeweiligen primitiven Typ angezeigt. Beachten Sie, dass die meisten der überschriebenen Methoden eine andere Überladung der `ToString` -Methode aufrufen und dabei den Formatbezeichner G übergeben, der das allgemeine Format des Typs definiert, sowie ein <xref:System.IFormatProvider> -Objekt, das die aktuelle Kultur darstellt.

|Typ|ToString-Überschreibung|
|----------|-----------------------|
|<xref:System.Boolean>|Gibt entweder <xref:System.Boolean.TrueString?displayProperty=nameWithType> oder <xref:System.Boolean.FalseString?displayProperty=nameWithType>zurück.|
|<xref:System.Byte>|Ruft `Byte.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den <xref:System.Byte> -Wert für die aktuelle Kultur zu formatieren.|
|<xref:System.Char>|Gibt das Zeichen als Zeichenfolge zurück.|
|<xref:System.DateTime>|Ruft `DateTime.ToString("G", DatetimeFormatInfo.CurrentInfo)` auf, um den Datums- und Uhrzeitwert für die aktuelle Kultur zu formatieren.|
|<xref:System.Decimal>|Ruft `Decimal.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den <xref:System.Decimal> -Wert für die aktuelle Kultur zu formatieren.|
|<xref:System.Double>|Ruft `Double.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den <xref:System.Double> -Wert für die aktuelle Kultur zu formatieren.|
|<xref:System.Int16>|Ruft `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den <xref:System.Int16> -Wert für die aktuelle Kultur zu formatieren.|
|<xref:System.Int32>|Ruft `Int32.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den <xref:System.Int32> -Wert für die aktuelle Kultur zu formatieren.|
|<xref:System.Int64>|Ruft `Int64.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den <xref:System.Int64> -Wert für die aktuelle Kultur zu formatieren.|
|<xref:System.SByte>|Ruft `SByte.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den <xref:System.SByte> -Wert für die aktuelle Kultur zu formatieren.|
|<xref:System.Single>|Ruft `Single.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den <xref:System.Single> -Wert für die aktuelle Kultur zu formatieren.|
|<xref:System.UInt16>|Ruft `UInt16.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den <xref:System.UInt16> -Wert für die aktuelle Kultur zu formatieren.|
|<xref:System.UInt32>|Ruft `UInt32.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den <xref:System.UInt32> -Wert für die aktuelle Kultur zu formatieren.|
|<xref:System.UInt64>|Ruft `UInt64.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den <xref:System.UInt64> -Wert für die aktuelle Kultur zu formatieren.|

## <a name="the-tostring-method-and-format-strings"></a>ToString-Methode und Formatzeichenfolgen

Wenn ein Objekt über eine einzelne Zeichenfolgendarstellung verfügt, ist das Verwenden der `ToString` -Standardmethode oder das Überschreiben von `ToString` angemessen. Der Wert eines Objekts weist jedoch häufig mehrere Darstellungen auf. Beispielsweise kann die Temperatur in Grad Fahrenheit, Grad Celsius oder Kelvin ausgedrückt werden. Entsprechend kann der ganzzahlige Wert 10 unterschiedlich dargestellt werden, z. B. als 10, 10.0, 1.0e01 oder $10.00.

Damit ein einzelner Wert mehrere Zeichenfolgendarstellungen aufweisen kann, verwendet .NET Formatzeichenfolgen. Eine Formatzeichenfolge ist eine Zeichenfolge, die einen oder mehrere vordefinierte Formatbezeichner enthält. Dies sind einzelne Zeichen oder Gruppen von Zeichen, die definieren, wie die `ToString` -Methode die Ausgabe formatieren soll. Die Formatzeichenfolge wird dann als Parameter an die `ToString` -Methode des Objekts übergeben und bestimmt, wie die Zeichenfolgendarstellung des Werts dieses Objekts angezeigt werden soll.

Alle numerischen Typen sowie die Datums- und Uhrzeittypen und die Enumerationstypen in .NET unterstützen einen vordefinierten Satz von Formatbezeichnern. Sie können auch Formatzeichenfolgen verwenden, um mehrere Zeichenfolgendarstellungen der anwendungsdefinierten Datentypen zu definieren.

### <a name="standard-format-strings"></a>Standardformatzeichenfolgen

Standardformatzeichenfolgen enthalten einen einzelnen Formatbezeichner. Dabei handelt es sich um ein alphabetisches Zeichen, das die Zeichenfolgendarstellung des Objekts definiert, auf das es angewendet wird. Außerden enthalten sie einen optionalen Genauigkeitsbezeichner, der angibt, wie viele Stellen in der Ergebniszeichenfolge angezeigt werden. Wenn der Genauigkeitsbezeichner nicht angegeben oder nicht unterstützt wird, entspricht ein Standardformatbezeichner einer Standardformatzeichenfolge.

.NET definiert einen Satz von Standardformatbezeichnern für alle numerischen Typen, alle Datums- und Uhrzeittypen und alle Enumerationstypen. Beispielsweise definieren die einzelnen Kategorien den Standardformatbezeichner "G", der eine allgemeine Zeichenfolgendarstellung für einen Wert dieses Typs definiert.

Standardformatzeichenfolgen für Enumerationstypen steuern die Zeichenfolgendarstellung eines Werts direkt. Die an die `ToString` -Methode eines Enumerationswerts übergebenen Formatzeichenfolgen bestimmen, ob der Wert mit seinem Zeichenfolgennamen (Formatbezeichner "G" und "F"), seinem zugrunde liegenden ganzzahligen Wert (Formatbezeichner "D") oder seinem Hexadezimalwert (Formatbezeichner "X") angezeigt wird. Im folgenden Beispiel wird die Verwendung von Standardformatzeichenfolgen zum Formatieren eines <xref:System.DayOfWeek> -Enumerationswerts veranschaulicht.

[!code-csharp[Conceptual.Formatting.Overview#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/standard1.cs#4)]
[!code-vb[Conceptual.Formatting.Overview#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/standard1.vb#4)]

Weitere Informationen über Enumerationsformatzeichenfolgen finden Sie unter [Enumeration Format Strings](../../../docs/standard/base-types/enumeration-format-strings.md).

Standardformatzeichenfolgen für numerische Typen definieren normalerweise eine Ergebniszeichenfolge, deren genaue Darstellung von einem oder mehreren Eigenschaftswerten gesteuert wird. Beispielsweise formatiert der Formatbezeichner "C" eine Zahl als Währungswert. Wenn Sie die `ToString` -Methode mit dem Formatbezeichner "C" als einzigem Parameter aufrufen, werden die folgenden Eigenschaftswerte des <xref:System.Globalization.NumberFormatInfo> -Objekts der aktuellen Kultur verwendet, um die Zeichenfolgendarstellung des numerischen Werts zu definieren:

- Die <xref:System.Globalization.NumberFormatInfo.CurrencySymbol%2A> -Eigenschaft, die das Währungssymbol der aktuellen Kultur angibt.

- Die <xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern%2A> -Eigenschaft oder die <xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern%2A> -Eigenschaft, die eine ganz Zahl zurückgeben, die Folgendes bestimmt:

  - Die Platzierung des Währungssymbols.

  - Ob negative Werte durch ein führendes negatives Vorzeichen, ein nachfolgendes negatives Vorzeichen oder durch Klammern angegeben werden.

  - Ob zwischen dem numerischen Wert und dem Währungssymbol ein Leerzeichen angezeigt wird.

- Die <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits%2A> -Eigenschaft, die die Anzahl der Dezimalstellen in der Ergebniszeichenfolge definiert.

- Die <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator%2A> -Eigenschaft, die das Dezimaltrennzeichen in der Ergebniszeichenfolge definiert.

- Die <xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator%2A> -Eigenschaft, die das Gruppentrennzeichen definiert.

- Die <xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes%2A> -Eigenschaft, die die Anzahl der Stellen in jeder Gruppe links vom Dezimaltrennzeichen definiert.

- Die <xref:System.Globalization.NumberFormatInfo.NegativeSign%2A> -Eigenschaft, die das negative Vorzeichen bestimmt, das in der Ergebniszeichenfolge verwendet wird, wenn negative Werte nicht mit Klammern angegeben werden.

Darüber hinaus enthalten numerische Formatzeichenfolgen möglicherweise einen Genauigkeitsbezeichner. Die Bedeutung dieses Bezeichners ist abhängig von der Formatzeichenfolge, mit der er verwendet wird. In aller Regel wird dadurch jedoch entweder die Gesamtzahl der Stellen oder die Anzahl der Dezimalstellen angegeben, die in der Ergebniszeichenfolge erscheinen soll. So werden im folgenden Beispiel die numerische Standardzeichenfolge "X4" sowie ein Genauigkeitsbezeichner angegeben, um einen Zeichenfolgenwert mit vier Hexadezimalzahlen zu erstellen.

[!code-csharp[Conceptual.Formatting.Overview#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/precisionspecifier1.cs#6)]
[!code-vb[Conceptual.Formatting.Overview#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/precisionspecifier1.vb#6)]

Weitere Informationen zu standardmäßigen numerischen Formatierungszeichenfolgen finden Sie unter [Standard Numeric Format Strings](../../../docs/standard/base-types/standard-numeric-format-strings.md).

Standardformatzeichenfolgen für Datums- und Uhrzeitwerte sind Aliase für benutzerdefinierte Formatzeichenfolgen, die von einer bestimmten <xref:System.Globalization.DateTimeFormatInfo> -Eigenschaft gespeichert werden. Beispielsweise werden durch Aufrufen der `ToString` -Methode eines Datums- und Uhrzeitwerts mit dem Formatbezeichner "D" das Datum und die Uhrzeit mit der benutzerdefinierten Formatzeichenfolge angezeigt, die in der <xref:System.Globalization.DateTimeFormatInfo.LongDatePattern%2A?displayProperty=nameWithType> -Eigenschaft der aktuellen Kultur gespeichert sind. (Weitere Informationen zu benutzerdefinierten Formatzeichenfolgen finden Sie im [nächsten Abschnitt](#custom-format-strings).) Diese Beziehung wird anhand des folgenden Beispiels veranschaulicht.

[!code-csharp[Conceptual.Formatting.Overview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/alias1.cs#5)]
[!code-vb[Conceptual.Formatting.Overview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/alias1.vb#5)]

Weitere Informationen über Standardformatzeichenfolgen für Datum und Uhrzeit finden Sie unter [Standard Date and Time Format Strings](../../../docs/standard/base-types/standard-date-and-time-format-strings.md).

Sie können Standardformatzeichenfolgen auch verwenden, um die Zeichenfolgendarstellung eines anwendungsdefinierten Objekts anzugeben, die von der `ToString(String)` -Methode des Objekts erstellt wird. Sie können die spezifischen Standardformatbezeichner definieren, die von dem Objekt unterstützt werden, und Sie können angeben, ob die Groß- und Kleinschreibung beachtet werden soll. Ihre Implementierung der `ToString(String)`-Methode sollte Folgendes unterstützen:

- Den Formatbezeichner "G", der ein übliches oder allgemeines Format des Objekts darstellt. Die parameterlose Überladung der `ToString` -Methode des Objekts sollte die zugehörige `ToString(String)` -Überladung aufrufen und die Standardformatzeichenfolge "G" übergeben.

- Unterstützung für einen Formatbezeichner, der gleich einem NULL-Verweis (`Nothing` in Visual Basic) ist. Ein Formatbezeichner, der gleich einem NULL-Verweis ist, sollte als äquivalent mit dem "G"-Formatbezeichner angesehen werden.

Beispielsweise kann eine `Temperature`-Klasse die Temperatur in Grad Celsius intern speichern und Formatbezeichner verwenden, um den Wert des `Temperature`-Objekts in Grad Celsius, Grad Fahrenheit und Kelvin darzustellen. Dies wird im folgenden Beispiel veranschaulicht.

[!code-csharp[Conceptual.Formatting.Overview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/appstandard1.cs#7)]
[!code-vb[Conceptual.Formatting.Overview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/appstandard1.vb#7)]

### <a name="custom-format-strings"></a>Benutzerdefinierte Formatzeichenfolgen

Zusätzlich zu den Standardformatzeichenfolgen definiert .NET benutzerdefinierte Formatzeichenfolgen für numerische Werte und Datums- und Uhrzeitwerte. Eine benutzerdefinierte Formatzeichenfolge besteht aus einem oder mehreren benutzerdefinierten Formatbezeichnern, die die Zeichenfolgendarstellung eines Werts definieren. Beispielsweise konvertiert die benutzerdefinierte Datums- und Uhrzeitformatzeichenfolge "yyyy/mm/dd hh:mm:ss.ffff t zzz" ein Datum für die Kultur en-US wie folgt in die entsprechende Zeichenfolgendarstellung: "2008/11/15 07:45:00.0000 P -08:00". Analog konvertiert die benutzerdefinierte Formatzeichenfolge "0000" den ganzzahligen Wert 12 in "0012". Eine vollständige Liste von benutzerdefinierten Formatzeichenfolgen finden Sie unter [Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md) und [Custom Numeric Format Strings](../../../docs/standard/base-types/custom-numeric-format-strings.md).

Wenn eine Formatzeichenfolge aus einem einzelnen benutzerdefinierten Formatbezeichner besteht, sollte dem Formatbezeichner das Prozentsymbol (%) vorangestellt werden, um Verwechslungen mit einem Standardformatbezeichner zu vermeiden. Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner "M" verwendet, um eine einstellige oder zweistellige Ziffer für einen bestimmten Tag des Monats anzuzeigen.

[!code-csharp[Conceptual.Formatting.Overview#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/singlecustom1.cs#8)]
[!code-vb[Conceptual.Formatting.Overview#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/singlecustom1.vb#8)]

Viele Standardformatzeichenfolgen für Datums- und Uhrzeitwerte sind Aliase für benutzerdefinierte Formatzeichenfolgen, die von Eigenschaften des <xref:System.Globalization.DateTimeFormatInfo> -Objekts definiert werden. Benutzerdefinierte Formatzeichenfolgen ermöglichen außerdem eine hohe Flexibilität beim Bereitstellen von anwendungsdefinierter Formatierung für numerische Werte oder Datums- und Uhrzeitwerte. Sie können eigene benutzerdefinierte Ergebniszeichenfolgen für numerische Werte und für Datums- und Uhrzeitwerte definieren, indem Sie mehrere benutzerdefinierte Formatbezeichner zu einer einzelnen benutzerdefinierten Formatzeichenfolge kombinieren. Im folgenden Beispiel wird eine benutzerdefinierte Formatzeichenfolge definiert, die im Anschluss an den Namen des Monats, den Tag und das Jahr den Tag der Woche in Klammern anzeigt.

[!code-csharp[Conceptual.Formatting.Overview#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/custom1.cs#9)]
[!code-vb[Conceptual.Formatting.Overview#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/custom1.vb#9)]

Das folgende Beispiel definiert eine benutzerdefinierte Formatzeichenfolge, die einen <xref:System.Int64> -Wert als standardmäßige, siebenstellige US-Telefonnummer mit der Ortskennzahl anzeigt.

[!code-csharp[Conceptual.Formatting.Overview#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/telnumber1.cs#21)]
[!code-vb[Conceptual.Formatting.Overview#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/telnumber1.vb#21)]

Standardformatzeichenfolgen decken i. d. R. die meisten der Formatierungsanforderungen für anwendungsdefinierte Typen ab. Sie können jedoch auch benutzerdefinierte Formatbezeichner definieren, um Typen zu formatieren.

### <a name="format-strings-and-net-types"></a>Formatzeichenfolgen und .NET-Typen

Alle numerischen Typen (d.h. <xref:System.Byte>, <xref:System.Decimal>, <xref:System.Double>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.SByte>, <xref:System.Single>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64> und <xref:System.Numerics.BigInteger>) sowie <xref:System.DateTime>, <xref:System.DateTimeOffset>, <xref:System.TimeSpan>, <xref:System.Guid> und alle Enumerationstypen unterstützen die Formatierung mit Formatzeichenfolgen. Informationen zu bestimmten Formatzeichenfolgen, die von jedem Typ unterstützt werden, finden Sie in den folgenden Themen:

|Titel|Definition|
|-----------|----------------|
|[Standard Numeric Format Strings](../../../docs/standard/base-types/standard-numeric-format-strings.md)|Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen häufig verwendete Zeichenfolgenentsprechungen von numerischen Werten erstellt werden.|
|[Custom Numeric Format Strings](../../../docs/standard/base-types/custom-numeric-format-strings.md)|Beschreibt benutzerdefinierte Formatzeichenfolgen, die anwendungsspezifische Formate für numerische Werte erstellen.|
|[Standard Date and Time Format Strings](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)|Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen häufig verwendete Zeichenfolgenentsprechungen von <xref:System.DateTime>- und<xref:System.DateTimeOffset>-Werten erstellt werden.|
|[Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)|Beschreibt benutzerdefinierte Formatzeichenfolgen, die anwendungsspezifische Formate für <xref:System.DateTime>- und <xref:System.DateTimeOffset>-Werte erstellen.|
|[TimeSpan-Standardformatzeichenfolgen](../../../docs/standard/base-types/standard-timespan-format-strings.md)|Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen häufig verwendete Zeichenfolgenentsprechungen von Zeitintervallen erstellt werden.|
|[Benutzerdefinierte TimeSpan-Formatzeichenfolgen](../../../docs/standard/base-types/custom-timespan-format-strings.md)|Beschreibt benutzerdefinierte Formatzeichenfolgen, die anwendungsspezifische Formate für Zeitintervalle erstellen.|
|[Enumeration Format Strings](../../../docs/standard/base-types/enumeration-format-strings.md)|Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen Zeichenfolgenentsprechungen von Enumerationswerten erstellt werden.|
|<xref:System.Guid.ToString%28System.String%29?displayProperty=nameWithType>|Beschreibt die Standard-Formatzeichenfolgen für <xref:System.Guid> -Werte.|

## <a name="culture-sensitive-formatting-with-format-providers"></a>Kulturabhängige Formatierung mit Formatanbietern

Obwohl Sie mit Formatbezeichnern die Formatierung von Objekten anpassen können, sind für eine sinnvolle Zeichenfolgendarstellung von Objekten oft zusätzliche Formatierungsinformationen erforderlich. Beispielsweise ist für das Formatieren einer Zahl als Währungswert mit der Standardformatzeichenfolge "C" oder mit einer benutzerdefinierten Formatzeichenfolge wie "$ #,#.00" mindestens erforderlich, dass Informationen über das richtige Währungssymbol, das richtige Gruppentrennzeichen und das richtige Dezimaltrennzeichen verfügbar sind, um in die formatierte Zeichenfolge eingeschlossen zu werden. In .NET werden diese zusätzlichen Formatierungsinformationen durch die <xref:System.IFormatProvider>-Schnittstelle verfügbar gemacht. Diese wird als Parameter für eine oder mehrere Überladungen der `ToString`-Methode von numerischen Typen sowie von Datums- und Uhrzeittypen bereitgestellt. <xref:System.IFormatProvider>-Implementierungen werden in .NET verwendet, um eine kulturabhängige Formatierung zu unterstützen. Im folgenden Beispiel wird veranschaulicht, wie sich die Zeichenfolgendarstellung eines Objekts ändert, wenn die Formatierung mit drei <xref:System.IFormatProvider> -Objekten erfolgt, die verschiedene Kulturen darstellen.

[!code-csharp[Conceptual.Formatting.Overview#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/iformatprovider1.cs#11)]
[!code-vb[Conceptual.Formatting.Overview#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/iformatprovider1.vb#11)]

Die <xref:System.IFormatProvider> -Schnittstelle enthält die <xref:System.IFormatProvider.GetFormat%28System.Type%29>-Methode. Diese weist einen einzelnen Parameter auf, der den Typ des Objekts angibt, das Formatierungsinformationen bereitstellt. Wenn die Methode ein Objekt dieses Typs bereitstellen kann, wird dieses zurückgegeben. Andernfalls wird ein NULL-Verweis (`Nothing` in Visual Basic) zurückgegeben.

<xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> ist eine Rückrufmethode. Wenn Sie eine `ToString` -Methodenüberladung aufrufen, die einen <xref:System.IFormatProvider> -Parameter einschließt, wird die <xref:System.IFormatProvider.GetFormat%2A> -Methode dieses <xref:System.IFormatProvider> -Objekts aufgerufen. Die <xref:System.IFormatProvider.GetFormat%2A> -Methode ist dafür verantwortlich, ein Objekt zurückzugeben, das die notwendigen Formatierungsinformationen, wie vom `formatType` -Parameter angegeben, für die `ToString` -Methode bereitstellt.

Eine Reihe von Formatierungs- oder Zeichenfolgenkonvertierungsmethoden enthalten einen Parameter vom Typ <xref:System.IFormatProvider>; in vielen Fällen wird der Wert des Parameters beim Aufrufen der Methode jedoch ignoriert. In der folgenden Tabelle sind einige Formatierungsmethoden aufgeführt, die den Parameter und den Typ des <xref:System.Type> -Objekts verwenden, die an die <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> -Methode übergeben werden.

|Methode|`formatType` -Parametertyp|
|------------|------------------------------------|
|`ToString` -Methode für numerische Typen|<xref:System.Globalization.NumberFormatInfo?displayProperty=nameWithType>|
|`ToString`-Methode für Datums- und Uhrzeittypen|<xref:System.Globalization.DateTimeFormatInfo?displayProperty=nameWithType>|
|<xref:System.String.Format%2A?displayProperty=nameWithType>|<xref:System.ICustomFormatter?displayProperty=nameWithType>|
|<xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>|<xref:System.ICustomFormatter?displayProperty=nameWithType>|

> [!NOTE]
> Die `ToString` -Methoden der numerischen Typen und der Datums- und Uhrzeittypen werden überladen, und nur einige der Überladungen enthalten einen <xref:System.IFormatProvider> -Parameter. Wenn eine Methode keinen Parameter vom Typ <xref:System.IFormatProvider>aufweist, wird stattdessen das Objekt übergeben, das von der <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> -Eigenschaft zurückgegeben wird. Beispielsweise führt ein Aufruf der <xref:System.Int32.ToString?displayProperty=nameWithType> -Standardmethode letztendlich zu einem Methodenaufruf wie dem folgenden: `Int32.ToString("G", System.Globalization.CultureInfo.CurrentCulture)`.

.NET stellt drei Klassen bereit, die <xref:System.IFormatProvider> implementieren:

- <xref:System.Globalization.DateTimeFormatInfo>, eine Klasse, die Formatierungsinformationen für Datums- und Uhrzeitwerte für eine bestimmte Kultur bereitstellt. Die zugehörige <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> -Implementierung gibt eine Instanz von sich selbst zurück.

- <xref:System.Globalization.NumberFormatInfo>, eine Klasse, die numerische Formatierungsinformationen für eine bestimmte Kultur bereitstellt. Die zugehörige <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> -Implementierung gibt eine Instanz von sich selbst zurück.

- <xref:System.Globalization.CultureInfo>. Die zugehörige <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> -Implementierung kann ein <xref:System.Globalization.NumberFormatInfo> -Objekt zurückgeben, um numerische Formatierungsinformationen bereitzustellen, oder ein <xref:System.Globalization.DateTimeFormatInfo> -Objekt, um Formatierungsinformationen für Datums- und Uhrzeitwerte bereitzustellen.

Sie können auch einen eigenen Formatanbieter implementieren, um eine dieser Klassen zu ersetzen. Die <xref:System.IFormatProvider.GetFormat%2A>-Methode Ihrer Implementierung muss jedoch ein Objekt eines in der vorangehenden Tabelle aufgeführten Typs zurückgeben, um Formatierungsinformationen für die `ToString`-Methode bereitzustellen.

### <a name="culture-sensitive-formatting-of-numeric-values"></a>Kulturabhängige Formatierung von numerischen Werten

Standardmäßig ist die Formatierung von numerischen Werten kulturabhängig. Wenn Sie beim Aufrufen einer Formatierungsmethode keine Kultur angeben, werden die Formatierungskonventionen der aktuellen Threadkultur verwendet. Dies wird im folgenden Beispiel veranschaulicht, das die aktuelle Threadkultur viermal ändert und anschließend die <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType> -Methode aufruft. In allen Fällen gibt die Ergebniszeichenfolge die Formatierungskonventionen der aktuellen Kultur wieder. Dies liegt daran, dass die `ToString` - und `ToString(String)` -Methoden die Aufrufe der `ToString(String, IFormatProvider)` -Methode jedes numerischen Typs umschließen.

[!code-csharp[Conceptual.Formatting.Overview#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/culturespecific3.cs#19)]
[!code-vb[Conceptual.Formatting.Overview#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/culturespecific3.vb#19)]

Sie können einen numerischen Wert für eine bestimmte Kultur ebenso formatieren, indem Sie eine `ToString` -Überladung aufrufen, die einen `provider` -Parameter hat, und ihr eines der folgenden Objekte übergeben:

- Ein <xref:System.Globalization.CultureInfo> -Objekt, das die Kultur darstellt, deren Formatierungskonventionen verwendet werden sollen. Die zugehörige <xref:System.Globalization.CultureInfo.GetFormat%2A?displayProperty=nameWithType> -Methode gibt den Wert der <xref:System.Globalization.CultureInfo.NumberFormat%2A?displayProperty=nameWithType> -Eigenschaft zurück, die das <xref:System.Globalization.NumberFormatInfo> -Objekt ist, das kulturspezifische Formatierungsinformationen für numerische Werte bereitstellt.

- Ein <xref:System.Globalization.NumberFormatInfo> -Objekt, das die kulturspezifischen Formatierungskonventionen definiert, die verwendet werden sollen. Die zugehörige <xref:System.Globalization.NumberFormatInfo.GetFormat%2A> -Methode gibt eine Instanz von sich selbst zurück.

Im folgenden Beispiel werden <xref:System.Globalization.NumberFormatInfo> -Objekte verwendet, die die Kulturen Englisch (USA) und Englisch (Großbritannien) sowie die neutralen Kulturen Französisch und Russisch darstellen, um eine Gleitkommazahl zu formatieren.

[!code-csharp[Conceptual.Formatting.Overview#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/culturespecific4.cs#20)]
[!code-vb[Conceptual.Formatting.Overview#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/culturespecific4.vb#20)]

### <a name="culture-sensitive-formatting-of-date-and-time-values"></a>Kulturabhängige Formatierung von Datums- und Uhrzeitwerten

Standardmäßig ist die Formatierung von Daten- und Uhrzeitwerten kulturabhängig. Wenn Sie beim Aufrufen einer Formatierungsmethode keine Kultur angeben, werden die Formatierungskonventionen der aktuellen Threadkultur verwendet. Dies wird im folgenden Beispiel veranschaulicht, das die aktuelle Threadkultur viermal ändert und anschließend die <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> -Methode aufruft. In allen Fällen gibt die Ergebniszeichenfolge die Formatierungskonventionen der aktuellen Kultur wieder. Dies liegt daran, dass die <xref:System.DateTime.ToString?displayProperty=nameWithType>-, <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType>-, <xref:System.DateTimeOffset.ToString?displayProperty=nameWithType>- und <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> -Methoden die Aufrufe der <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> - und <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> -Methoden umschließen.

[!code-csharp[Conceptual.Formatting.Overview#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/culturespecific1.cs#17)]
[!code-vb[Conceptual.Formatting.Overview#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/culturespecific1.vb#17)]

Sie können einen Datums- und Uhrzeitwert für eine bestimmte Kultur ebenso formatieren, indem Sie eine <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> - oder <xref:System.DateTimeOffset.ToString%2A?displayProperty=nameWithType> -Überladung aufrufen, die einen `provider` -Parameter hat, und ihr eines der folgenden Objekte übergeben:

- Ein <xref:System.Globalization.CultureInfo> -Objekt, das die Kultur darstellt, deren Formatierungskonventionen verwendet werden sollen. Die zugehörige <xref:System.Globalization.CultureInfo.GetFormat%2A?displayProperty=nameWithType> -Methode gibt den Wert der <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> -Eigenschaft zurück, die das <xref:System.Globalization.DateTimeFormatInfo> -Objekt ist, das kulturspezifische Formatierungsinformationen für Datums- und Uhrzeitwerte bereitstellt.

- Ein <xref:System.Globalization.DateTimeFormatInfo> -Objekt, das die kulturspezifischen Formatierungskonventionen definiert, die verwendet werden sollen. Die zugehörige <xref:System.Globalization.DateTimeFormatInfo.GetFormat%2A> -Methode gibt eine Instanz von sich selbst zurück.

Im folgenden Beispiel werden <xref:System.Globalization.DateTimeFormatInfo> -Objekte verwendet, die die Kulturen Englisch (USA) und Englisch (Großbritannien) sowie die neutralen Kulturen Französisch und Russisch darstellen, um ein Datum zu formatieren.

[!code-csharp[Conceptual.Formatting.Overview#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/culturespecific2.cs#18)]
[!code-vb[Conceptual.Formatting.Overview#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/culturespecific2.vb#18)]

## <a name="the-iformattable-interface"></a>IFormattable-Schnittstelle

Typen, die die `ToString` -Methode mit einer Formatzeichenfolge und einem <xref:System.IFormatProvider> -Parameter überladen, implementieren i. d. R. auch die <xref:System.IFormattable> -Schnittstelle. Diese Schnittstelle verfügt über einen einzelnen Member, <xref:System.IFormattable.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, der sowohl eine Formatzeichenfolge als auch einen Formatanbieter als Parameter einschließt.

Das Implementieren der <xref:System.IFormattable> -Schnittstelle für die anwendungsdefinierte Klasse bietet zwei Vorteile:

- Unterstützung der Zeichenfolgenkonvertierung durch die <xref:System.Convert> -Klasse. Automatisches Aufrufen der <xref:System.Convert.ToString%28System.Object%29?displayProperty=nameWithType> -Implementierung durch Aufrufe der <xref:System.Convert.ToString%28System.Object%2CSystem.IFormatProvider%29?displayProperty=nameWithType> -Methode und der <xref:System.IFormattable> -Methode.

- Unterstützung für kombinierte Formatierung. Wenn ein Formatelement, das eine Formatzeichenfolge einschließt, verwendet wird, um den benutzerdefinierten Typ zu formatieren, ruft die Common Language Runtime automatisch Ihre <xref:System.IFormattable> -Implementierung auf und übergibt die Formatzeichenfolge. Weitere Informationen zur kombinierten Formatierung mit Methoden wie <xref:System.String.Format%2A?displayProperty=nameWithType> oder <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>finden Sie im Abschnitt [Kombinierte Formatierung](#composite-formatting) .

Im folgenden Beispiel wird eine `Temperature` -Klasse definiert, die die <xref:System.IFormattable> -Schnittstelle implementiert. Die Formatbezeichner "C" oder "G" werden darin unterstützt, um die Temperatur in Celsius anzuzeigen, der Formatbezeichner "F", um die Temperatur in Fahrenheit anzuzeigen, und der Formatbezeichner "KB", um die Temperatur in Kelvin anzuzeigen.

[!code-csharp[Conceptual.Formatting.Overview#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/iformattable.cs#12)]
[!code-vb[Conceptual.Formatting.Overview#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/iformattable.vb#12)]

Im folgenden Beispiel wird ein `Temperature`-Objekt instanziiert. Anschließend wird die <xref:System.Convert.ToString%2A> -Methode aufgerufen und mehrere zusammengesetzte Formatzeichenfolgen werden verwendet, um andere Zeichenfolgendarstellungen eines `Temperature` -Objekts zu erhalten. Die einzelnen Methoden rufen wiederum die <xref:System.IFormattable> -Implementierung der `Temperature` -Klasse auf.

[!code-csharp[Conceptual.Formatting.Overview#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/iformattable.cs#13)]
[!code-vb[Conceptual.Formatting.Overview#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/iformattable.vb#13)]

## <a name="composite-formatting"></a>Kombinierte Formatierung

Einige Methoden wie <xref:System.String.Format%2A?displayProperty=nameWithType> und <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType> unterstützen die kombinierte Formatierung. Eine kombinierte Formatzeichenfolge ist eine Vorlage, die verwendet wird, um eine einzelne Zeichenfolge zurückzugeben, die die Zeichenfolgendarstellung von 0 (null), einem oder mehreren Objekten beinhaltet. Jedes Objekt wird in der kombinierten Formatzeichenfolge durch ein indiziertes Formatelement dargestellt. Der Index des Formatelements entspricht der Position des Objekts, das es in der Parameterliste der Methode darstellt. Indizes sind nullbasiert. Beispielsweise wird im folgenden Aufruf der <xref:System.String.Format%2A?displayProperty=nameWithType>-Methode das erste Formatelement `{0:D}` durch die Zeichenfolgendarstellung von `thatDate` ersetzt. Das zweite Formatelement `{1}` wird durch die Zeichenfolgendarstellung `item1` ersetzt, und das dritte Formatelement `{2:C2}` wird durch die Zeichenfolgendarstellung von `item1.Value` ersetzt.

[!code-csharp[Conceptual.Formatting.Overview#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/composite1.cs#14)]
[!code-vb[Conceptual.Formatting.Overview#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/composite1.vb#14)]

Zusätzlich zum Ersetzen eines Formatelements durch die Zeichenfolgendarstellung seines entsprechenden Objekts können Sie mit Formatelementen auch Folgendes steuern:

- Die spezifische Art, in der ein Objekt als Zeichenfolge dargestellt wird, wenn das Objekt die <xref:System.IFormattable> -Schnittstelle implementiert und Formatzeichenfolgen unterstützt. Zu diesem Zweck geben Sie nach dem Index des Formatelements einen `:` (Doppelpunkt) ein, gefolgt von einer gültigen Formatzeichenfolge. Im vorherigen Beispiel wurde hierzu ein Datumswert mit der Formatzeichenfolge "d" (kurzes Datumsmuster) formatiert (z. B. `{0:d}`) und ein numerischer Wert mit der Formatzeichenfolge "C2" formatiert (z. B. `{2:C2}` ), um die Zahl als Währungswert mit zwei Dezimalstellen für Sekundenbruchteile darzustellen.

- Die Breite des Felds, das die Zeichenfolgendarstellung des Objekts enthält, und die Ausrichtung der Zeichenfolgendarstellung in diesem Feld. Hierzu geben Sie nach dem Index des Formatelements ein `,` (Komma) ein, gefolgt von der Feldbreite. Die Zeichenfolge wird rechtsbündig in dem Feld ausgerichtet, wenn die Feldbreite ein positiver Wert ist, und linksbündig, wenn die Feldbreite ein negativer Wert ist. Im folgenden Beispiel werden Datumswerte in einem 20 Zeichen breiten Feld linksbündig ausgerichtet, und Dezimalwerte mit einer Hinterkommastelle werden in einem 11 Zeichen breiten Feld rechtsbündig ausgerichtet.

     [!code-csharp[Conceptual.Formatting.Overview#22](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/composite2.cs#22)]
     [!code-vb[Conceptual.Formatting.Overview#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/composite2.vb#22)]

     Beachten Sie, dass, wenn sowohl die Ausrichtungszeichenfolge-Komponente als auch die Formatzeichenfolgen-Komponente vorhanden ist, die erste der letzteren vorausgeht (z. B. `{0,-20:g}`).

Weitere Informationen zur zusammengesetzten Formatierung finden Sie unter [Composite Formatting](../../../docs/standard/base-types/composite-formatting.md).

## <a name="custom-formatting-with-icustomformatter"></a>Benutzerdefinierte Formatierung mit ICustomFormatter

Zwei Methoden zur kombinierten Formatierung, <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> und <xref:System.Text.StringBuilder.AppendFormat%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>, enthalten auch einen Formatanbieterparameter, der die benutzerdefinierte Formatierung unterstützt. Wenn eine der beiden Formatierungsmethoden aufgerufen wird, übergibt sie ein <xref:System.Type> -Objekt, das eine <xref:System.ICustomFormatter> -Schnittstelle für die <xref:System.IFormatProvider.GetFormat%2A> -Methode des Formatanbieters darstellt. Die <xref:System.IFormatProvider.GetFormat%2A> -Methode ist dann dafür verantwortlich, die <xref:System.ICustomFormatter> -Implementierung zurückzugeben, die die benutzerdefinierte Formatierung bereitstellt.

Die <xref:System.ICustomFormatter> -Schnittstelle verfügt über eine einzelne Methode, <xref:System.ICustomFormatter.Format%28System.String%2CSystem.Object%2CSystem.IFormatProvider%29>, die für jedes Formatelement in einer zusammengesetzten Formatzeichenfolge automatisch von einer kombinierten Formatierungsmethode aufgerufen wird. Die <xref:System.ICustomFormatter.Format%28System.String%2CSystem.Object%2CSystem.IFormatProvider%29> -Methode verfügt über drei Parameter: eine Formatzeichenfolge, die das `formatString` -Argument in einem Formatelement darstellt, ein Objekt zum Formatieren und ein <xref:System.IFormatProvider> -Objekt, das Formatierungsdienste bereitstellt. In der Regel implementiert die Klasse, die <xref:System.ICustomFormatter> implementiert, auch <xref:System.IFormatProvider>; der letzte Parameter stellt daher einen Verweis auf die benutzerdefinierte Formatierungsklasse selbst dar. Die Methode gibt eine benutzerdefinierte formatierte Zeichenfolgendarstellung des Objekts zurück, das formatiert werden soll. Wenn die Methode das Objekt nicht formatieren kann, sollte ein NULL-Verweis (`Nothing` in Visual Basic) zurückgegeben werden.

Im folgenden Beispiel wird eine <xref:System.ICustomFormatter> -Implementierung mit dem Namen `ByteByByteFormatter` bereitgestellt, die ganzzahlige Werte als Sequenz von zweistelligen Hexadezimalwerten, gefolgt von einem Leerzeichen anzeigt.

[!code-csharp[Conceptual.Formatting.Overview#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/icustomformatter1.cs#15)]
[!code-vb[Conceptual.Formatting.Overview#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/icustomformatter1.vb#15)]

Im folgenden Beispiel werden mit der `ByteByByteFormatter` -Klasse Ganzzahlwerte formatiert. Beachten Sie, dass die <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> -Methode im zweiten Aufruf der <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> -Methode mehr als einmal aufgerufen wird, und dass der <xref:System.Globalization.NumberFormatInfo> -Standardanbieter im dritten Methodenaufruf verwendet wird, da die`ByteByByteFormatter.Format` -Methode die Formatzeichenfolge "N0" nicht erkennt und ein NULL-Verweis (`Nothing` in Visual Basic) ist.

[!code-csharp[Conceptual.Formatting.Overview#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/icustomformatter1.cs#16)]
[!code-vb[Conceptual.Formatting.Overview#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/icustomformatter1.vb#16)]

## <a name="related-topics"></a>Verwandte Themen

|Titel|Definition|
|-----------|----------------|
|[Standard Numeric Format Strings](../../../docs/standard/base-types/standard-numeric-format-strings.md)|Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen häufig verwendete Zeichenfolgenentsprechungen von numerischen Werten erstellt werden.|
|[Custom Numeric Format Strings](../../../docs/standard/base-types/custom-numeric-format-strings.md)|Beschreibt benutzerdefinierte Formatzeichenfolgen, die anwendungsspezifische Formate für numerische Werte erstellen.|
|[Standard Date and Time Format Strings](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)|Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen häufig verwendete Zeichenfolgenentsprechungen von <xref:System.DateTime> -Werten erstellt werden.|
|[Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)|Beschreibt benutzerdefinierte Formatzeichenfolgen, die anwendungsspezifische Formate für <xref:System.DateTime> -Werte erstellen.|
|[TimeSpan-Standardformatzeichenfolgen](../../../docs/standard/base-types/standard-timespan-format-strings.md)|Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen häufig verwendete Zeichenfolgenentsprechungen von Zeitintervallen erstellt werden.|
|[Benutzerdefinierte TimeSpan-Formatzeichenfolgen](../../../docs/standard/base-types/custom-timespan-format-strings.md)|Beschreibt benutzerdefinierte Formatzeichenfolgen, die anwendungsspezifische Formate für Zeitintervalle erstellen.|
|[Enumeration Format Strings](../../../docs/standard/base-types/enumeration-format-strings.md)|Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen Zeichenfolgenentsprechungen von Enumerationswerten erstellt werden.|
|[Kombinierte Formatierung](../../../docs/standard/base-types/composite-formatting.md)|Beschreibt die Einbettung eines oder mehrerer formatierter Werte in eine Zeichenfolge. Die Zeichenfolge kann anschließend in der Konsole angezeigt oder in einen Stream geschrieben werden.|
|[Durchführen von Formatierungsvorgängen](../../../docs/standard/base-types/performing-formatting-operations.md)|Enthält Themen, in denen schrittweise Anleitungen zum Ausführen bestimmter Formatierungsvorgänge vorgestellt werden.|
|[Parsing Strings](../../../docs/standard/base-types/parsing-strings.md)|Beschreibt, wie Objekte mit den Werten initialisiert werden, die durch Zeichenfolgenentsprechungen dieser Objekte beschrieben werden. Das Verarbeiten ist die Umkehroperation zum Formatieren.|

## <a name="reference"></a>Referenz

- <xref:System.IFormattable?displayProperty=nameWithType>
- <xref:System.IFormatProvider?displayProperty=nameWithType>
- <xref:System.ICustomFormatter?displayProperty=nameWithType>

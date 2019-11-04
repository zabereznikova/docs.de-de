---
title: 'Vorgehensweise: Extrahieren des Wochentags aus einem bestimmten Datum'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [.NET Framework], dates
- DateTime.DayOfWeek property
- DateTime.ToString method
- dates [.NET Framework], retrieving week information
- DateTimeOffset.DayOfWeek property
- dates [.NET Framework], day of week
- Weekday function
- day of week [.NET Framework]
- extracting day of week
- weekday names
- WeekdayName function
- numbers [.NET Framework], day of week
- formatting [.NET Framework], time
- DateTimeOffset.ToString method
- full weekday names
ms.assetid: 1c9bef76-5634-46cf-b91c-9b9eb72091d7
ms.openlocfilehash: 771bd0276310eecb534fb80836faadb1a8aa10bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084201"
---
# <a name="how-to-extract-the-day-of-the-week-from-a-specific-date"></a>Vorgehensweise: Extrahieren des Wochentags aus einem bestimmten Datum
Mit .NET Framework ist es einfach, den Wochentag für ein bestimmtes Datum festzulegen und den lokalisierten Namen eines Wochentags für ein bestimmtes Datum anzuzeigen. Ein Aufzählungswert, der den einem bestimmten Datum entsprechenden Wochentag anzeigt, ist über die <xref:System.DateTime.DayOfWeek%2A>- oder die <xref:System.DateTimeOffset.DayOfWeek%2A>-Eigenschaft verfügbar. Dagegen ist das Abrufen des Namens eines Wochentags ein Formatierungsvorgang, der durch das Aufrufen einer Formatierungsmethode ausgeführt werden kann, wie z. B. der `ToString`-Methode eines Datums- oder Zeitwertes oder der <xref:System.String.Format%2A?displayProperty=nameWithType>-Methode. In diesem Thema wird gezeigt, wie diese Formatierungsvorgänge ausgeführt werden.  
  
### <a name="to-extract-a-number-indicating-the-day-of-the-week-from-a-specific-date"></a>Extrahieren einer Zahl, die den Wochentag anzeigt, aus einem bestimmten Datum  
  
1. Wenn Sie mit der Zeichenfolgendarstellung eines Datums arbeiten, konvertieren Sie sie mithilfe der statischen <xref:System.DateTime>-Methode oder <xref:System.DateTimeOffset>-Methode in einen <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>-Wert oder einen <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>-Wert.  
  
2. Verwenden Sie die <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType>- oder die <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType>-Eigenschaft, um einen <xref:System.DayOfWeek>-Wert abzurufen, der den Wochentag anzeigt.  
  
3. Falls nötig, wandeln Sie den <xref:System.DayOfWeek>-Wert in eine Ganzzahl um (in C#) oder konvertieren Sie ihn (in Visual Basic).  
  
 Das folgende Beispiel zeigt eine Ganzzahl, die den Wochentag eines bestimmten Datums anzeigt.  
  
 [!code-csharp[Formatting.Howto.WeekdayName#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/weekdaynumber7.cs#7)]
 [!code-vb[Formatting.Howto.WeekdayName#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/weekdaynumber7.vb#7)]  
  
### <a name="to-extract-the-abbreviated-weekday-name-from-a-specific-date"></a>Extrahieren des abgekürzten Wochentagsnamens aus einem bestimmten Datum  
  
1. Wenn Sie mit der Zeichenfolgendarstellung eines Datums arbeiten, konvertieren Sie sie mithilfe der statischen <xref:System.DateTime>-Methode oder <xref:System.DateTimeOffset>-Methode in einen <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>-Wert oder einen <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>-Wert.  
  
2. Sie können den abgekürzten Wochentagsnamen der aktuellen Kultur oder einer bestimmten Kultur extrahieren:  
  
    1. Um den abgekürzten Wochentagsnamen der aktuellen Kultur zu extrahieren, rufen Sie die <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType>- oder <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType>-Instanzmethode des Datums- oder Zeitwerts auf und übergeben Sie die Zeichenfolge "ddd" als `format`-Parameter. Im folgenden Beispiel wird das Aufrufen der <xref:System.DateTime.ToString%28System.String%29>-Methode veranschaulicht.  
  
         [!code-csharp[Formatting.Howto.WeekdayName#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/abbrname1.cs#1)]
         [!code-vb[Formatting.Howto.WeekdayName#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/abbrname1.vb#1)]  
  
    2. Um den abgekürzten Wochentagsnamen einer bestimmten Kultur zu extrahieren, rufen Sie die <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>- oder <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>-Instanzmethode des Datums- oder Zeitwerts auf. Übergeben Sie die Zeichenfolge "ddd" als `format`-Parameter. Übergeben Sie entweder ein <xref:System.Globalization.CultureInfo>- oder ein <xref:System.Globalization.DateTimeFormatInfo>-Objekt, das die Kultur darstellt, deren Wochentagsnamen Sie abrufen wollen, als `provider`-Parameter. Der folgende Code veranschaulicht einen Aufruf der <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29>-Methode mit einem <xref:System.Globalization.CultureInfo>-Objekt, das die fr-FR-Kultur darstellt.  
  
         [!code-csharp[Formatting.Howto.WeekdayName#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/abbrname2.cs#2)]
         [!code-vb[Formatting.Howto.WeekdayName#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/abbrname2.vb#2)]  
  
### <a name="to-extract-the-full-weekday-name-from-a-specific-date"></a>Extrahieren des vollen Wochentagsnamens aus einem bestimmten Datum  
  
1. Wenn Sie mit der Zeichenfolgendarstellung eines Datums arbeiten, konvertieren Sie sie mithilfe der statischen <xref:System.DateTime>-Methode oder <xref:System.DateTimeOffset>-Methode in einen <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>-Wert oder einen <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>-Wert.  
  
2. Sie können den vollen Wochentagsnamen der aktuellen Kultur oder einer bestimmten Kultur extrahieren:  
  
    1. Um den Wochentagsnamen der aktuellen Kultur zu extrahieren, rufen Sie die <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType>- oder <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType>-Instanzmethode des Datums- oder Zeitwerts auf und übergeben Sie die Zeichenfolge "dddd" als `format`-Parameter. Im folgenden Beispiel wird das Aufrufen der <xref:System.DateTime.ToString%28System.String%29>-Methode veranschaulicht.  
  
         [!code-csharp[Formatting.Howto.WeekdayName#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/fullname4.cs#4)]
         [!code-vb[Formatting.Howto.WeekdayName#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/fullname4.vb#4)]  
  
    2. Um den Wochentagsnamen einer bestimmten Kultur zu extrahieren, rufen Sie die <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>- oder <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>-Instanzmethode des Datums- oder Zeitwerts auf. Übergeben Sie die Zeichenfolge "dddd" als `format`-Parameter. Übergeben Sie entweder ein <xref:System.Globalization.CultureInfo>- oder ein <xref:System.Globalization.DateTimeFormatInfo>-Objekt, das die Kultur darstellt, deren Wochentagsnamen Sie abrufen wollen, als `provider`-Parameter. Der folgende Code veranschaulicht einen Aufruf der <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29>-Methode mit einem <xref:System.Globalization.CultureInfo>-Objekt, das die es-ES-Kultur darstellt.  
  
         [!code-csharp[Formatting.Howto.WeekdayName#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/fullname5.cs#5)]
         [!code-vb[Formatting.Howto.WeekdayName#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/fullname5.vb#5)]  
  
## <a name="example"></a>Beispiel  
 Das Beispiel veranschaulicht Aufrufe der <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType>- und <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType>-Eigenschaften sowie der <xref:System.DateTime.ToString%2A?displayProperty=nameWithType>- und der <xref:System.DateTimeOffset.ToString%2A?displayProperty=nameWithType>-Methode zum Abrufen der Nummer, die den Wochentag, den abgekürzten Wochentagsnamen und den vollen Wochentagsnamen für ein bestimmtes Datum darstellt.  
  
 [!code-csharp[Formatting.Howto.WeekdayName#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/example6.cs#6)]
 [!code-vb[Formatting.Howto.WeekdayName#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/example6.vb#6)]  
  
 Einzelne Sprachen verfügen ggf. über Funktionen, die die von .NET Framework zur Verfügung gestellte Funktionalität duplizieren oder ergänzen. Visual Basic verfügt beispielsweise über zwei solcher Funktionen:  
  
- `Weekday`, die eine Zahl zurückgibt, die den Wochentag eines bestimmten Datums anzeigt. Sie betrachtet den Ordinalwert des ersten Wochentags als eins, während die <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType>-Eigenschaft ihn als null betrachtet.  
  
- `WeekdayName`, die den Namen des Wochentags in der aktuellen Kultur zurückgibt, der der Nummer eines bestimmten Wochentags entspricht.  
  
 Das folgende Beispiel veranschaulicht die Verwendung der `Weekday`- und `WeekdayName`-Funktionen in Visual Basic.  
  
 [!code-vb[Formatting.HowTo.WeekdayName#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/example9.vb#9)]  
  
 Sie können auch den von der <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType>-Eigenschaft zurückgegebenen Wert verwenden, um den Wochentagsnamen eines bestimmten Datums abzurufen. Dies erfordert lediglich einen Aufruf der <xref:System.Enum.ToString%2A>-Methode auf dem von der Eigenschaft zurückgegebenen <xref:System.DayOfWeek>-Wert. Diese Vorgehensweise erzeugt jedoch nicht den lokalisierten Wochentagsnamen für die aktuelle Kultur, wie das folgende Beispiel zeigt.  
  
 [!code-csharp[Formatting.HowTo.WeekdayName#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/Howto1.cs#8)]
 [!code-vb[Formatting.HowTo.WeekdayName#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/Howto1.vb#8)]  
  
## <a name="see-also"></a>Siehe auch

- [Durchführen von Formatierungsvorgängen](../../../docs/standard/base-types/performing-formatting-operations.md)
- [Standard Date and Time Format Strings](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)
- [Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)

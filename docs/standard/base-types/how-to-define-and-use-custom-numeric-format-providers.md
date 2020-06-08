---
title: 'Vorgehensweise: Definieren und Verwenden von benutzerdefinierten numerischen Formatanbietern'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- custom numeric format strings
- numbers [.NET Framework], custom numeric format strings
- displaying date and time data
- format providers [.NET Framework]
- custom format strings
ms.assetid: a281bfbf-6596-45ed-a2d6-3782d535ada2
ms.openlocfilehash: d12899fff7d9e6cb63728ba0b160b70fa2a41a1a
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290512"
---
# <a name="how-to-define-and-use-custom-numeric-format-providers"></a>Vorgehensweise: Definieren und Verwenden von benutzerdefinierten numerischen Formatanbietern
.NET Framework ermöglicht eine umfangreiche Steuerung der Zeichenfolgendarstellung numerischer Werte. Die folgenden Funktionen für die Anpassung des Formats numerischer Werte werden unterstützt:  
  
- Standardmäßige Zahlenformatzeichenfolgen, die einen vordefinierten Satz an Formaten für die Konvertierung von Zahlen in ihre Zeichenfolgendarstellung bereitstellen. Sie können diese mit jeder Zahlenformatierungsmethode verwenden, die über einen `format`-Parameter verfügt, z.B. <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType>. Weitere Informationen finden Sie unter [Standardmäßige Zahlenformatzeichenfolgen](standard-numeric-format-strings.md).  
  
- Benutzerdefinierte Zahlenformatzeichenfolgen, die einen Satz von Symbolen bereitstellen, die kombiniert werden können, um benutzerdefinierte Zahlenformatbezeichner zu definieren. Sie können auch mit jeder Zahlenformatierungsmethode verwendet werden, die über einen `format`-Parameter verfügt, z.B. <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType>. Weitere Informationen finden Sie unter [Benutzerdefinierte Zahlenformatzeichenfolgen](custom-numeric-format-strings.md).  
  
- Benutzerdefinierte <xref:System.Globalization.CultureInfo>- oder <xref:System.Globalization.NumberFormatInfo>-Objekte, die die beim Anzeigen der Zeichenfolgendarstellungen numerischer Werte verwendeten Symbole und Formatmuster definieren. Sie können diese mit jeder Zahlenformatierungsmethode verwenden, die über einen `provider`-Parameter verfügt, z.B. <xref:System.Int32.ToString%2A>. Üblicherweise wird der `provider`-Parameter verwendet, um eine kulturspezifische Formatierung anzugeben.  
  
 In einigen Fällen (z.B. wenn eine Anwendung eine formatierte Kontonummer, eine ID oder eine Postleitzahl anzeigen muss) sind diese drei Techniken nicht geeignet. .NET Framework ermöglicht Ihnen auch die Definition eines Formatierungsobjekts, bei dem es sich weder um ein <xref:System.Globalization.CultureInfo>-Objekt noch um ein <xref:System.Globalization.NumberFormatInfo>-Objekt handelt, um zu bestimmen, wie ein numerischer Wert formatiert wird. Dieses Thema stellt eine Schrittanleitung für die Implementierung eines solchen Objekts bereit und bietet ein Beispiel, das Telefonnummern formatiert.  
  
### <a name="to-define-a-custom-format-provider"></a>Definieren eines benutzerdefinierten Formatanbieters  
  
1. Definieren Sie eine Klasse, die die <xref:System.IFormatProvider>- und <xref:System.ICustomFormatter>-Schnittstelle implementiert.  
  
2. Implementieren Sie die <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType>-Methode. <xref:System.IFormatProvider.GetFormat%2A> ist eine Rückrufmethode, die von der Formatierungsmethode (z.B. der <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>-Methode) aufgerufen wird, um das Objekt abzurufen, das tatsächlich für die benutzerdefinierte Formatierung zuständig ist. Eine typische Implementierung von <xref:System.IFormatProvider.GetFormat%2A> führt Folgendes aus:  
  
    1. Bestimmt, ob das als Methodenparameter übergebene <xref:System.Type>-Objekt eine <xref:System.ICustomFormatter>-Schnittstelle darstellt.  
  
    2. Wenn der Parameter die <xref:System.ICustomFormatter>-Schnittstelle tatsächlich darstellt, gibt <xref:System.IFormatProvider.GetFormat%2A> ein Objekt zurück, das die für die benutzerdefinierte Formatierung zuständige <xref:System.ICustomFormatter>-Schnittstelle implementiert. Üblicherweise gibt das benutzerdefinierte Formatierungsobjekt sich selbst zurück.  
  
    3. Wenn der Parameter die <xref:System.ICustomFormatter>-Schnittstelle nicht darstellt, gibt <xref:System.IFormatProvider.GetFormat%2A>`null` zurück.  
  
3. Implementieren Sie die <xref:System.ICustomFormatter.Format%2A>-Methode. Diese Methode wird von der <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>-Methode aufgerufen und ist für die Rückgabe der Zeichenfolgendarstellung einer Zahl zuständig. Die Implementierung der Methode umfasst üblicherweise Folgendes:  
  
    1. Stellen Sie optional sicher, dass die Methode dazu in der Lage sein soll, Formatierungsdienste bereitzustellen, indem Sie den `provider`-Parameter untersuchen. Bei Formatierungsobjekten, die sowohl <xref:System.IFormatProvider> als auch <xref:System.ICustomFormatter> implementieren, umfasst dies das Testen des `provider`-Parameters auf Gleichheit mit dem aktuellen Formatierungsobjekt.  
  
    2. Bestimmen Sie, ob das Formatierungsobjekt benutzerdefinierte Formatbezeichner unterstützen soll. (Beispielsweise könnte ein Formatbezeichner „N“ angeben, dass eine US-amerikanische Telefonnummer im NANP-Format (Nordamerikanischer Nummerierungsplan) ausgegeben werden soll, und ein Bezeichner „I“ könnte eine Ausgabe im Format der ITU-T-Empfehlung E.123 angeben.) Wenn Formatbezeichner verwendet werden, muss die Methode den angegebenen Formatbezeichner verarbeiten. Der Bezeichner wird im `format`-Parameter der Methode übergeben. Wenn kein Bezeichner vorhanden ist, lautet der Wert des `format`-Parameters <xref:System.String.Empty?displayProperty=nameWithType>.  
  
    3. Rufen Sie den numerischen Wert ab, der als `arg`-Parameter der Methode übergeben wurde. Führen Sie alle Änderungen durch, die notwendig sind, um den Wert in seine Zeichenfolgendarstellung zu konvertieren.  
  
    4. Geben Sie die Zeichenfolgendarstellung des `arg`-Parameters zurück.  
  
### <a name="to-use-a-custom-numeric-formatting-object"></a>Verwenden eines benutzerdefinierten Zahlenformatierungsobjekts  
  
1. Erstellen Sie eine neue Instanz der benutzerdefinierten Formatierungsklasse.  
  
2. Rufen Sie die <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>-Formatierungsmethode auf, und übergeben Sie das benutzerdefinierte Formatierungsobjekt, den Formatierungsbezeichner (oder <xref:System.String.Empty?displayProperty=nameWithType>, falls kein Bezeichner verwendet wird) und den numerischen Wert, der formatiert werden soll.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert einen benutzerdefinierten Zahlenformatanbieter namens `TelephoneFormatter`, der eine Zahl, die eine US-amerikanische Telefonnummer darstellt, in das entsprechende NANP- oder E.123-Format konvertiert. Die Methode verarbeitet zwei Formatbezeichner: „N“ (zur Ausgabe des NANP-Formats) und „I“ (zur Ausgabe des internationalen E.123-Formats).  
  
 [!code-csharp[Formatting.HowTo.NumericValue#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#1)]
 [!code-vb[Formatting.HowTo.NumericValue#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#1)]  
  
 Der benutzerdefinierte Zahlenformatanbieter kann nur mit der <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>-Methode verwendet werden. Alle anderen Überladungen der Zahlenformatierungsmethoden (z.B. `ToString`), die einen Parameter des Typs <xref:System.IFormatProvider> aufweisen, übergeben der <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType>-Implementierung ein <xref:System.Type>-Objekt, das den <xref:System.Globalization.NumberFormatInfo>-Typ darstellt. Im Gegenzug erwarten sie, dass die Methode ein <xref:System.Globalization.NumberFormatInfo>-Objekt zurückgibt. Wenn dies nicht der Fall ist, wird der benutzerdefinierte Zahlenformatanbieter ignoriert und stattdessen das <xref:System.Globalization.NumberFormatInfo>-Objekt für die aktuelle Kultur verwendet. Im Beispiel verarbeitet die `TelephoneFormatter.GetFormat`-Methode die Möglichkeit, dass sie fälschlicherweise an eine Zahlenformatierungsmethode übergeben wurde, indem sie den Methodenparameter untersucht und `null` zurückgibt, wenn dieser einen anderen Typ als <xref:System.ICustomFormatter> darstellt.  
  
 Wenn ein benutzerdefinierter Zahlenformatanbieter einen Satz von Formatbezeichnern unterstützt, stellen Sie sicher, dass Sie ein Standardverhalten einrichten, falls in dem Formatelement, das im <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>-Methodenaufruf verwendet wird, kein Formatbezeichner bereitgestellt wird. Im Beispiel ist „N“ der Standardformatbezeichner. Dadurch kann eine Zahl in eine formatierte Telefonnummer konvertiert werden, indem ein expliziter Formatbezeichner bereitgestellt wird. Das folgende Beispiel veranschaulicht einen solchen Methodenaufruf.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#2)]
 [!code-vb[Formatting.HowTo.NumericValue#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#2)]  
  
 Es ermöglicht die Konvertierung aber auch, falls kein Formatbezeichner vorhanden ist. Das folgende Beispiel veranschaulicht einen solchen Methodenaufruf.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#3)]
 [!code-vb[Formatting.HowTo.NumericValue#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#3)]  
  
 Wenn kein Standardformatbezeichner definiert ist, muss Ihre Implementierung der <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType>-Methode einen Code wie den folgenden beinhalten, damit .NET eine Formatierung bereitstellen kann, die von Ihrem Code nicht unterstützt wird.  
  
 [!code-csharp[System.ICustomFormatter.Format#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.ICustomFormatter.Format/cs/format.cs#1)]
 [!code-vb[System.ICustomFormatter.Format#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.ICustomFormatter.Format/vb/Format.vb#1)]  
  
 In diesem Beispiel dient die Methode, die <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> implementiert, als eine Rückrufmethode der <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>-Methode. Daher untersucht diese Methode den `formatProvider`-Parameter, um zu ermitteln, ob dieser einen Verweis auf das aktuelle `TelephoneFormatter`-Objekt enthält. Die Methode kann jedoch auch direkt aus dem Code aufgerufen werden. In diesem Fall können Sie den `formatProvider`-Parameter verwenden, um ein <xref:System.Globalization.CultureInfo>- oder <xref:System.Globalization.NumberFormatInfo>-Objekt bereitzustellen, das kulturspezifische Formatierungsinformationen bereitstellt.

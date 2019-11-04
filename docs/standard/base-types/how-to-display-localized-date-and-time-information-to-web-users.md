---
title: 'Vorgehensweise: Anzeigen lokalisierter Datums- und Uhrzeitangaben für Webbenutzer'
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- formatting [.NET Framework], dates
- parsing strings [.NET Framework], date and time strings
- localization [.NET Framework], date and time displays
- formatting [.NET Framework], localized data
- displaying date and time data
- localized date displays [.NET Framework]
ms.assetid: 377fe93c-32be-421a-a30a-be639a46ede8
dev_langs:
- csharp
- vb
ms.openlocfilehash: 51142a168aba4408e6ce550a032960c4df6c3ae7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138734"
---
# <a name="how-to-display-localized-date-and-time-information-to-web-users"></a>Vorgehensweise: Anzeigen lokalisierter Datums- und Uhrzeitangaben für Webbenutzer
Da eine Webseite überall in der Welt angezeigt werden kann, sollten Vorgänge, die Datums- und Uhrzeitwerte analysieren und formatieren, bei der Interaktion mit dem Benutzer nicht von einem Standardformat (am häufigsten das Format der lokalen Kultur des Webservers) abhängen. Stattdessen sollten Webformulare, die vom Benutzer eingegebene Datums- und Uhrzeitzeichenfolgen behandeln, die Zeichenfolgen gemäß der bevorzugten Kultur des Benutzers analysieren. Entsprechend sollten Datums- und Uhrzeitdaten dem Benutzer in einem Format angezeigt werden, das seiner Kultur entspricht. In diesem Thema wird gezeigt, wie Sie dazu vorgehen müssen.  
  
## <a name="to-parse-date-and-time-strings-input-by-the-user"></a>So analysieren Sie vom Benutzer eingegebene Datums- und Uhrzeitzeichenfolgen  
  
1. Bestimmen Sie, ob das von der <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>-Eigenschaft zurückgegebene Zeichenfolgenarray gefüllt ist. Wenn dies nicht der Fall ist, fahren Sie mit Schritt 6 fort.  
  
2. Wenn das von der <xref:System.Web.HttpRequest.UserLanguages%2A>-Eigenschaft zurückgegebene Zeichenfolgenarray aufgefüllt ist, rufen Sie sein erstes Element ab. Das erste Element gibt die Standardeinstellung des Benutzers oder seine bevorzugte Sprache und Region an.  
  
3. Instanziieren Sie ein <xref:System.Globalization.CultureInfo>-Objekt durch Aufrufen des <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType>-Konstruktors, das die bevorzugte Kultur des Benutzers darstellt.  
  
4. Rufen Sie entweder die `TryParse`- oder `Parse`-Methode des <xref:System.DateTime>- oder <xref:System.DateTimeOffset>-Typs ab, um die Konvertierung zu versuchen. Verwenden Sie eine Überladung der `TryParse`- oder `Parse`-Methode mit einem `provider`-Parameter, und übergeben Sie sie an eines der folgenden Objekte:  
  
    - Das in Schritt 3 erstellte <xref:System.Globalization.CultureInfo>-Objekt  
  
    - Das von der <xref:System.Globalization.CultureInfo.DateTimeFormat%2A>-Eigenschaft zurückgegebene <xref:System.Globalization.DateTimeFormatInfo>-Objekt des in Schritt 3 erstellten <xref:System.Globalization.CultureInfo>-Objekts  
  
5. Wenn bei der Konvertierung ein Fehler auftritt, wiederholen Sie die Schritte 2 bis 4 für jedes verbleibende Element im von der <xref:System.Web.HttpRequest.UserLanguages%2A>-Eigenschaft zurückgegebenen Zeichenfolgenarray.  
  
6. Wenn bei der Konvertierung weiterhin ein Fehler auftritt, oder das von der <xref:System.Web.HttpRequest.UserLanguages%2A>-Eigenschaft zurückgegebene Zeichenfolgenarray leer ist, analysieren Sie die Zeichenfolge mit der invarianten Kultur, die durch die <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>-Eigenschaft zurückgegeben wird.  
  
## <a name="to-parse-the-local-date-and-time-of-the-users-request"></a>So analysieren Sie lokales Datum und Ortszeit der Anforderung des Benutzers  
  
1. Fügen Sie einem Webformular ein <xref:System.Web.UI.WebControls.HiddenField>-Steuerelement hinzu.  
  
2. Erstellen Sie eine JavaScript-Funktion, die das `onClick`-Ereignis einer `Submit`-Schaltfläche behandelt, indem sie aktuelles Datum und aktuelle Uhrzeit sowie den Offset zwischen der lokalen Zeitzone und der koordinierten Weltzeit (UTC) in die <xref:System.Web.UI.WebControls.HiddenField.Value%2A>-Eigenschaft schreibt. Verwenden Sie ein Trennzeichen (z.B. ein Semikolon), um die beiden Komponenten der Zeichenfolge zu trennen.  
  
3. Verwenden Sie das <xref:System.Web.UI.Control.PreRender>-Ereignis des Webformulars, um die Funktion durch Übergeben des Skripttexts an die <xref:System.Web.UI.ClientScriptManager.RegisterClientScriptBlock%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType>-Methode in den HTML-Ausgabestream einzufügen.  
  
4. Verbinden Sie den Ereignishandler durch Übergabe des Namens der JavaScript-Funktion an das `OnClientClick`-Attribut der `Submit`-Schaltfläche mit dem `onClick`-Ereignis der `Submit`-Schaltfläche.  
  
5. Erstellen Sie einen Ereignishandler für das <xref:System.Web.UI.WebControls.Button.Click>-Ereignis der `Submit`-Schaltfläche.  
  
6. Bestimmen Sie im Ereignishandler, ob das von der <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>-Eigenschaft zurückgegebene Zeichenfolgenarray gefüllt ist. Wenn dies nicht der Fall ist, fahren Sie mit Schritt 14 fort.  
  
7. Wenn das von der <xref:System.Web.HttpRequest.UserLanguages%2A>-Eigenschaft zurückgegebene Zeichenfolgenarray gefüllt ist, rufen Sie sein erstes Element ab. Das erste Element gibt die Standardeinstellung des Benutzers oder seine bevorzugte Sprache und Region an.  
  
8. Instanziieren Sie ein <xref:System.Globalization.CultureInfo>-Objekt durch Aufrufen des <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType>-Konstruktors, das die bevorzugte Kultur des Benutzers darstellt.  
  
9. Übergeben Sie die Zeichenfolge, die der <xref:System.Web.UI.WebControls.HiddenField.Value%2A>-Eigenschaft zugewiesen ist, der <xref:System.String.Split%2A>-Methode, um die Zeichenfolgendarstellung des lokalen Datums und der Ortszeit des Benutzers und die Zeichenfolgendarstellung des Offsets der lokalen Zeitzone des Benutzers in separaten Arrayelementen zu speichern.  
  
10. Rufen Sie entweder die <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>- oder <xref:System.DateTime.TryParse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%2CSystem.DateTime%40%29?displayProperty=nameWithType>-Methode zum Konvertieren von Datum und Uhrzeit der Anforderung des Benutzers in einen <xref:System.DateTime>-Wert auf. Verwenden Sie eine Überladung der Methode mit einem `provider`-Parameter, und übergeben Sie sie an eines der folgenden Objekte:  
  
    - Das in Schritt 8 erstellte <xref:System.Globalization.CultureInfo>-Objekt.  
  
    - Das von der <xref:System.Globalization.CultureInfo.DateTimeFormat%2A>-Eigenschaft zurückgegebene <xref:System.Globalization.DateTimeFormatInfo>-Objekt des in Schritt 8 erstellten <xref:System.Globalization.CultureInfo>-Objekts.  
  
11. Wenn beim Analysevorgang in Schritt 10 ein Fehler auftritt, fahren Sie mit Schritt 13 fort. Rufen Sie andernfalls die <xref:System.UInt32.Parse%28System.String%29?displayProperty=nameWithType>-Methode auf, um die Zeichenfolgendarstellung des Offsets der Zeitzone des Benutzers in eine ganze Zahl zu konvertieren.  
  
12. Instanziieren Sie ein <xref:System.DateTimeOffset>-Objekt durch Aufrufen des <xref:System.DateTimeOffset.%23ctor%28System.DateTime%2CSystem.TimeSpan%29?displayProperty=nameWithType>-Konstruktors, das die Ortszeit des Benutzers darstellt.  
  
13. Wenn bei der Konvertierung in Schritt 10 ein Fehler auftritt, wiederholen Sie die Schritte 7 bis 12 für jedes verbleibende Element im von der <xref:System.Web.HttpRequest.UserLanguages%2A>-Eigenschaft zurückgegebenen Zeichenfolgenarray.  
  
14. Wenn bei der Konvertierung weiterhin ein Fehler auftritt, oder das von der <xref:System.Web.HttpRequest.UserLanguages%2A>-Eigenschaft zurückgegebene Zeichenfolgenarray leer ist, analysieren Sie die Zeichenfolge mit der invarianten Kultur, die durch die <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>-Eigenschaft zurückgegeben wird. Wiederholen Sie dann die Schritte 7 bis 12.  
  
 Das Ergebnis ist ein <xref:System.DateTimeOffset>-Objekt, das die Ortszeit des Benutzers auf Ihrer Webseite darstellt. Sie können dann die entsprechende UTC durch Aufrufen der <xref:System.DateTimeOffset.ToUniversalTime%2A>-Methode bestimmen. Sie können das entsprechende Datum und die Uhrzeit auch durch Aufrufen der <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>-Methode und Übergabe eines Werts von <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> als Zeitzone, in die die Uhrzeit konvertiert werden soll, auf dem Webserver bestimmen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel enthält die HTML-Quelle und den Code für ein ASP.NET-Webformular, das den Benutzer auffordert, einen Wert für Datum und Uhrzeit einzugeben. Ein clientseitiges Skript schreibt auch Informationen über das lokale Datum und die Uhrzeit der Anforderung des Benutzers sowie den Offset zwischen der Zeitzone des Benutzers und UTC in ein ausgeblendetes Feld. Diese Informationen werden dann durch den Server analysiert, der eine Webseite zurückgibt, die die Eingabe des Benutzers angezeigt. Es werden auch Datum und Uhrzeit der Anforderung des Benutzers unter Verwendung von Ortszeit des Benutzers, Uhrzeit auf dem Server und UTC angezeigt.  
  
 [!code-aspx-csharp[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/cs/GetDateInfo.aspx#1)]
 [!code-aspx-vb[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/vb/GetDateInfo.aspx#1)]
  
 Das clientseitige Skript ruft die JavaScript-Methode `toLocaleString` auf. Dies erzeugt eine Zeichenfolge, die den Formatierungskonventionen des Gebietsschemas des Benutzers entspricht, das eher erfolgreich auf dem Server analysiert werden kann.  
  
 Zum Füllen der <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>-Eigenschaft kommen die Kulturnamen infrage, die sich in den `Accept-Language`-Headern befinden, die in einer HTTP-Anforderung enthalten sind. Allerdings sind nicht in den Anforderungen aller Browser `Accept-Language`-Header enthalten, und die Benutzer können die Header auch vollständig unterdrücken. Daher ist es wichtig, dass bei der Analyse der Benutzereingabe eine Fallbackkultur verfügbar ist. In der Regel ist die Fallbackkultur die von <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> zurückgegebene invariante Kultur. Benutzer können für den Internet Explorer auch Kulturnamen bereitstellen, die sie in ein Textfeld eingeben, was die Gefahr mit sich bringt, dass die Kulturnamen möglicherweise nicht gültig sind. Daher ist es wichtig, bei der Instanziierung eines <xref:System.Globalization.CultureInfo>-Objekts eine Ausnahmebehandlung zu verwenden.  
  
 Beim Abrufen durch eine vom Internet Explorer übermittelte HTTP-Anforderung wird das <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>-Array in der durch die Benutzervoreinstellung vorgegebenen Reihenfolge aufgefüllt. Das erste Element im Array enthält den Namen der primären Kultur/Region des Benutzers. Wenn das Array zusätzliche Elemente enthält, weist der Internet Explorer ihnen nach dem Zufallsprinzip einen Qualitätsspezifizierer zu, der durch ein Semikolon vom Namen der Kultur getrennt wird. Beispielsweise kann ein Eintrag für die Kultur „fr-FR“ das Format `fr-FR;q=0.7` aufweisen.  
  
 Im Beispiel wird der <xref:System.Globalization.CultureInfo.%23ctor%2A>-Konstruktor mit seinem auf `false` festgelegten `useUserOverride`-Parametersatz zum Erstellen eines neuen <xref:System.Globalization.CultureInfo>-Objekts aufgerufen. Wenn der Kulturname der Standardkulturname auf dem Server ist, wird dadurch sichergestellt, dass das vom Klassenkonstruktor erstellte neue <xref:System.Globalization.CultureInfo>-Objekt die Standardeinstellungen einer Kultur enthält und keine mit der Anwendung **Regions- und Sprachoptionen** des Servers überschriebenen Einstellungen widerspiegelt. Es ist unwahrscheinlich, dass die Werte überschriebener Einstellungen auf dem Server auf dem System des Benutzers vorhanden sind oder in der Eingabe des Benutzers widergespiegelt werden.  
  
 Da in diesem Beispiel zwei Zeichenfolgendarstellungen eines Datums und einer Uhrzeit (eine Eingabe vom Benutzer, die andere im ausgeblendeten Feld gespeichert) analysiert werden, werden die <xref:System.Globalization.CultureInfo>-Objekte definiert, die möglicherweise im voraus erforderlich sind. Es wird ein Array von <xref:System.Globalization.CultureInfo>-Objekten erstellt, das um eins größer ist als die Anzahl der von der <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>-Eigenschaft zurückgegebenen Elemente. Dann wird für jede Sprachen-/Regionszeichenfolge ein <xref:System.Globalization.CultureInfo>-Objekt instanziiert und darüber hinaus ein <xref:System.Globalization.CultureInfo>-Objekt, das <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> darstellt.  
  
 Ihr Code kann entweder die <xref:System.DateTime.Parse%2A>- oder <xref:System.DateTime.TryParse%2A>-Methode zum Konvertieren der Zeichenfolgendarstellung eines Datums und einer Uhrzeit des Benutzers in einen <xref:System.DateTime>-Wert aufrufen. Wiederholte an eine Analysemethode gerichtete Aufrufe können für einen einzelnen Analysevorgang erforderlich sein. Daher ist die <xref:System.DateTime.TryParse%2A>-Methode besser, weil sie `false` zurückgibt, wenn bei einem Analysevorgang ein Fehler auftritt. Im Gegensatz dazu kann das Behandeln wiederholter Ausnahmen, die ggf. von der <xref:System.DateTime.Parse%2A>-Methode ausgelöst werden, ein sehr ressourcenintensiver Vorgang in einer Webanwendung sein.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um den Code zu kompilieren, erstellen Sie eine ASP.NET-Webseite ohne CodeBehind. Anschließend kopieren Sie das Beispiel in die Webseite, damit es den vorhandenen Code ersetzt. Die ASP.NET-Webseite sollte folgende Steuerelemente enthalten:  
  
- Ein <xref:System.Web.UI.WebControls.Label>-Steuerelement, auf das nicht im Code verwiesen wird. Legen Sie seine <xref:System.Web.UI.WebControls.TextBox.Text%2A>-Eigenschaft auf „Geben Sie eine Zahl ein:“ fest.  
  
- Ein <xref:System.Web.UI.WebControls.TextBox>-Steuerelement namens `DateString`.  
  
- Ein <xref:System.Web.UI.WebControls.Button>-Steuerelement namens `OKButton`. Legen Sie seine <xref:System.Web.UI.WebControls.Button.Text%2A>-Eigenschaft auf „OK“ fest.  
  
- Ein <xref:System.Web.UI.WebControls.HiddenField>-Steuerelement namens `DateInfo`.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Um zu verhindern, dass ein Benutzer ein Skript in den HTML-Stream einfügt, sollte eine Benutzereingabe nie direkt in der Antwort des Servers wiederholt werden. Sie sollte stattdessen mithilfe der <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType>-Methode codiert werden.  
  
## <a name="see-also"></a>Siehe auch

- [Durchführen von Formatierungsvorgängen](../../../docs/standard/base-types/performing-formatting-operations.md)
- [Standard Date and Time Format Strings](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)
- [Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)
- [Verarbeiten von Zeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/parsing-datetime.md)

---
title: "Gewusst wie: Anzeigen lokalisierter Datums- und Uhrzeitangaben für Webbenutzer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- formatting [.NET Framework], dates
- parsing strings [.NET Framework], date and time strings
- localization [.NET Framework], date and time displays
- formatting [.NET Framework], localized data
- displaying date and time data
- localized date displays [.NET Framework]
ms.assetid: 377fe93c-32be-421a-a30a-be639a46ede8
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 21493e0e0c9e42cf5efc42d86c8f126fbae9b392
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-localized-date-and-time-information-to-web-users"></a>Gewusst wie: Anzeigen lokalisierter Datums- und Uhrzeitangaben für Webbenutzer
Da eine Webseite an einer beliebigen Stelle in der ganzen Welt angezeigt werden können, von Vorgängen zum Analysieren und Formatieren von Datums-und Uhrzeitwerte nicht empfehlenswert Standardformat (die am häufigsten das Format der lokalen Kultur des Webservers) bei der Interaktion mit dem Benutzer verwendet. WebForms, die Behandeln von Datum und Uhrzeit-Zeichenfolgen-Eingabe vom Benutzer sollten stattdessen die Zeichenfolgen werden mithilfe der bevorzugten Kultur des Benutzers analysiert werden. Entsprechend sollte Datums-und Uhrzeitdaten in einem Format an den Benutzer angezeigt werden, die das der Kultur des Benutzers entspricht. In diesem Thema wird gezeigt, wie Sie dazu vorgehen müssen.  
  
### <a name="to-parse-date-and-time-strings-input-by-the-user"></a>Analysieren von Datum und Uhrzeit Zeichenfolgen Eingabe vom Benutzer  
  
1.  Bestimmen, ob das Zeichenfolgenarray zurückgegebene der <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> Eigenschaft wird aufgefüllt. Wenn sie nicht der Fall ist, fahren Sie mit Schritt 6.  
  
2.  Wenn das Array von Zeichenfolgen von zurückgegeben der <xref:System.Web.HttpRequest.UserLanguages%2A> Eigenschaft wird angegeben, das erste Element abzurufen. Das erste Element gibt an Standardeinstellung oder bevorzugte Sprache und Region des Benutzers.  
  
3.  Instanziieren einer <xref:System.Globalization.CultureInfo> -Objekt, das den Benutzer darstellt bevorzugte Kultur durch Aufrufen der <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> Konstruktor.  
  
4.  Rufen Sie entweder die `TryParse` oder `Parse` Methode der <xref:System.DateTime> oder <xref:System.DateTimeOffset> Typ, um die Konvertierung zu versuchen. Verwenden Sie eine Überladung der der `TryParse` oder `Parse` Methode mit einer `provider` Parameter, und übergeben sie eine der folgenden:  
  
    -   Die <xref:System.Globalization.CultureInfo> in Schritt 3 erstellten Objekt.  
  
    -   Die <xref:System.Globalization.DateTimeFormatInfo> von zurückgegebene Objekt der <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> Eigenschaft von der <xref:System.Globalization.CultureInfo> in Schritt 3 erstellten Objekt.  
  
5.  Wenn die Konvertierung fehlschlägt, wiederholen Sie die Schritte 2 bis 4 für jedes verbleibende Element im Zeichenfolgenarray zurückgegebenes der <xref:System.Web.HttpRequest.UserLanguages%2A> Eigenschaft.  
  
6.  Wenn die Konvertierung weiterhin fehlschlägt oder von der String-Array zurückgegeben der <xref:System.Web.HttpRequest.UserLanguages%2A> -Eigenschaft leer ist, analysiert die Zeichenfolge mit der invarianten Kultur zurückgegeben, durch die <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> Eigenschaft.  
  
### <a name="to-parse-the-local-date-and-time-of-the-users-request"></a>Das lokale Datum und Uhrzeit der Anforderung des Benutzers analysiert  
  
1.  Hinzufügen einer <xref:System.Web.UI.WebControls.HiddenField> Steuerelement ein Web Form.  
  
2.  Erstellen Sie eine JavaScript-Funktion, die behandelt die `onClick` -Ereignis für ein `Submit` Schaltfläche durch das aktuelle Datum und Uhrzeit und die lokale Zeitzone Offset von Coordinated Universal Time (UTC) zu schreiben die <xref:System.Web.UI.WebControls.HiddenField.Value%2A> Eigenschaft. Verwenden Sie ein Trennzeichen (z. B. ein Semikolon), um die beiden Komponenten der Zeichenfolge zu trennen.  
  
3.  Verwenden Sie des Webformular <xref:System.Web.UI.Control.PreRender> Ereignis, um die Funktion in der HTML-Code einfügen Ausgabestream durch Übergeben des Texts des Skripts an die <xref:System.Web.UI.ClientScriptManager.RegisterClientScriptBlock%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType> Methode.  
  
4.  Verbinden Sie den Ereignishandler der `Submit` Schaltfläche `onClick` Ereignis durch Eingabe des Namens der JavaScript-Funktion, um die `OnClientClick` Attribut des der `Submit` Schaltfläche.  
  
5.  Erstellen Sie einen Ereignishandler für das `Submit` Schaltfläche <xref:System.Web.UI.WebControls.Button.Click> Ereignis.  
  
6.  Bei der Ereignishandler ermitteln, ob das Zeichenfolgenarray zurückgegebene der <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> Eigenschaft wird aufgefüllt. Wenn sie nicht der Fall ist, fahren Sie mit Schritt 14.  
  
7.  Wenn das Array von Zeichenfolgen von zurückgegeben der <xref:System.Web.HttpRequest.UserLanguages%2A> Eigenschaft wird angegeben, das erste Element abzurufen. Das erste Element gibt an Standardeinstellung oder bevorzugte Sprache und Region des Benutzers.  
  
8.  Instanziieren einer <xref:System.Globalization.CultureInfo> -Objekt, das den Benutzer darstellt bevorzugte Kultur durch Aufrufen der <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> Konstruktor.  
  
9. Die zugewiesene Zeichenfolge zu übergeben der <xref:System.Web.UI.WebControls.HiddenField.Value%2A> Eigenschaft, um die <xref:System.String.Split%2A> Methode, um die Zeichenfolgendarstellung des Benutzers lokale Datums- und Uhrzeitangabe und der Zeichenfolgendarstellung der lokalen Zeitzone des Benutzers in separaten Arrayelemente speichern.  
  
10. Rufen Sie entweder die <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> oder <xref:System.DateTime.TryParse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%2CSystem.DateTime%40%29?displayProperty=nameWithType> -Methode zum Konvertieren von Datum und Uhrzeit der Anforderung des Benutzers, um eine <xref:System.DateTime> Wert. Verwenden Sie eine Überladung der Methode mit einem `provider` Parameter, und übergeben sie eine der folgenden:  
  
    -   Die <xref:System.Globalization.CultureInfo> in Schritt 8 erstellte Objekt.  
  
    -   Die <xref:System.Globalization.DateTimeFormatInfo> von zurückgegebene Objekt der <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> Eigenschaft von der <xref:System.Globalization.CultureInfo> in Schritt 8 erstellte Objekt.  
  
11. Wenn der Analysevorgang in Schritt 10 fehlschlägt, fahren Sie mit Schritt 13. Rufen Sie andernfalls die <xref:System.UInt32.Parse%28System.String%29?displayProperty=nameWithType> Methode, die Zeichenfolgendarstellung des Benutzers einen Zeitzonenoffset in eine ganze Zahl zu konvertieren.  
  
12. Instanziieren einer <xref:System.DateTimeOffset> , die Ortszeit des Benutzers durch Aufrufen der <xref:System.DateTimeOffset.%23ctor%28System.DateTime%2CSystem.TimeSpan%29?displayProperty=nameWithType> Konstruktor.  
  
13. Wenn die Konvertierung in Schritt 10 fehlschlägt, wiederholen Sie die Schritte 7 bis 12 für jedes verbleibende Element im Zeichenfolgenarray zurückgegebenes der <xref:System.Web.HttpRequest.UserLanguages%2A> Eigenschaft.  
  
14. Wenn die Konvertierung weiterhin fehlschlägt oder von der String-Array zurückgegeben der <xref:System.Web.HttpRequest.UserLanguages%2A> -Eigenschaft leer ist, analysiert die Zeichenfolge mit der invarianten Kultur zurückgegeben, durch die <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> Eigenschaft. Wiederholen Sie dann die Schritte 7 bis 12.  
  
 Das Ergebnis ist ein <xref:System.DateTimeOffset> Objekt, das die Ortszeit des Benutzers Ihrer Webseite darstellt. Sie können dann die entsprechende UTC bestimmen, durch Aufrufen der <xref:System.DateTimeOffset.ToUniversalTime%2A> Methode. Festzustellen können Sie auch das entsprechende Datum und die Uhrzeit auf dem Webserver durch Aufrufen der <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> -Methode und die Übergabe des Werts <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> als die Zeitzone, die Uhrzeit zu konvertieren.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel enthält der HTML-Quelle und den Code für eine ASP.NET Web-Formular, das den Benutzer auffordert, geben Sie einen Wert für Datum und Uhrzeit. Ein clientseitiges Skript schreibt Informationen über das lokale Datum und die Uhrzeit der Anforderung des Benutzers und den Offset der Zeitzone des Benutzers von UTC in ein ausgeblendetes Feld. Diese Informationen wird dann durch den Server analysiert, die eine Webseite zurückgibt, die die Eingaben des Benutzers werden angezeigt. Es zeigt auch das Datum und die Uhrzeit der Anforderung des Benutzers, die mithilfe der lokalen Zeit des Benutzers, der den Zeitpunkt auf dem Server und UTC.  
  
 [!code-aspx-csharp[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/cs/GetDateInfo.aspx#1)]
 [!code-aspx-vb[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/vb/GetDateInfo.aspx#1)]
  
 Die clientseitige Skript ruft die JavaScript `toLocaleString` Methode. Dies erzeugt eine Zeichenfolge, die die Formatierungskonventionen der das Gebietsschema des Benutzers, folgt also eher auf dem Server erfolgreich analysiert werden.  
  
 Die <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> Eigenschaft wird angegeben, aus den Kulturnamen, die in enthaltenen `Accept-Language` Header in einer HTTP-Anforderung. Allerdings enthalten, nicht von allen Browsern `Accept-Language` Header in ihren Anforderungen und die Benutzer können auch unterdrückt werden die Kopfzeilen vollständig. Daher ist es wichtig, eine Fallbackkultur haben bei der Analyse der Benutzereingabe. In der Regel ist die Fallbackkultur der invarianten Kultur zurückgegebenes <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Benutzer können Internet Explorer auch mit Kulturnamen bereitstellen, dass sie in einem Textfeld, die die Möglichkeit, dass erstellt eingegeben, die den Kulturnamen möglicherweise nicht gültig sind. Daher ist es wichtig, eine Ausnahmebehandlung verwendet, bei der Instanziierung einer <xref:System.Globalization.CultureInfo> Objekt.  
  
 Beim Abrufen der aus einer HTTP-Anforderung von Internet Explorer, übermittelt der <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> Array wird aufgefüllt, in der Reihenfolge der benutzereinstellung. Das erste Element im Array enthält den Namen des primären Kultur bzw. der Region des Benutzers. Wenn das Array zusätzliche Elemente enthält, weist Internet Explorer werden nach dem Zufallsprinzip einen Spezifizierer Qualität, die aus den Namen der Kultur, die durch ein Semikolon getrennt wird. Beispielsweise kann ein Eintrag für die Kultur fr-FR Form dauern `fr-FR;q=0.7`.  
  
 Im Beispiel wird die <xref:System.Globalization.CultureInfo.%23ctor%2A> Konstruktor mit seiner `useUserOverride` Parametersatz auf `false` zum Erstellen eines neuen <xref:System.Globalization.CultureInfo> Objekt. Dadurch wird sichergestellt, dass, wenn der Name der Kultur der Standardname für die Kultur auf dem Server ist die neue <xref:System.Globalization.CultureInfo> Objekt erstellt, indem der Konstruktor der Klasse enthält die Standardeinstellungen für eine Kultur und reflektiert keine Einstellungen, die mit des Servers überschrieben  **Regionalen und Sprachoptionen** Anwendung. Die Werte in "alle Einstellungen außer Kraft gesetzte" auf dem Server sind wahrscheinlich nicht auf dem System des Benutzers vorhanden ist oder in der Eingabe des Benutzers berücksichtigt werden.  
  
 Da in diesem Beispiel zwei zeichenfolgendarstellungen einer Datums- und Uhrzeitangabe (eine Eingabe vom Benutzer, die andere dem ausgeblendeten Feld gespeichert) analysiert, definiert die möglichen <xref:System.Globalization.CultureInfo> Objekte, die möglicherweise erforderlich sind, im voraus. Erstellt ein Array von <xref:System.Globalization.CultureInfo> Objekte, der eins größer als die Anzahl von zurückgegebenen Elementen ist das <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> Eigenschaft. Dann instanziiert einen <xref:System.Globalization.CultureInfo> -Objekt für jede Sprache/Regionszeichenfolge und darüber hinaus instanziiert einen <xref:System.Globalization.CultureInfo> Objekt, das darstellt <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.  
  
 Kann Ihren Code rufen Sie entweder die <xref:System.DateTime.Parse%2A> oder <xref:System.DateTime.TryParse%2A> Methode zum Konvertieren des Benutzers Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe in einer <xref:System.DateTime> Wert. Wiederholte Aufrufe an eine Analysemethode können für eine einzelnes Analysevorgang erforderlich sein. Daher die <xref:System.DateTime.TryParse%2A> Methode ist besser, weil sie zurückgibt `false` Wenn es sich bei einem Analysevorgang misslingt. Im Gegensatz dazu Behandeln der wiederholten Ausnahmen, die von ausgelöst werden möglicherweise die <xref:System.DateTime.Parse%2A> Methode kann ein sehr ressourcenintensiver Vorgang in einer Webanwendung sein.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um den Code zu kompilieren, erstellen Sie eine [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Webseite ohne Code-Behind. Anschließend kopieren Sie das Beispiel in der Webseite, damit sie den vorhandenen Code ersetzt. Die [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Webseite sollte die folgenden Steuerelemente enthalten:  
  
-   Ein <xref:System.Web.UI.WebControls.Label> -Steuerelement, das nicht im Code verwiesen wird. Legen Sie seine <xref:System.Web.UI.WebControls.TextBox.Text%2A> -Eigenschaft auf "Geben Sie eine Zahl:".  
  
-   Ein <xref:System.Web.UI.WebControls.TextBox>-Steuerelement namens `DateString`.  
  
-   Ein <xref:System.Web.UI.WebControls.Button>-Steuerelement namens `OKButton`. Legen Sie dessen <xref:System.Web.UI.WebControls.Button.Text%2A> Eigenschaft auf "OK".  
  
-   Ein <xref:System.Web.UI.WebControls.HiddenField>-Steuerelement namens `DateInfo`.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Um zu verhindern, dass einen Benutzer Räumen Skript in den HTML-Stream, sollte eine Benutzereingabe nie direkt wieder in die Antwort des Servers wiederholt werden. Sie sollten stattdessen codiert werden, mithilfe der <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType> Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [Durchführen von Formatierungsvorgängen](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [Standard Date and Time Format Strings](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)  
 [Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)  
 [Verarbeiten von Zeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/parsing-datetime.md)

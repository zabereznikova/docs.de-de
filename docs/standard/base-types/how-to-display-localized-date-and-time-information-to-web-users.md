---
title: "Gewusst wie: Anzeigen lokalisierter Datums- und Uhrzeitangaben f&#252;r Webbenutzer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Anzeigen von Datums- und Uhrzeitdaten"
  - "Formatieren [.NET Framework], Datumsangaben"
  - "Formatieren [.NET Framework], Lokalisierte Daten"
  - "Lokalisierung [.NET Framework], Datums- und Uhrzeitanzeigen"
  - "Lokalisierte Datenanzeigen [.NET Framework]"
  - "Analysieren von Zeichenfolgen [.NET Framework], Datum- und Uhrzeitzeichenfolgen"
ms.assetid: 377fe93c-32be-421a-a30a-be639a46ede8
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Anzeigen lokalisierter Datums- und Uhrzeitangaben f&#252;r Webbenutzer
Eine Webseite kann an beliebigen Standorten weltweit angezeigt werden kann. Bei der Interaktion mit dem Benutzer sollten daher Vorgänge, mit denen Datums\- und Uhrzeitwerte analysiert und formatiert werden, nicht auf einem Standardformat \(meist dem Format der lokalen Kultur des Webservers\) beruhen.  Web Forms, die vom Benutzer eingegebene Datums\- und Uhrzeitzeichenfolgen verarbeiten, sollten die Zeichenfolgen stattdessen unter Verwendung der bevorzugten Kultur des Benutzers analysieren.  Und auch Datums\- und Uhrzeitdaten sollten dem Benutzer in einem Format angezeigt werden, das dessen Kultur entspricht.  In diesem Artikel wird die Vorgehensweise veranschaulicht.  
  
### So analysieren Sie vom Benutzer eingegebene Datums\- und Uhrzeitzeichenfolgen  
  
1.  Stellen Sie fest, ob das von der <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName>\-Eigenschaft zurückgegebene Zeichenfolgenarray Daten enthält.  Falls nicht, fahren Sie mit Schritt 6 fort.  
  
2.  Wenn das von der <xref:System.Web.HttpRequest.UserLanguages%2A>\-Eigenschaft zurückgegebene Zeichenfolgenarray Daten enthält, rufen Sie dessen erstes Element ab.  Das erste Element gibt die standardmäßige bzw. bevorzugte Sprache und Region des Benutzers an.  
  
3.  Instanziieren Sie ein <xref:System.Globalization.CultureInfo>\-Objekt, das die bevorzugte Kultur des Benutzers darstellt, indem Sie den <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName>\-Konstruktor aufrufen.  
  
4.  Rufen Sie entweder die `TryParse`\-Methode oder die `Parse`\-Methode des <xref:System.DateTime>\-Typs oder des <xref:System.DateTimeOffset>\-Typs auf, um zu versuchen, eine Konvertierung auszuführen.  Verwenden Sie eine Überladung der `TryParse`\-Methode oder der `Parse`\-Methode mit einem `provider`\-Parameter, und übergeben Sie eines der folgenden Objekte:  
  
    -   Das in Schritt 3 erstellte <xref:System.Globalization.CultureInfo>\-Objekt.  
  
    -   Das <xref:System.Globalization.DateTimeFormatInfo>\-Objekt, das durch die <xref:System.Globalization.CultureInfo.DateTimeFormat%2A>\-Eigenschaft des in Schritt 3 erstellten <xref:System.Globalization.CultureInfo>\-Objekts zurückgegeben wird.  
  
5.  Wenn die Konvertierung fehlschlägt, wiederholen Sie die Schritte 2 bis 4 für jedes verbleibende Element in dem durch die <xref:System.Web.HttpRequest.UserLanguages%2A>\-Eigenschaft zurückgegebenen Zeichenfolgenarray.  
  
6.  Wenn die Konvertierung weiterhin fehlschlägt oder das von der <xref:System.Web.HttpRequest.UserLanguages%2A>\-Eigenschaft zurückgegebene Zeichenfolgenarray leer ist, analysieren Sie die Zeichenfolge unter Verwendung der invarianten Kultur, die von der <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>\-Eigenschaft zurückgegeben wird.  
  
### So analysieren Sie das lokale Datum und die Ortszeit der Benutzeranforderung  
  
1.  Fügen Sie einem Web Form ein <xref:System.Web.UI.WebControls.HiddenField>\-Steuerelement hinzu.  
  
2.  Erstellen Sie eine JavaScript\-Funktion, die das `onClick`\-Ereignis einer `Submit`\-Schaltfläche behandelt, indem das aktuelle Datum und die aktuelle Zeit sowie der Offset der lokalen Zeitzone von der koordinierten Weltzeit \(Coordinated Universal Time, UTC\) in die <xref:System.Web.UI.WebControls.HiddenField.Value%2A>\-Eigenschaft geschrieben wird.  Verwenden Sie ein Trennzeichen \(z. B. ein Semikolon\), um die beiden Komponenten der Zeichenfolge zu trennen.  
  
3.  Verwenden Sie das <xref:System.Web.UI.Control.PreRender>\-Ereignis des Web Forms, um die Funktion in den HTML\-Ausgabestream einzufügen, indem Sie den Text des Skripts an die <xref:System.Web.UI.ClientScriptManager.RegisterClientScriptBlock%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=fullName>\-Methode übergeben.  
  
4.  Verbinden Sie den Ereignishandler mit dem `onClick`\-Ereignis der `Submit`\-Schaltfläche, indem Sie den Namen der JavaScript\-Funktion für das `OnClientClick`\-Attribut der `Submit`\-Schaltfläche bereitstellen.  
  
5.  Erstellen Sie einen Handler für das <xref:System.Web.UI.WebControls.Button.Click>\-Ereignis der `Submit`\-Schaltfläche.  
  
6.  Bestimmen Sie im Ereignishandler, ob das von der <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName>\-Eigenschaft zurückgegebene Zeichenfolgenarray Daten enthält.  Falls nicht, fahren Sie mit Schritt 14 fort.  
  
7.  Wenn das von der <xref:System.Web.HttpRequest.UserLanguages%2A>\-Eigenschaft zurückgegebene Zeichenfolgenarray Daten enthält, rufen Sie dessen erstes Element ab.  Das erste Element gibt die standardmäßige bzw. bevorzugte Sprache und Region des Benutzers an.  
  
8.  Instanziieren Sie ein <xref:System.Globalization.CultureInfo>\-Objekt, das die bevorzugte Kultur des Benutzers darstellt, indem Sie den <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName>\-Konstruktor aufrufen.  
  
9. Übergeben Sie die der <xref:System.Web.UI.WebControls.HiddenField.Value%2A>\-Eigenschaft zugewiesene Zeichenfolge an die <xref:System.String.Split%2A>\-Methode, um die Zeichenfolgendarstellung des lokalen Datums und der Ortszeit des Benutzers und die Zeichenfolgendarstellung des Offsets der lokalen Zeitzone des Benutzers in getrennten Arrayelementen zu speichern.  
  
10. Rufen Sie entweder die <xref:System.DateTime.Parse%2A?displayProperty=fullName>\-Methode oder die <xref:System.DateTime.TryParse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%2CSystem.DateTime%40%29?displayProperty=fullName>\-Methode auf, um das Datum und die Uhrzeit der Benutzeranforderung in einen <xref:System.DateTime>\-Wert zu konvertieren.  Verwenden Sie eine Überladung der Methode mit einem `provider`\-Parameter, und übergeben Sie eines der folgenden Objekte:  
  
    -   Das in Schritt 8 erstellte <xref:System.Globalization.CultureInfo>\-Objekt.  
  
    -   Das <xref:System.Globalization.DateTimeFormatInfo>\-Objekt, das durch die <xref:System.Globalization.CultureInfo.DateTimeFormat%2A>\-Eigenschaft des in Schritt 8 erstellten <xref:System.Globalization.CultureInfo>\-Objekts zurückgegeben wird.  
  
11. Wenn die Analyseoperation in Schritt 10 fehlschlägt, fahren Sie mit Schritt 13 fort.  Andernfalls rufen Sie die <xref:System.UInt32.Parse%28System.String%29?displayProperty=fullName>\-Methode auf, um die Zeichenfolgendarstellung des Zeitzonenoffsets des Benutzers in eine ganze Zahl zu konvertieren.  
  
12. Instanziieren Sie einen <xref:System.DateTimeOffset>, der die Ortszeit des Benutzers darstellt, indem Sie den <xref:System.DateTimeOffset.%23ctor%28System.DateTime%2CSystem.TimeSpan%29?displayProperty=fullName>\-Konstruktor aufrufen.  
  
13. Wenn die Konvertierung in Schritt 10 fehlschlägt, wiederholen Sie die Schritte 7 bis 12 für jedes verbleibende Element in dem durch die <xref:System.Web.HttpRequest.UserLanguages%2A>\-Eigenschaft zurückgegebenen Zeichenfolgenarray.  
  
14. Wenn die Konvertierung weiterhin fehlschlägt oder das von der <xref:System.Web.HttpRequest.UserLanguages%2A>\-Eigenschaft zurückgegebene Zeichenfolgenarray leer ist, analysieren Sie die Zeichenfolge unter Verwendung der invarianten Kultur, die von der <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>\-Eigenschaft zurückgegeben wird.  Wiederholen Sie dann die Schritte 7 bis 12.  
  
 Das Ergebnis ist ein <xref:System.DateTimeOffset>\-Objekt, das die Ortszeit des Benutzers Ihrer Webseite darstellt.  Sie können dann die entsprechende UTC bestimmen, indem Sie die <xref:System.DateTimeOffset.ToUniversalTime%2A>\-Methode aufrufen.  Sie können auch das entsprechende Datum und die entsprechende Uhrzeit auf Ihrem Webserver feststellen, indem Sie die <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=fullName>\-Methode aufrufen und einen Wert von <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName> als Zeitzone übergeben, in die die Uhrzeit konvertiert werden soll.  
  
## Beispiel  
 Das folgende Beispiel enthält sowohl den HTML\-Quellcode als auch den Code für ein ASP.NET\-Web Form, in dem der Benutzer aufgefordert wird, einen Datums\- und Uhrzeitwert einzugeben.  Außerdem schreibt ein clientseitiges Skript Informationen zum lokalen Datum und der Ortszeit der Benutzeranforderung sowie zum Offset der Zeitzone des Benutzers von der UTC in ein ausgeblendetes Feld.  Anschließend werden die Informationen vom Server analysiert, der eine Webseite zurückgibt, in der die Benutzereingabe angezeigt wird.  Darüber hinaus werden Datum und Uhrzeit der Benutzeranforderung unter Verwendung der Ortszeit des Benutzers, die Uhrzeit auf dem Server sowie die UTC angezeigt.  
  
 <!-- TODO: review snippet reference [!code-csharp[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/cs/GetDateInfo.aspx#1)]  -->
 <!-- TODO: review snippet reference [!code-vb[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/vb/GetDateInfo.aspx#1)]  -->  
  
 Das clientseitige Skript ruft die JavaScript\-Methode `toLocaleString` auf.  Auf diese Weise wird eine Zeichenfolge generiert, die den Formatierungskonventionen des Benutzergebietsschemas entspricht und dadurch wahrscheinlich erfolgreicher auf dem Server analysiert werden kann.  
  
 Die <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName>\-Eigenschaft wird unter Verwendung der Kulturnamen aufgefüllt, die in `Accept-Language`\-Headern innerhalb einer HTTP\-Anforderung enthalten sind.  Allerdings schließen nicht alle Browser `Accept-Language`\-Header in ihre Anforderungen ein, und die Header können vom Benutzer auch vollständig unterdrückt werden.  Daher ist es wichtig, bei der Analyse der Benutzereingabe über eine Fallbackkultur zu verfügen.  Die Fallbackkultur ist in der Regel die von der <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>\-Eigenschaft zurückgegebene invariante Kultur.  Benutzer können auch Kulturnamen für Internet Explorer bereitstellen, die sie in ein Textfeld eingeben. Dabei ist es möglich, dass die Kulturnamen nicht gültig sind.  Aus diesem Grund sollte beim Instanziieren eines <xref:System.Globalization.CultureInfo>\-Objekts unbedingt eine Ausnahmebehandlung verwendet werden.  
  
 Wenn das <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName>\-Array durch eine von Internet Explorer gesendeten HTTP\-Anforderung abgerufen wird, wird es in der Reihenfolge der Benutzereinstellungen aufgefüllt.  Das erste Element im Array enthält den Namen der primären Kultur\/Region des Benutzers.  Wenn das Array zusätzliche Elemente enthält, weist Ihnen Internet Explorer beliebig einen Qualitätsbezeichner zu, der durch ein Semikolon vom Kulturnamen getrennt ist.  Beispielsweise könnte ein Eintrag für die Kultur fr\-FR wie folgt aussehen: `fr-FR;q=0.7`.  
  
 Im Beispiel wird der <xref:System.Globalization.CultureInfo.%23ctor%2A>\-Konstruktor, dessen `useUserOverride`\-Parameter auf `false` festgelegt ist, aufgerufen, um ein neues <xref:System.Globalization.CultureInfo>\-Objekt zu erstellen.  So wird sichergestellt, dass, wenn der Kulturname dem standardmäßigen Kulturnamen auf dem Server entspricht, das neue, vom Klassenkonstruktor erstellte <xref:System.Globalization.CultureInfo>\-Objekt die Standardkultureinstellungen beinhaltet und keine Einstellungen widerspiegelt, die durch die Anwendung **Regions\- und Sprachoptionen** des Servers überschrieben wurden.  Es ist unwahrscheinlich, dass die Werte von auf dem Server überschriebenen Einstellungen auf dem Benutzersystem vorhanden sind oder in der Benutzereingabe wiedergegeben werden.  
  
 Da in diesem Beispiel zwei Zeichenfolgendarstellungen eines Datums und einer Uhrzeit \(einerseits vom Benutzer eingegeben und andererseits im ausgeblendeten Feld gespeichert\) analysiert werden, werden die möglicherweise erforderlichen <xref:System.Globalization.CultureInfo>\-Objekte im Voraus definiert.  Es wird ein Array von <xref:System.Globalization.CultureInfo>\-Objekten erstellt, das um ein Element größer als die Anzahl der von der <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName>\-Eigenschaft zurückgegebenen Elemente ist.  Anschließend wird ein <xref:System.Globalization.CultureInfo>\-Objekt für jede Sprach\-\/Regionszeichenfolge und darüber hinaus ein <xref:System.Globalization.CultureInfo>\-Objekt instanziiert, das <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> darstellt.  
  
 Der Code kann entweder die <xref:System.DateTime.Parse%2A>\-Methode oder die <xref:System.DateTime.TryParse%2A>\-Methode zur Konvertierung der benutzerspezifischen Zeichenfolgendarstellung eines Datums und einer Uhrzeit in einen <xref:System.DateTime>\-Wert aufrufen.  Für einen einzelnen Analysevorgang muss eine Analysemethode möglicherweise wiederholt aufgerufen werden.  Folglich ist die <xref:System.DateTime.TryParse%2A>\-Methode besser geeignet, da sie `false` zurückgibt, falls ein Analysevorgang fehlschlägt.  Die Behandlung der wiederholten Ausnahmen, die von der <xref:System.DateTime.Parse%2A>\-Methode ausgelöst werden , kann sich in einer Webanwendung hingegen als kostenintensives Unterfangen herausstellen.  
  
## Kompilieren des Codes  
 Um den Code zu kompilieren, erstellen Sie eine [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]\-Webseite ohne Code\-Behind.  Anschließend kopieren Sie das Beispiel in die Webseite, um den gesamten vorhandenen Code zu ersetzen.  Die [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]\-Webseite sollte die folgenden Steuerelemente enthalten:  
  
-   Ein <xref:System.Web.UI.WebControls.Label>\-Steuerelement, auf das im Code nicht verwiesen wird.  Legen Sie die zugehörige <xref:System.Web.UI.WebControls.TextBox.Text%2A>\-Eigenschaft auf "Enter a Number:" fest.  
  
-   Ein <xref:System.Web.UI.WebControls.TextBox>\-Steuerelement mit dem Namen `DateString`.  
  
-   Ein <xref:System.Web.UI.WebControls.Button>\-Steuerelement mit dem Namen `OKButton`.  Legen Sie die entsprechende <xref:System.Web.UI.WebControls.Button.Text%2A>\-Eigenschaft auf "OK" fest.  
  
-   Ein <xref:System.Web.UI.WebControls.HiddenField>\-Steuerelement mit dem Namen `DateInfo`.  
  
## .NET Framework-Sicherheit  
 Um zu verhindern, dass ein Benutzer Skriptcode in den HTML\-Stream einfügt, sollte die Benutzereingabe in der Serverantwort nie direkt wiedergegeben werden.  Stattdessen sollte sie mithilfe der <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=fullName>\-Methode codiert werden.  
  
## Siehe auch  
 [Durchführen von Formatierungsvorgängen](../../../docs/standard/base-types/performing-formatting-operations.md)   
 [Standard\-Formatzeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)   
 [Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)   
 [Verarbeiten von Zeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/parsing-datetime.md)
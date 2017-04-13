---
title: "Gewusst wie: Konvertieren numerischer Benutzereingaben in Websteuerelementen in Zahlen | Microsoft Docs"
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
  - "Konvertieren einer numerischen Benutzereingabe in eine Zahl"
  - "Formatieren [.NET Framework], Zahlen"
  - "Zahlenformatierung [.NET Framework]"
  - "Zahlen [.NET Framework], Konvertieren einer numerischen Benutzereingabe in eine Zahl"
  - "Numerische Formatzeichenfolgen [.NET Framework]"
  - "Analysieren von Zeichenfolgen [.NET Framework], Numerische Zeichenfolgen"
ms.assetid: f27ddfb8-7479-4b79-8879-02a3bd8402d4
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Konvertieren numerischer Benutzereingaben in Websteuerelementen in Zahlen
Da eine Webseite auf der ganzen Welt angezeigt werden kann, können Benutzer numerische Daten unter Verwendung unbegrenzt vieler Formate in ein <xref:System.Web.UI.WebControls.TextBox>\-Steuerelement eingeben.  Folglich ist es sehr wichtig, das Gebietsschema und die Kultur des Webseitenbenutzers zu ermitteln.  Wenn Sie eine Benutzereingabe analysieren, können Sie die Formatierungskonventionen übernehmen, die vom Gebietsschema und der Kultur des Benutzers vorgegeben werden.  
  
### So konvertieren Sie numerische Eingaben aus einem TextBox\-Websteuerelement in eine Zahl  
  
1.  Stellen Sie fest, ob das von der <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName>\-Eigenschaft zurückgegebene Zeichenfolgenarray Daten enthält.  Falls nicht, fahren Sie mit Schritt 6 fort.  
  
2.  Wenn das von der <xref:System.Web.HttpRequest.UserLanguages%2A>\-Eigenschaft zurückgegebene Zeichenfolgenarray Daten enthält, rufen Sie dessen erstes Element ab.  Das erste Element gibt die standardmäßige bzw. bevorzugte Sprache und Region des Benutzers an.  
  
3.  Instanziieren Sie ein <xref:System.Globalization.CultureInfo>\-Objekt, das die bevorzugte Kultur des Benutzers darstellt, indem Sie den <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName>\-Konstruktor aufrufen.  
  
4.  Rufen Sie entweder die `TryParse`\-Methode oder die `Parse`\-Methode des numerischen Typs auf, in den die Benutzereingabe konvertiert werden soll.  Verwenden Sie eine Überladung der `TryParse`\-Methode oder der `Parse`\-Methode mit einem `provider`\-Parameter, und übergeben Sie eines der folgenden Objekte:  
  
    -   Das in Schritt 3 erstellte <xref:System.Globalization.CultureInfo>\-Objekt.  
  
    -   Das <xref:System.Globalization.NumberFormatInfo>\-Objekt, das durch die <xref:System.Globalization.CultureInfo.NumberFormat%2A>\-Eigenschaft des in Schritt 3 erstellten <xref:System.Globalization.CultureInfo>\-Objekts zurückgegeben wird.  
  
5.  Wenn die Konvertierung fehlschlägt, wiederholen Sie die Schritte 2 bis 4 für jedes verbleibende Element in dem durch die <xref:System.Web.HttpRequest.UserLanguages%2A>\-Eigenschaft zurückgegebenen Zeichenfolgenarray.  
  
6.  Wenn die Konvertierung weiterhin fehlschlägt oder das von der <xref:System.Web.HttpRequest.UserLanguages%2A>\-Eigenschaft zurückgegebene Zeichenfolgenarray leer ist, analysieren Sie die Zeichenfolge unter Verwendung der invarianten Kultur, die von der <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>\-Eigenschaft zurückgegeben wird.  
  
## Beispiel  
 Das folgende Beispiel stellt eine vollständige Code\-Behind\-Seite für ein Web Form dar, in dem der Benutzer zur Eingabe eines numerischen Wertes in ein <xref:System.Web.UI.WebControls.TextBox>\-Steuerelement aufgefordert und der Wert in eine Zahl konvertiert wird.  Diese Zahl wird dann verdoppelt und unter Verwendung derselben wie für die Originaleingabe verwendeten Formatierungsregeln angezeigt.  
  
 [!code-csharp[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/cs/NumericUserInput1.aspx.cs#1)]
 [!code-vb[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/vb/NumericUserInput1.aspx.vb#1)]  
  
 Die <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName>\-Eigenschaft wird unter Verwendung der Kulturnamen aufgefüllt, die in `Accept-Language`\-Headern innerhalb einer HTTP\-Anforderung enthalten sind.  Allerdings schließen nicht alle Browser `Accept-Language`\-Header in ihre Anforderungen ein, und die Header können vom Benutzer auch vollständig unterdrückt werden.  Daher ist es wichtig, bei der Analyse der Benutzereingabe über eine Fallbackkultur zu verfügen.  Die Fallbackkultur ist in der Regel die von der <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>\-Eigenschaft zurückgegebene invariante Kultur.  Benutzer können auch Kulturnamen für Internet Explorer bereitstellen, die sie in ein Textfeld eingeben. Dabei ist es möglich, dass die Kulturnamen nicht gültig sind.  Aus diesem Grund sollte beim Instanziieren eines <xref:System.Globalization.CultureInfo>\-Objekts unbedingt eine Ausnahmebehandlung verwendet werden.  
  
 Wenn das <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName>\-Array durch eine von Internet Explorer gesendeten HTTP\-Anforderung abgerufen wird, wird es in der Reihenfolge der Benutzereinstellungen aufgefüllt.  Das erste Element im Array enthält den Namen der primären Kultur\/Region des Benutzers.  Wenn das Array zusätzliche Elemente enthält, weist Ihnen Internet Explorer beliebig einen Qualitätsbezeichner zu, der durch ein Semikolon vom Kulturnamen getrennt ist.  Beispielsweise könnte ein Eintrag für die Kultur fr\-FR wie folgt aussehen: `fr-FR;q=0.7`.  
  
 Im Beispiel wird der <xref:System.Globalization.CultureInfo.%23ctor%2A>\-Konstruktor, dessen `useUserOverride`\-Parameter auf `false` festgelegt ist, aufgerufen, um ein neues <xref:System.Globalization.CultureInfo>\-Objekt zu erstellen.  So wird sichergestellt, dass, wenn der Kulturname dem standardmäßigen Kulturnamen auf dem Server entspricht, das neue, vom Klassenkonstruktor erstellte <xref:System.Globalization.CultureInfo>\-Objekt die Standardkultureinstellungen beinhaltet und keine Einstellungen widerspiegelt, die durch die Anwendung **Regions\- und Sprachoptionen** des Servers überschrieben wurden.  Es ist unwahrscheinlich, dass die Werte von auf dem Server überschriebenen Einstellungen auf dem Benutzersystem vorhanden sind oder in der Benutzereingabe wiedergegeben werden.  
  
 Durch Ihren Code kann entweder die `Parse`\-Methode oder die `TryParse`\-Methode des numerischen Typs aufgerufen werden, in den die Benutzereingabe konvertiert wird.  Für einen einzelnen Analysevorgang muss eine Analysemethode möglicherweise wiederholt aufgerufen werden.  Folglich ist die `TryParse`\-Methode besser geeignet, da sie `false` zurückgibt, falls ein Analysevorgang fehlschlägt.  Die Behandlung wiederholter Ausnahmen, die von der `Parse`\-Methode ausgelöst werden können, kann sich in einer Webanwendung hingegen als kostenintensives Unterfangen herausstellen.  
  
## Kompilieren des Codes  
 Um den Code zu kompilieren, kopieren Sie ihn in eine [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]\-Code\-Behind\-Seite, um den gesamten vorhandenen Code zu ersetzen.  Die [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]\-Webseite sollte die folgenden Steuerelemente enthalten:  
  
-   Ein <xref:System.Web.UI.WebControls.Label>\-Steuerelement, auf das im Code nicht verwiesen wird.  Legen Sie die zugehörige <xref:System.Web.UI.WebControls.TextBox.Text%2A>\-Eigenschaft auf "Enter a Number:" fest.  
  
-   Ein <xref:System.Web.UI.WebControls.TextBox>\-Steuerelement mit dem Namen `NumericString`.  
  
-   Ein <xref:System.Web.UI.WebControls.Button>\-Steuerelement mit dem Namen `OKButton`.  Legen Sie die entsprechende <xref:System.Web.UI.WebControls.Button.Text%2A>\-Eigenschaft auf "OK" fest.  
  
 Ändern Sie den Namen der Klasse von `NumericUserInput` in den durch das `Inherits`\-Attribut der `Page`\-Direktive der [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]\-Seite definierten Klassennamen.  Ändern Sie den Namen des `NumericInput`\-Objektverweises in den Namen, der vom `id`\-Attribut des `form`\-Tags der [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]\-Seite definiert wird.  
  
## .NET Framework-Sicherheit  
 Um zu verhindern, dass ein Benutzer Skriptcode in den HTML\-Stream einfügt, sollte die Benutzereingabe in der Serverantwort nie direkt wiedergegeben werden.  Stattdessen sollte sie mithilfe der <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=fullName>\-Methode codiert werden.  
  
## Siehe auch  
 [Durchführen von Formatierungsvorgängen](../../../docs/standard/base-types/performing-formatting-operations.md)   
 [Verarbeiten numerischer Zeichenfolgen](../../../docs/standard/base-types/parsing-numeric.md)
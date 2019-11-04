---
title: 'Vorgehensweise: Konvertieren numerischer Benutzereingaben in Websteuerelementen in Zahlen'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- parsing strings [.NET Framework], numeric strings
- converting numeric user input to number
- numbers [.NET Framework], converting numeric user input to number
ms.assetid: f27ddfb8-7479-4b79-8879-02a3bd8402d4
ms.openlocfilehash: 78ba284ad2e75b39c0fb1001b0f65b48c519dbb5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140106"
---
# <a name="how-to-convert-numeric-user-input-in-web-controls-to-numbers"></a>Vorgehensweise: Konvertieren numerischer Benutzereingaben in Websteuerelementen in Zahlen
Da eine Webseite in verschiedensten Ländern auf der ganzen Welt angezeigt werden kann, können Benutzer numerische Daten in einer nahezu unbegrenzten Anzahl von Formaten in ein <xref:System.Web.UI.WebControls.TextBox>-Steuerelement einfügen. Daher ist es von entscheidender Bedeutung, das Gebietsschema und die Kultur des Webseitenbenutzers zu ermitteln. Bei der Analyse von Benutzereingaben können Sie dann die vom Gebietsschema und der Kultur des Benutzers definierten Formatierungskonventionen anwenden.  
  
### <a name="to-convert-numeric-input-from-a-web-textbox-control-to-a-number"></a>So konvertieren Sie numerische Eingaben eines TextBox-Websteuerelements in eine Zahl  
  
1. Stellen Sie fest, ob das von der <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>-Eigenschaft zurückgegebene Zeichenfolgenarray aufgefüllt ist. Wenn dies nicht der Fall ist, fahren Sie mit Schritt 6 fort.  
  
2. Wenn das von der <xref:System.Web.HttpRequest.UserLanguages%2A>-Eigenschaft zurückgegebene Zeichenfolgenarray aufgefüllt ist, rufen Sie sein erstes Element ab. Das erste Element gibt die Standardeinstellung des Benutzers oder seine bevorzugte Sprache und Region an.  
  
3. Instanziieren Sie durch Aufrufen des <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType>-Konstruktors ein <xref:System.Globalization.CultureInfo>-Objekt, das die bevorzugte Kultur des Benutzers darstellt.  
  
4. Rufen Sie entweder die `TryParse`- oder `Parse`-Methode des numerischen Typs auf, in den die Benutzereingabe konvertiert werden soll. Verwenden Sie eine Überladung der `TryParse`- oder `Parse`-Methode mit einem `provider`-Parameter, und übergeben Sie sie an eines der folgenden Objekte:  
  
    - Das in Schritt 3 erstellte <xref:System.Globalization.CultureInfo>-Objekt  
  
    - Das von der <xref:System.Globalization.CultureInfo.NumberFormat%2A>-Eigenschaft zurückgegebene <xref:System.Globalization.NumberFormatInfo>-Objekt des in Schritt 3 erstellten <xref:System.Globalization.CultureInfo>-Objekts  
  
5. Wenn bei der Konvertierung ein Fehler auftritt, wiederholen Sie die Schritte 2 bis 4 für jedes verbleibende Element im von der <xref:System.Web.HttpRequest.UserLanguages%2A>-Eigenschaft zurückgegebenen Zeichenfolgenarray.  
  
6. Wenn bei der Konvertierung weiterhin ein Fehler auftritt, oder das von der <xref:System.Web.HttpRequest.UserLanguages%2A>-Eigenschaft zurückgegebene Zeichenfolgenarray leer ist, analysieren Sie die Zeichenfolge mit der invarianten Kultur, die durch die <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>-Eigenschaft zurückgegeben wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die gesamte CodeBehind-Seite für ein Webformular dargestellt, das den Benutzer dazu auffordert, einen numerischen Wert in ein <xref:System.Web.UI.WebControls.TextBox>-Steuerelement einzugeben, und diesen Wert in eine Zahl konvertiert. Diese Zahl wird dann verdoppelt und mit den gleichen Formatierungsregeln wie denen der ursprünglichen Eingabe angezeigt.  
  
 [!code-csharp[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/cs/NumericUserInput1.aspx.cs#1)]
 [!code-vb[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/vb/NumericUserInput1.aspx.vb#1)]  
  
 Zum Auffüllen der <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>-Eigenschaft kommen die Kulturnamen infrage, die sich in den in einer HTTP-Anforderung enthaltenen `Accept-Language`-Headern befinden. Allerdings sind nicht in den Anforderungen aller Browser `Accept-Language`-Header enthalten, und die Benutzer können die Header auch vollständig unterdrücken. Daher ist es wichtig, dass bei der Analyse der Benutzereingabe eine Fallbackkultur verfügbar ist. In der Regel ist die Fallbackkultur die von <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> zurückgegebene invariante Kultur. Benutzer können für den Internet Explorer auch Kulturnamen bereitstellen, die sie in ein Textfeld eingeben, was die Gefahr mit sich bringt, dass die Kulturnamen möglicherweise ungültig sind. Daher ist es wichtig, bei der Instanziierung eines <xref:System.Globalization.CultureInfo>-Objekts eine Ausnahmebehandlung zu verwenden.  
  
 Beim Abrufen durch eine vom Internet Explorer übermittelte HTTP-Anforderung wird das <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>-Array in der durch die Benutzervoreinstellung vorgegebenen Reihenfolge aufgefüllt. Das erste Element im Array enthält den Namen der primären Kultur/Region des Benutzers. Wenn das Array zusätzliche Elemente enthält, weist der Internet Explorer ihnen nach dem Zufallsprinzip einen Qualitätsspezifizierer zu, der durch ein Semikolon vom Namen der Kultur getrennt wird. Beispielsweise kann ein Eintrag für die Kultur „fr-FR“ das Format `fr-FR;q=0.7` aufweisen.  
  
 Im Beispiel wird der <xref:System.Globalization.CultureInfo.%23ctor%2A>-Konstruktor mit seinem auf `false` festgelegten `useUserOverride`-Parametersatz zum Erstellen eines neuen <xref:System.Globalization.CultureInfo>-Objekts aufgerufen. Wenn der Kulturname der Standardkulturname auf dem Server ist, wird dadurch sichergestellt, dass das vom Klassenkonstruktor erstellte neue <xref:System.Globalization.CultureInfo>-Objekt die Standardeinstellungen einer Kultur enthält und keine mit der Anwendung **Regions- und Sprachoptionen** des Servers überschriebenen Einstellungen widerspiegelt. Es ist unwahrscheinlich, dass die Werte überschriebener Einstellungen auf dem Server auf dem System des Benutzers vorhanden sind oder in der Eingabe des Benutzers widergespiegelt werden.  
  
 Ihr Code kann entweder die `Parse`- oder `TryParse`-Methode des numerischen Typs aufrufen, in den die Benutzereingabe konvertiert wird. Wiederholte an eine Analysemethode gerichtete Aufrufe können für einen einzelnen Analysevorgang erforderlich sein. Daher ist die `TryParse`-Methode besser, weil sie `false` zurückgibt, wenn bei einem Analysevorgang ein Fehler auftritt. Im Gegensatz dazu kann das Behandeln wiederholter Ausnahmen, die ggf. von der `Parse`-Methode ausgelöst werden, ein sehr ressourcenintensiver Vorgang in einer Webanwendung sein.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um den Code zu kompilieren, kopieren Sie ihn in eine ASP.NET-CodeBehind-Seite, damit diese den gesamten vorhandenen Code ersetzt. Die ASP.NET-Webseite sollte folgende Steuerelemente enthalten:  
  
- Ein <xref:System.Web.UI.WebControls.Label>-Steuerelement, auf das nicht im Code verwiesen wird. Legen Sie seine <xref:System.Web.UI.WebControls.TextBox.Text%2A>-Eigenschaft auf „Geben Sie eine Zahl ein:“ fest.  
  
- Ein <xref:System.Web.UI.WebControls.TextBox>-Steuerelement namens `NumericString`.  
  
- Ein <xref:System.Web.UI.WebControls.Button>-Steuerelement namens `OKButton`. Legen Sie seine <xref:System.Web.UI.WebControls.Button.Text%2A>-Eigenschaft auf „OK“ fest.  
  
 Ändern Sie den Namen der Klasse von `NumericUserInput` in den Namen der Klasse, die vom `Inherits`-Attribut der `Page`-Anweisung der ASP.NET-Seite definiert wird. Ändern Sie den Namen des `NumericInput`-Objektverweises in den Namen, der mit dem `id`-Attribut des `form`-Tags der ASP.NET-Seite definiert wird.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Um zu verhindern, dass ein Benutzer ein Skript in den HTML-Stream einfügt, sollte eine Benutzereingabe nie direkt in der Antwort des Servers wiederholt werden. Sie sollte stattdessen mithilfe der <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType>-Methode codiert werden.  
  
## <a name="see-also"></a>Siehe auch

- [Durchführen von Formatierungsvorgängen](../../../docs/standard/base-types/performing-formatting-operations.md)
- [Verarbeiten numerischer Zeichenfolgen](../../../docs/standard/base-types/parsing-numeric.md)

---
title: 'Gewusst wie: Konvertieren numerischer Benutzereingaben in Websteuerelementen in Zahlen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 92e28e3b303a7523b9da69b7eb283e0261fc681c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-numeric-user-input-in-web-controls-to-numbers"></a>Gewusst wie: Konvertieren numerischer Benutzereingaben in Websteuerelementen in Zahlen
Da eine Webseite an einer beliebigen Stelle in der ganzen Welt angezeigt werden kann, können Benutzer eingegeben numerische Daten in eine <xref:System.Web.UI.WebControls.TextBox> -Steuerelement in eine nahezu unbegrenzte Anzahl von Formaten. Daher ist es sehr wichtig, um zu bestimmen, das Gebietsschema und die Kultur des Benutzers für die Webseite. Wenn Sie Benutzereingaben analysieren, können Sie dann die Formatierungskonventionen definiert, die vom Gebietsschema und die Kultur des Benutzers anwenden.  
  
### <a name="to-convert-numeric-input-from-a-web-textbox-control-to-a-number"></a>Numerische Eingabe aus einem Web TextBox-Steuerelement in eine Zahl zu konvertieren.  
  
1.  Bestimmen, ob das Zeichenfolgenarray zurückgegebene der <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> Eigenschaft wird aufgefüllt. Wenn sie nicht der Fall ist, fahren Sie mit Schritt 6.  
  
2.  Wenn das Array von Zeichenfolgen von zurückgegeben der <xref:System.Web.HttpRequest.UserLanguages%2A> Eigenschaft wird angegeben, das erste Element abzurufen. Das erste Element gibt an Standardeinstellung oder bevorzugte Sprache und Region des Benutzers.  
  
3.  Instanziieren einer <xref:System.Globalization.CultureInfo> -Objekt, das den Benutzer darstellt bevorzugte Kultur durch Aufrufen der <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> Konstruktor.  
  
4.  Rufen Sie entweder die `TryParse` oder die `Parse` -Methode des numerischen Typs, die den Benutzer konvertiert werden sollen die Eingabe an. Verwenden Sie eine Überladung der der `TryParse` oder `Parse` Methode mit einer `provider` Parameter, und übergeben sie eine der folgenden:  
  
    -   Die <xref:System.Globalization.CultureInfo> in Schritt 3 erstellten Objekt.  
  
    -   Die <xref:System.Globalization.NumberFormatInfo> von zurückgegebene Objekt der <xref:System.Globalization.CultureInfo.NumberFormat%2A> Eigenschaft von der <xref:System.Globalization.CultureInfo> in Schritt 3 erstellten Objekt.  
  
5.  Wenn die Konvertierung fehlschlägt, wiederholen Sie die Schritte 2 bis 4 für jedes verbleibende Element im Zeichenfolgenarray zurückgegebenes der <xref:System.Web.HttpRequest.UserLanguages%2A> Eigenschaft.  
  
6.  Wenn die Konvertierung weiterhin fehlschlägt oder von der String-Array zurückgegeben der <xref:System.Web.HttpRequest.UserLanguages%2A> -Eigenschaft leer ist, analysiert die Zeichenfolge mit der invarianten Kultur zurückgegeben, durch die <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird der vollständige Code-Behind-Seite für ein Web Form, die den Benutzer auffordert, geben Sie einen numerischen Wert in einer <xref:System.Web.UI.WebControls.TextBox> steuern und konvertiert ihn in eine Zahl. Diese Anzahl ist dann verdoppelt und mit den gleichen Formatierungsregeln wie die ursprüngliche Eingabe angezeigt.  
  
 [!code-csharp[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/cs/NumericUserInput1.aspx.cs#1)]
 [!code-vb[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/vb/NumericUserInput1.aspx.vb#1)]  
  
 Die <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> Eigenschaft wird angegeben, aus den Kulturnamen, die in enthaltenen `Accept-Language` Header in einer HTTP-Anforderung. Allerdings enthalten, nicht von allen Browsern `Accept-Language` Header in ihren Anforderungen und die Benutzer können auch unterdrückt werden die Kopfzeilen vollständig. Daher ist es wichtig, eine Fallbackkultur haben bei der Analyse der Benutzereingabe. In der Regel ist die Fallbackkultur der invarianten Kultur zurückgegebenes <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Benutzer können Internet Explorer auch mit Kulturnamen bereitstellen, dass sie in einem Textfeld, die die Möglichkeit, dass erstellt eingegeben, die den Kulturnamen möglicherweise nicht gültig sind. Daher ist es wichtig, eine Ausnahmebehandlung verwendet, bei der Instanziierung einer <xref:System.Globalization.CultureInfo> Objekt.  
  
 Beim Abrufen der aus einer HTTP-Anforderung von Internet Explorer, übermittelt der <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> Array wird aufgefüllt, in der Reihenfolge der benutzereinstellung. Das erste Element im Array enthält den Namen des primären Kultur bzw. der Region des Benutzers. Wenn das Array zusätzliche Elemente enthält, weist Internet Explorer werden nach dem Zufallsprinzip einen Spezifizierer Qualität, die aus den Namen der Kultur, die durch ein Semikolon getrennt wird. Beispielsweise kann ein Eintrag für die Kultur fr-FR Form dauern `fr-FR;q=0.7`.  
  
 Im Beispiel wird die <xref:System.Globalization.CultureInfo.%23ctor%2A> Konstruktor mit seiner `useUserOverride` Parametersatz auf `false` zum Erstellen eines neuen <xref:System.Globalization.CultureInfo> Objekt. Dadurch wird sichergestellt, dass, wenn der Name der Kultur der Standardname für die Kultur auf dem Server ist die neue <xref:System.Globalization.CultureInfo> Objekt erstellt, indem der Konstruktor der Klasse enthält die Standardeinstellungen für eine Kultur und reflektiert keine Einstellungen, die mit des Servers überschrieben  **Regionalen und Sprachoptionen** Anwendung. Die Werte in "alle Einstellungen außer Kraft gesetzte" auf dem Server sind wahrscheinlich nicht auf dem System des Benutzers vorhanden ist oder in der Eingabe des Benutzers berücksichtigt werden.  
  
 Kann Ihren Code rufen Sie entweder die `Parse` oder `TryParse` Methode des numerischen Typs, der die Benutzereingabe wird in konvertiert werden. Wiederholte Aufrufe an eine Analysemethode können für eine einzelnes Analysevorgang erforderlich sein. Daher die `TryParse` Methode ist besser, weil sie zurückgibt `false` Wenn es sich bei einem Analysevorgang misslingt. Im Gegensatz dazu Behandeln der wiederholten Ausnahmen, die von ausgelöst werden möglicherweise die `Parse` Methode kann ein sehr ressourcenintensiver Vorgang in einer Webanwendung sein.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um den Code zu kompilieren, kopieren Sie ihn in ein [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Code-Behind-Seite, damit diese sie den vorhandenen Code ersetzt. Die [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Webseite sollte die folgenden Steuerelemente enthalten:  
  
-   Ein <xref:System.Web.UI.WebControls.Label> -Steuerelement, das nicht im Code verwiesen wird. Legen Sie seine <xref:System.Web.UI.WebControls.TextBox.Text%2A> -Eigenschaft auf "Geben Sie eine Zahl:".  
  
-   Ein <xref:System.Web.UI.WebControls.TextBox>-Steuerelement namens `NumericString`.  
  
-   Ein <xref:System.Web.UI.WebControls.Button>-Steuerelement namens `OKButton`. Legen Sie dessen <xref:System.Web.UI.WebControls.Button.Text%2A> Eigenschaft auf "OK".  
  
 Ändern Sie den Namen der Klasse aus `NumericUserInput` auf den Namen der Klasse, die von definiert wird die `Inherits` Attribut des der [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Seite `Page` Richtlinie. Ändern Sie den Namen des der `NumericInput` -Objektverweis auf den Namen von definiert die `id` Attribut der [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Seite `form` Tag.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Um zu verhindern, dass einen Benutzer Räumen Skript in den HTML-Stream, sollte eine Benutzereingabe nie direkt wieder in die Antwort des Servers wiederholt werden. Sie sollten stattdessen codiert werden, mithilfe der <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType> Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [Durchführen von Formatierungsvorgängen](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [Verarbeiten numerischer Zeichenfolgen](../../../docs/standard/base-types/parsing-numeric.md)

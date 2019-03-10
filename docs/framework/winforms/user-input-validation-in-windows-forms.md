---
title: Validierung von Benutzereingaben in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
ms.openlocfilehash: fb804e6596de14d93ec6f0405480b60c03c7cbf9
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711316"
---
# <a name="user-input-validation-in-windows-forms"></a>Validierung von Benutzereingaben in Windows Forms
Wenn Benutzer Daten in Ihre Anwendung eingeben, empfiehlt es sich um sicherzustellen, dass die Daten gültig sind, bevor Sie Ihre Anwendung verwendet. Sie erfordern, dass bestimmte Textfelder nicht mit der Länge Null, ein Feld als eine Telefonnummer oder andere Art von wohlgeformte Daten formatiert werden, oder, dass eine Zeichenfolge keine unsicheren Zeichen enthalten, die zur Beeinträchtigung der Sicherheit einer Datenbank verwendet werden können. Windows Forms bietet mehrere Möglichkeiten zum Überprüfen der Eingabe in Ihrer Anwendung.  
  
## <a name="validation-with-the-maskedtextbox-control"></a>Validierung mit dem MaskedTextBox-Steuerelement  
 Wenn Sie Benutzer zur Eingabe von Daten in ein klar definiertes Format aufweisen, z. B. eine Telefonnummer oder eine Teilenummer, erfordern müssen erreichen Sie dies schnell und mit minimalem Code mithilfe der <xref:System.Windows.Forms.MaskedTextBox> Steuerelement. Ein *Maske* ist eine Zeichenfolge, die Zeichen aus einer Maskierungssprache, der angibt, welche Zeichen, die an einer bestimmten Position in das Textfeld eingegeben werden können. Das Steuerelement zeigt eine Reihe von Anweisungen für den Benutzer. Wenn der Benutzer einen unzulässigen Eintrag eingibt, z. B. der Benutzer einen Buchstaben eingibt, wenn eine Ziffer erforderlich ist, die das Steuerelement die Eingabe automatisch abgelehnt.  
  
 Die Maskierungssprache, mit dem <xref:System.Windows.Forms.MaskedTextBox> ist sehr flexibel. Sie können Sie erforderliche Zeichen, optionale Zeichen, einem Literalzeichen, z. B. Bindestriche und Klammern, Währungszeichen und Datumstrennzeichen angeben. Das Steuerelement funktioniert auch gut mit einer Datenquelle gebunden. Die <xref:System.Windows.Forms.Binding.Format> Ereignis für eine Datenbindung kann verwendet werden, um eingehende Daten zur Einhaltung der Maske neu zu formatieren und die <xref:System.Windows.Forms.Binding.Parse> -Ereignis kann verwendet werden, um ausgehende Daten zur Einhaltung der Spezifikationen des Datenfelds neu zu formatieren.  
  
 Weitere Informationen finden Sie unter [MaskedTextBox-Steuerelement](./controls/maskedtextbox-control-windows-forms.md).  
  
## <a name="event-driven-validation"></a>Ereignisgesteuerte Überprüfung  
 Wenn Sie vollständige programmgesteuerte Kontrolle über die Validierung möchten oder komplexe validierungsüberprüfungen durchführen müssen, sollten Sie die Überprüfung-Ereignisse, die in den meisten Windows Forms-Steuerelemente integriert verwenden. Jedes Steuerelement, das freier Form Benutzereingaben akzeptiert hat eine <xref:System.Windows.Forms.Control.Validating> -Ereignis, das erfolgt, wenn das Steuerelement die datenvalidierung erfordert. In der <xref:System.Windows.Forms.Control.Validating> Ereignisbehandlungsmethode, Sie können überprüfen, eine Benutzereingabe auf verschiedene Weise. Wenn Sie ein Textfeld, die eine Postleitzahl enthalten muss verfügen, können Sie z. B. die Überprüfung auf folgende Weise ausführen:  
  
-   Wenn die Postleitzahl für eine bestimmte Gruppe von Postleitzahlen gehören muss, können Sie einen Zeichenfolgenvergleich für die Eingabe zum Überprüfen der vom Benutzer eingegebenen Daten ausführen. Z. B. wenn die Postleitzahl in den Satz {10001, 10002 10003} sein muss, können klicken Sie dann einen Zeichenfolgenvergleich Sie um die Daten zu überprüfen.  
  
-   Wenn die Postleitzahl in einem bestimmten Formular sein muss können Sie reguläre Ausdrücke verwenden, zum Überprüfen der Daten, die vom Benutzer eingegeben werden. So überprüfen das Formular beispielsweise `#####` oder `#####-####`, können Sie den regulären Ausdruck `^(\d{5})(-\d{4})?$`. So überprüfen das Formular `A#A #A#`, können Sie den regulären Ausdruck `[A-Z]\d[A-Z] \d[A-Z]\d`. Weitere Informationen zu regulären Ausdrücken finden Sie unter [reguläre Ausdrücke von .NET Framework](../../standard/base-types/regular-expressions.md) und [Beispiele für reguläre Ausdrücke](../../standard/base-types/regular-expression-examples.md).  
  
-   Wenn die Postleitzahl in eine gültige Postleitzahl der Vereinigten Staaten sein muss, können Sie zum Überprüfen der Daten vom Benutzer eingegebene Postleitzahl Webdienst aufrufen.  
  
 Die <xref:System.Windows.Forms.Control.Validating> Ereignis angegeben wird ein Objekt des Typs <xref:System.ComponentModel.CancelEventArgs>. Wenn Sie feststellen, dass die Daten des Steuerelements nicht gültig ist, können Sie Abbrechen der <xref:System.Windows.Forms.Control.Validating> -Ereignisses durch Festlegen dieses Objekts <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> Eigenschaft `true`. Wenn Sie nicht Festlegen der <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> -Eigenschaft, Windows Forms werden angenommen, die Validierung erfolgreich war, für das Steuerelement, und erhöhen die <xref:System.Windows.Forms.Control.Validated> Ereignis.  
  
 Ein Codebeispiel, das überprüft, eine e-Mail-Adresse in ob einem <xref:System.Windows.Controls.TextBox>, finden Sie unter <xref:System.Windows.Forms.Control.Validating>.  
  
### <a name="data-binding-and-event-driven-validation"></a>Die Datenbindung und das ereignisgesteuerte Überprüfung  
 Überprüfung ist sehr nützlich, wenn Sie Ihre Steuerelemente mit einer Datenquelle, z. B. eine Datenbanktabelle gebunden haben. Mithilfe der Validierung können Sie sicherstellen kann, dass die Daten des Steuerelements entspricht das Format, die von der Datenquelle erforderlich sind, dass sie nicht sichern und keine wie z. B. Anführungszeichen Sonderzeichen,, die Schrägstrichen unsichere sein.  
  
 Wenn Sie die Datenbindung verwenden, die Daten in Ihrem Steuerelement synchronisiert mit der Datenquelle während der Ausführung der <xref:System.Windows.Forms.Control.Validating> Ereignis. Wenn Sie Abbrechen der <xref:System.Windows.Forms.Control.Validating> Ereignis die Daten werden nicht mit der Datenquelle synchronisiert werden.  
  
> [!IMPORTANT]
>  Wenn Sie benutzerdefinierte Validierung, die ausgeführt wird verfügen, nachdem die <xref:System.Windows.Forms.Control.Validating> Ereignis wirkt sich nicht die Datenbindung. Angenommen, Sie über Code verfügen, einem <xref:System.Windows.Forms.Control.Validated> Ereignis, das versucht, das die Datenbindung abzubrechen, das die Datenbindung erfolgt weiterhin. In diesem Fall für die Validierung in der <xref:System.Windows.Forms.Control.Validated> Ereignis des Steuerelements ändern **Datenquellen-Aktualisierungsmodus** Eigenschaft (**unter (Databindings)**\\ **(Erweitert)** ) von **OnValidation** zu **nie**, und fügen *Steuerelement*`.DataBindings["`*\<YOURFIELD >*  `"].WriteValue()` an Ihrem Überprüfungscode.  
  
### <a name="implicit-and-explicit-validation"></a>Implizite und explizite Überprüfung  
 Also wenn überprüft die Daten im Steuerelement? Dies liegt an Ihnen als Entwickler. Sie können entweder implizit oder explizit Überprüfung je nach den Anforderungen Ihrer Anwendung verwenden.  
  
#### <a name="implicit-validation"></a>Implizite Validierung  
 Der Ansatz für die implizite Validierung überprüft Daten, wie der Benutzer es eingibt. Sie können die Daten überprüfen, wenn die Daten in mindestens ein Steuerelement durch die Schlüssel lesen, gedrückten eingegeben werden, häufig auf, wenn der Benutzer von einem Steuerelement den Eingabefokus besitzt wird, und zur nächsten wechselt. Dieser Ansatz ist hilfreich, wenn der Benutzer sofort Feedback zu den Daten zu erhalten, während der Arbeit verwendet werden sollen.  
  
 Wenn Sie die implizite Validierung für ein Steuerelement verwenden möchten, müssen Sie festlegen, dass dieses Steuerelements <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> Eigenschaft `true`. Wenn Sie Abbrechen der <xref:System.Windows.Forms.Control.Validating> -Ereignis, das Verhalten des Steuerelements wird durch diese zugewiesene Wert bestimmt, <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>. Wenn Sie zugewiesen <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>, Abbrechen des Ereignisses führt dazu, dass die <xref:System.Windows.Forms.Control.Validated> -Ereignis nicht auftreten. Klicken Sie auf das aktuelle Steuerelement wird Eingabefokus bleibt, bis der Benutzer die Daten in eine gültige Eingabe ändert. Wenn Sie zugewiesen <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>, <xref:System.Windows.Forms.Control.Validated> Ereignis wird nicht auftreten, wenn Sie das Ereignis abzubrechen, den Fokus wird jedoch trotzdem auf das nächste Steuerelement.  
  
 Zuweisen von <xref:System.Windows.Forms.AutoValidate.Disable> auf die <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> Eigenschaft wird verhindert, dass implizite Validierung vollständig. Um Steuerelemente zu überprüfen, müssen Sie zur Verwendung der expliziten Überprüfung.  
  
#### <a name="explicit-validation"></a>Explizite Validierung  
 Der expliziten Validierung überprüft Daten gleichzeitig an. Sie können die Daten als Antwort auf eine Benutzeraktion wie das Klicken auf eine Schaltfläche "Speichern" oder ein weiter-Link überprüfen. Wenn die Benutzeraktion auftritt, können Sie explizite Validierung in einem der folgenden Arten auslösen:  
  
-   Rufen Sie <xref:System.Windows.Forms.ContainerControl.Validate%2A> überprüft das letzte Steuerelement aus, um den Fokus verloren haben.  
  
-   Rufen Sie <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> alle untergeordneten Steuerelemente in einem Formular oder Container-Steuerelement zu überprüfen.  
  
-   Rufen Sie eine benutzerdefinierte Methode zum Überprüfen der Daten in den Steuerelementen manuell.  
  
#### <a name="default-implicit-validation-behavior-for-windows-forms-controls"></a>Implizite Validierung-Standardverhalten für Windows Forms-Steuerelementen  
 Andere Windows Forms-Steuerelemente haben unterschiedliche Standardwerte für ihre <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> Eigenschaft. Die folgende Tabelle zeigt die am häufigsten verwendeten Steuerelemente und ihre Standardwerte.  
  
|Steuerelement|Standardverhalten für die Validierung|  
|-------------|---------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
|<xref:System.Windows.Forms.PropertyGrid>|Eigenschaft, die nicht in Visual Studio verfügbar gemacht.|  
|<xref:System.Windows.Forms.ToolStripContainer>|Eigenschaft, die nicht in Visual Studio verfügbar gemacht.|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
  
## <a name="closing-the-form-and-overriding-validation"></a>Schließen des Formulars und Überschreiben der Validierung  
 Wenn ein Steuerelement den Fokus verwaltet, da die darin enthaltenen Daten ungültig sind, ist es unmöglich, schließen Sie das übergeordnete Formular in einer der üblichen Methoden:  
  
-   Durch Klicken auf die **schließen** Schaltfläche.  
  
-   Durch Auswahl **schließen** in die **System** Menü.  
  
-   Durch Aufrufen der <xref:System.Windows.Forms.Form.Close%2A> Methode programmgesteuert.  
  
 In einigen Fällen möchten jedoch möglicherweise kann der Benutzer, schließen Sie das Formular, unabhängig davon, ob die Werte in den Steuerelementen gültig sind. Kann außer Kraft setzen Überprüfung und ein Formular, das weiterhin ungültige Daten enthält, erstellen Sie einen Handler für des Formulars geschlossen <xref:System.Windows.Forms.Form.Closing> Ereignis. Legen Sie das Ereignis die <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> Eigenschaft `false`. Dies erzwingt, dass das Formular zu schließen. Weitere Informationen und ein Beispiel finden Sie unter <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Wenn Sie das Formular, um auf diese Weise schließen erzwingen, bleibt Daten in den Steuerelementen des Formulars, die noch nicht gespeichert wurde. Darüber hinaus überprüfen modale Formulare nicht den Inhalt der Steuerelemente, wenn sie geschlossen werden. Sie können die Validierung von Steuerelementen weiterhin verwenden, um den Fokus auf ein Steuerelement zu sperren, aber Sie müssen keine Gedanken über das Verhalten für das Formular geschlossen werden.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>
- <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType>
- [MaskedTextBox-Steuerelement](./controls/maskedtextbox-control-windows-forms.md)
- [Beispiele für reguläre Ausdrücke](../../standard/base-types/regular-expression-examples.md)

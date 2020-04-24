---
title: Benutzereingabevalidierung
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
ms.openlocfilehash: eafbf54552566011fef9d2dbeb5e9f9fa3facabd
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646303"
---
# <a name="user-input-validation-in-windows-forms"></a>Validierung von Benutzereingaben in Windows Forms
Wenn Benutzer Daten in Ihre Anwendung eingeben, können Sie überprüfen, ob die Daten gültig sind, bevor die Anwendung sie verwendet. Sie können verlangen, dass bestimmte Textfelder keine Länge von Null haben, dass ein Feld als Telefonnummer oder andere Arten von wohlgeformten Daten formatiert wird oder dass eine Zeichenfolge keine unsicheren Zeichen enthält, die verwendet werden könnten, um die Sicherheit einer Datenbank zu gefährden. Windows Forms bietet mehrere Möglichkeiten zum Überprüfen von Eingaben in Ihrer Anwendung.  
  
## <a name="validation-with-the-maskedtextbox-control"></a>Validierung mit dem MaskedTextBox-Steuerelement  
 Wenn Sie von Benutzern verlangen müssen, dass sie Daten in einem genau definierten Format eingeben, z. B. <xref:System.Windows.Forms.MaskedTextBox> eine Telefonnummer oder eine Teilenummer, können Sie dies schnell und mit minimalem Code mithilfe des Steuerelements erreichen. Eine *Maske* ist eine Zeichenfolge, die aus Zeichen aus einer Maskierungssprache besteht, die angibt, welche Zeichen an einer bestimmten Position im Textfeld eingegeben werden können. Das Steuerelement zeigt dem Benutzer eine Reihe von Eingabeaufforderungen an. Wenn der Benutzer z. B. einen falschen Eintrag eingibt, gibt der Benutzer einen Buchstaben ein, wenn eine Ziffer erforderlich ist, das Steuerelement weist die Eingabe automatisch zurück.  
  
 Die Maskierungssprache, <xref:System.Windows.Forms.MaskedTextBox> die von verwendet wird, ist sehr flexibel. Sie können erforderliche Zeichen, optionale Zeichen, Literalzeichen wie Bindestriche und Klammern, Währungszeichen und Datumstrennzeichen angeben. Das Steuerelement funktioniert auch gut, wenn es an eine Datenquelle gebunden ist. Das <xref:System.Windows.Forms.Binding.Format> Ereignis für eine Datenbindung kann verwendet werden, um eingehende Daten <xref:System.Windows.Forms.Binding.Parse> neu zu formatieren, um der Maske zu entsprechen, und das Ereignis kann verwendet werden, um ausgehende Daten so neu zu formatieren, dass sie den Spezifikationen des Datenfelds entsprechen.  
  
 Weitere Informationen finden Sie unter [MaskedTextBox Control](./controls/maskedtextbox-control-windows-forms.md).  
  
## <a name="event-driven-validation"></a>Ereignisgesteuerte Validierung  
 Wenn Sie eine vollständige programmgesteuerte Kontrolle über die Validierung wünschen oder komplexe Validierungsprüfungen durchführen möchten, sollten Sie die Validierungsereignisse verwenden, die in den meisten Windows Forms-Steuerelementen integriert sind. Jedes Steuerelement, das Freiformbenutzereingaben akzeptiert, verfügt über ein <xref:System.Windows.Forms.Control.Validating> Ereignis, das immer dann auftritt, wenn das Steuerelement eine Datenüberprüfung erfordert. In <xref:System.Windows.Forms.Control.Validating> der Ereignisbehandlungsmethode können Sie Benutzereingaben auf verschiedene Weise überprüfen. Wenn Sie z. B. über ein Textfeld verfügen, das eine Postleitzahl enthalten muss, können Sie die Überprüfung wie folgt durchführen:  
  
- Wenn die Postleitzahl zu einer bestimmten Gruppe von Postleitzahlen gehören muss, können Sie einen Zeichenfolgenvergleich für die Eingabe durchführen, um die vom Benutzer eingegebenen Daten zu überprüfen. Wenn sich z. B. die Postleitzahl in der Menge 10001, 10002, 10003 befinden muss, können Sie einen Zeichenfolgenvergleich verwenden, um die Daten zu überprüfen.  
  
- Wenn die Postleitzahl in einem bestimmten Formular sein muss, können Sie reguläre Ausdrücke verwenden, um die vom Benutzer eingegebenen Daten zu überprüfen. Um z. B. `#####` `#####-####`das Formular oder zu `^(\d{5})(-\d{4})?$`überprüfen, können Sie den regulären Ausdruck verwenden. Um das `A#A #A#`Formular zu überprüfen, `[A-Z]\d[A-Z] \d[A-Z]\d`können Sie den regulären Ausdruck verwenden. Weitere Informationen zu regulären Ausdrücken finden Sie unter [.NET Framework Regular Expressions](../../standard/base-types/regular-expressions.md) and [Regular Expression Examples](../../standard/base-types/regular-expression-example-scanning-for-hrefs.md).  
  
- Wenn es sich bei der Postleitzahl um eine gültige POSTleitzahl in den Vereinigten Staaten sein muss, können Sie einen Postleitzahl-Webdienst aufrufen, um die vom Benutzer eingegebenen Daten zu überprüfen.  
  
 Das <xref:System.Windows.Forms.Control.Validating> Ereignis wird als <xref:System.ComponentModel.CancelEventArgs>Objekt vom Typ angegeben. Wenn Sie feststellen, dass die Daten des Steuerelements <xref:System.Windows.Forms.Control.Validating> ungültig sind, können <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> Sie `true`das Ereignis abbrechen, indem Sie die Eigenschaft dieses Objekts auf festlegen. Wenn Sie die <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> Eigenschaft nicht festlegen, geht Windows Forms davon aus, dass die Überprüfung für dieses Steuerelement erfolgreich war, und hebt das <xref:System.Windows.Forms.Control.Validated> Ereignis auf.  
  
 Ein Codebeispiel, das eine E-Mail-Adresse in einem <xref:System.Windows.Controls.TextBox>überprüft, finden Sie unter <xref:System.Windows.Forms.Control.Validating>.  
  
### <a name="data-binding-and-event-driven-validation"></a>Datenbindung und ereignisgesteuerte Validierung  
 Die Validierung ist sehr nützlich, wenn Sie Ihre Steuerelemente an eine Datenquelle, z. B. eine Datenbanktabelle, gebunden haben. Mithilfe der Validierung können Sie sicherstellen, dass die Daten des Steuerelements das für die Datenquelle erforderliche Format erfüllt und keine Sonderzeichen wie Anführungszeichen und umgekehrte Schrägstriche enthalten, die möglicherweise unsicher sind.  
  
 Wenn Sie die Datenbindung verwenden, werden die Daten in Ihrem <xref:System.Windows.Forms.Control.Validating> Steuerelement während der Ausführung des Ereignisses mit der Datenquelle synchronisiert. Wenn Sie <xref:System.Windows.Forms.Control.Validating> das Ereignis abbrechen, werden die Daten nicht mit der Datenquelle synchronisiert.  
  
> [!IMPORTANT]
> Wenn Sie über eine benutzerdefinierte <xref:System.Windows.Forms.Control.Validating> Validierung verfügen, die nach dem Ereignis stattfindet, wirkt sich dies nicht auf die Datenbindung aus. Wenn Sie z. B. <xref:System.Windows.Forms.Control.Validated> Code in einem Ereignis haben, das versucht, die Datenbindung abzubrechen, wird die Datenbindung weiterhin ausgeführt. Ändern Sie in diesem <xref:System.Windows.Forms.Control.Validated> Fall, um die Validierung im Ereignis durchzuführen, die Eigenschaft **"Datenquellenaktualisierungsmodus"** ( unter **(Datenbindungen)**\\ **(Erweitert)**) von **OnValidation** in **Never**, und fügen Sie *Control*`.DataBindings["`*\<YOURFIELD>* `"].WriteValue()` zu Ihrem Validierungscode hinzu.  
  
### <a name="implicit-and-explicit-validation"></a>Implizite und explizite Validierung  
 Wann werden also die Daten eines Steuerelements validiert? Dies liegt an Ihnen, dem Entwickler. Je nach den Anforderungen Ihrer Anwendung können Sie eine implizite oder explizite Validierung verwenden.  
  
#### <a name="implicit-validation"></a>Implizite Validierung  
 Der implizite Validierungsansatz überprüft Daten, wenn der Benutzer sie eingibt. Sie können die Daten überprüfen, wenn die Daten in ein Steuerelement eingegeben werden, indem Sie die Tasten lesen, während sie gedrückt werden, oder häufiger, wenn der Benutzer den Eingabefokus von einem Steuerelement entfernt und zum nächsten verschoben wird. Dieser Ansatz ist nützlich, wenn Sie dem Benutzer sofort Feedback zu den Daten geben möchten, während sie funktionieren.  
  
 Wenn Sie die implizite Validierung für ein Steuerelement verwenden <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> möchten, müssen Sie die Eigenschaft dieses Steuerelements auf <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange> oder <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>festlegen. Wenn Sie <xref:System.Windows.Forms.Control.Validating> das Ereignis abbrechen, wird das Verhalten des Steuerelements <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>durch den Wert bestimmt, den Sie der zugewiesen haben. Wenn Sie <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>zugewiesen haben, führt <xref:System.Windows.Forms.Control.Validated> das Abbrechen des Ereignisses dazu, dass das Ereignis nicht eintritt. Der Eingabefokus bleibt auf dem aktuellen Steuerelement, bis der Benutzer die Daten in eine gültige Eingabe ändert. Wenn Sie <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>zugewiesen <xref:System.Windows.Forms.Control.Validated> haben, tritt das Ereignis nicht auf, wenn Sie das Ereignis abbrechen, aber der Fokus ändert sich weiterhin zum nächsten Steuerelement.  
  
 Das <xref:System.Windows.Forms.AutoValidate.Disable> Zuweisen <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> zur Eigenschaft verhindert eine implizite Validierung. Um Ihre Steuerelemente zu validieren, müssen Sie eine explizite Validierung verwenden.  
  
#### <a name="explicit-validation"></a>Explizite Validierung  
 Der explizite Validierungsansatz überprüft Daten gleichzeitig. Sie können die Daten als Reaktion auf eine Benutzeraktion überprüfen, z. B. durch Klicken auf eine Schaltfläche Speichern oder einen Link Weiter. Wenn die Benutzeraktion auftritt, können Sie die explizite Validierung auf eine der folgenden Arten auslösen:  
  
- Rufen <xref:System.Windows.Forms.ContainerControl.Validate%2A> Sie auf, um zu überprüfen, ob das letzte Steuerelement den Fokus verloren hat.  
  
- Aufruf <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> zum Überprüfen aller untergeordneten Steuerelemente in einem Formular- oder Containersteuerelement.  
  
- Rufen Sie eine benutzerdefinierte Methode auf, um die Daten in den Steuerelementen manuell zu überprüfen.  
  
#### <a name="default-implicit-validation-behavior-for-windows-forms-controls"></a>Standardmäßiges implizites Validierungsverhalten für Windows Forms-Steuerelemente  
 Verschiedene Windows Forms-Steuerelemente haben <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> unterschiedliche Standardeinstellungen für ihre Eigenschaft. Die folgende Tabelle zeigt die gängigsten Steuerelemente und deren Standardeinstellungen.  
  
|Control|Standardvalidierungsverhalten|  
|-------------|---------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
|<xref:System.Windows.Forms.PropertyGrid>|Eigenschaft, die in Visual Studio nicht verfügbar gemacht wird|  
|<xref:System.Windows.Forms.ToolStripContainer>|Eigenschaft, die in Visual Studio nicht verfügbar gemacht wird|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
  
## <a name="closing-the-form-and-overriding-validation"></a>Schließen des Formulars und Überschreiben der Validierung  
 Wenn ein Steuerelement den Fokus behält, weil die darin enthaltenen Daten ungültig sind, ist es nicht möglich, das übergeordnete Formular auf eine der üblichen Arten zu schließen:  
  
- Klicken Sie auf die Schaltfläche **Schließen.**  
  
- Wenn Sie im **Menü System** **schließen** auswählen.  
  
- Durch programmgesteuertes Aufrufen der <xref:System.Windows.Forms.Form.Close%2A> Methode.  
  
 In einigen Fällen können Sie dem Benutzer jedoch das Schließen des Formulars unabhängig davon, ob die Werte in den Steuerelementen gültig sind, das Formular schließen lassen. Sie können die Validierung überschreiben und ein Formular schließen, das weiterhin <xref:System.Windows.Forms.Form.FormClosing> ungültige Daten enthält, indem Sie einen Handler für das Ereignis des Formulars erstellen. Legen Sie im <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> Ereignis `false`die Eigenschaft auf . Dies zwingt das Formular zu schließen. Weitere Informationen und ein Beispiel finden Sie unter <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>.  
  
> [!NOTE]
> Wenn Sie das Schließen des Formulars auf diese Weise erzwingen, gehen alle Daten in den Steuerelementen des Formulars verloren, die noch nicht gespeichert wurden. Darüber hinaus überprüfen Modalformulare den Inhalt von Steuerelementen nicht, wenn sie geschlossen werden. Sie können die Steuerelementüberprüfung weiterhin verwenden, um den Fokus auf ein Steuerelement zu sperren, aber Sie müssen sich keine Gedanken über das Verhalten machen, das mit dem Schließen des Formulars verbunden ist.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>
- <xref:System.Windows.Forms.FormClosingEventArgs?displayProperty=nameWithType>
- [MaskedTextBox-Steuerelement](./controls/maskedtextbox-control-windows-forms.md)
- [Beispiele für reguläre Ausdrücke](../../standard/base-types/regular-expression-example-scanning-for-hrefs.md)

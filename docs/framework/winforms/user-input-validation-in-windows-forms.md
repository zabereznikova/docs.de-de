---
title: Validierung von Benutzereingaben in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
ms.openlocfilehash: 0a1d6c4c18e658d71f1baf90763e121314ea35d4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916298"
---
# <a name="user-input-validation-in-windows-forms"></a>Validierung von Benutzereingaben in Windows Forms
Wenn Benutzerdaten in die Anwendung eingeben, sollten Sie überprüfen, ob die Daten gültig sind, bevor Sie von Ihrer Anwendung verwendet werden. Möglicherweise ist es erforderlich, dass bestimmte Textfelder nicht die Länge 0 (null) aufweisen, dass ein Feld als Telefonnummer oder anderer Typ von wohlgeformten Daten formatiert wird, oder dass eine Zeichenfolge keine unsicheren Zeichen enthält, die zum kompromittieren der Sicherheit einer Datenbank verwendet werden können. Windows Forms bietet mehrere Möglichkeiten zum Überprüfen von Eingaben in Ihrer Anwendung.  
  
## <a name="validation-with-the-maskedtextbox-control"></a>Validierung mit dem MaskedTextBox-Steuerelement  
 Wenn Sie möchten, dass Benutzerdaten in einem klar definierten Format (z. b. eine Telefonnummer oder eine Teilenummer) eingeben, können Sie dies schnell und mit minimalem Code erreichen, indem <xref:System.Windows.Forms.MaskedTextBox> Sie das-Steuerelement verwenden. Eine *Maske* ist eine Zeichenfolge, die aus Zeichen aus einer Maskierungs Sprache besteht, die angibt, welche Zeichen an einer beliebigen Position im Textfeld eingegeben werden können. Das-Steuerelement zeigt dem Benutzer eine Reihe von Eingabe Aufforderungen an. Wenn der Benutzer einen falschen Eintrag eingibt, z. b. wenn der Benutzer einen Buchstaben eingibt, wenn eine Ziffer erforderlich ist, lehnt das Steuerelement die Eingabe automatisch ab.  
  
 Die von <xref:System.Windows.Forms.MaskedTextBox> verwendete Maskierungs Sprache ist sehr flexibel. Sie ermöglicht das Angeben von erforderlichen Zeichen, optionalen Zeichen, Literalzeichen, z. b. Bindestrichen und Klammern, Währungszeichen und Datums Trennzeichen. Das-Steuerelement funktioniert auch gut, wenn es an eine Datenquelle gebunden ist. Das <xref:System.Windows.Forms.Binding.Format> -Ereignis für eine Datenbindung kann verwendet werden, um eingehende Daten zur Einhaltung der Maske neu zu formatieren, und das <xref:System.Windows.Forms.Binding.Parse> -Ereignis kann verwendet werden, um ausgehende Daten neu zu formatieren, sodass Sie den Spezifikationen des Daten Felds entsprechen.  
  
 Weitere Informationen finden Sie unter [MaskedTextBox-Steuer](./controls/maskedtextbox-control-windows-forms.md)Element.  
  
## <a name="event-driven-validation"></a>Ereignisgesteuerte Validierung  
 Wenn Sie die vollständige programmgesteuerte Kontrolle über die Validierung benötigen oder komplexe Validierungs Überprüfungen durchführen möchten, sollten Sie die in den meisten Windows Forms Steuerelementen integrierten Validierungs Ereignisse verwenden. Jedes Steuerelement, das eine frei Form Eingabe akzeptiert, <xref:System.Windows.Forms.Control.Validating> verfügt über ein-Ereignis, das auftritt, wenn das Steuerelement eine Datenüberprüfung erfordert. In der <xref:System.Windows.Forms.Control.Validating> Ereignis Behandlungsmethode können Sie Benutzereingaben auf verschiedene Weise überprüfen. Wenn Sie z. b. ein Textfeld haben, das eine Postleitzahl enthalten muss, können Sie die Überprüfung wie folgt ausführen:  
  
- Wenn die Postleitzahl einer bestimmten Gruppe von Postleitzahlen angehören muss, können Sie einen Zeichen folgen Vergleich mit der Eingabe durchführen, um die vom Benutzer eingegebenen Daten zu überprüfen. Wenn die Postleitzahl beispielsweise im Satz {10001, 10002, 10003} sein muss, können Sie einen Zeichen folgen Vergleich verwenden, um die Daten zu validieren.  
  
- Wenn die Postleitzahl in einer bestimmten Form vorliegen muss, können Sie reguläre Ausdrücke verwenden, um die vom Benutzer eingegebenen Daten zu validieren. Wenn Sie z. b. das `#####` Formular `#####-####`oder überprüfen möchten, können Sie `^(\d{5})(-\d{4})?$`den regulären Ausdruck verwenden. Sie können den regulären `A#A #A#`Ausdruck `[A-Z]\d[A-Z] \d[A-Z]\d`verwenden, um das Formular zu validieren. Weitere Informationen zu regulären Ausdrücken finden Sie unter [.NET Framework reguläre Ausdrücke](../../standard/base-types/regular-expressions.md) und [Beispiele für reguläre](../../standard/base-types/regular-expression-examples.md)Ausdrücke.  
  
- Wenn die Postleitzahl ein gültiger USA ZIP-Code sein muss, können Sie einen Postleitzahl-Webdienst zum Überprüfen der vom Benutzer eingegebenen Daten abrufen.  
  
 Das <xref:System.Windows.Forms.Control.Validating> -Ereignis wird als Objekt des- <xref:System.ComponentModel.CancelEventArgs>Typs bereitgestellt. Wenn Sie feststellen, dass die Daten des Steuer Elements nicht gültig sind, können <xref:System.Windows.Forms.Control.Validating> Sie das Ereignis abbrechen, indem <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> Sie die `true`-Eigenschaft dieses Objekts auf festlegen. Wenn Sie die <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> -Eigenschaft nicht festlegen, nimmt Windows Forms an, dass die Überprüfung für dieses Steuerelement erfolgreich <xref:System.Windows.Forms.Control.Validated> war, und gibt das-Ereignis aus.  
  
 Ein Codebeispiel, in dem eine e-Mail-Adresse <xref:System.Windows.Controls.TextBox>in einem <xref:System.Windows.Forms.Control.Validating>validiert wird, finden Sie unter.  
  
### <a name="data-binding-and-event-driven-validation"></a>Datenbindung und ereignisgesteuerte Validierung  
 Die Überprüfung ist sehr nützlich, wenn Sie Ihre Steuerelemente an eine Datenquelle gebunden haben, z. b. eine Datenbanktabelle. Mithilfe der Validierung können Sie sicherstellen, dass die Daten des Steuer Elements das für die Datenquelle erforderliche Format erfüllen und keine Sonderzeichen wie Anführungszeichen und hinterstriche enthalten, die möglicherweise unsicher sind.  
  
 Wenn Sie die Datenbindung verwenden, werden die Daten im-Steuerelement während der Ausführung des <xref:System.Windows.Forms.Control.Validating> Ereignisses mit der Datenquelle synchronisiert. Wenn Sie das <xref:System.Windows.Forms.Control.Validating> Ereignis abbrechen, werden die Daten nicht mit der Datenquelle synchronisiert.  
  
> [!IMPORTANT]
> Wenn Sie über eine benutzerdefinierte Validierung verfügen, die <xref:System.Windows.Forms.Control.Validating> nach dem Ereignis erfolgt, wirkt sich dies nicht auf die Datenbindung aus. Wenn Sie z. b. Code in einem <xref:System.Windows.Forms.Control.Validated> -Ereignis haben, das versucht, die Datenbindung abzubrechen, erfolgt die Datenbindung weiterhin. Um in diesem Fall <xref:System.Windows.Forms.Control.Validated> die Validierung im Ereignis auszuführen, ändern Sie die Eigenschaft **Datenquellen-Aktualisierungs Modus** des Steuer Elements (**unter (DataBindings)** \\ **(erweitert)** ) von **OnValidation** in **Never**, und fügen Sie hinzu.Steuern`.DataBindings["`SieIhren`"].WriteValue()` Feld-> auf den Validierungscode. *\<*  
  
### <a name="implicit-and-explicit-validation"></a>Implizite und explizite Validierung  
 Wann werden die Daten eines Steuer Elements überprüft? Dies ist der Entwickler. Abhängig von den Anforderungen Ihrer Anwendung können Sie entweder implizite oder explizite Validierung verwenden.  
  
#### <a name="implicit-validation"></a>Implizite Validierung  
 Bei der impliziten Überprüfung werden Daten überprüft, während Sie vom Benutzer eingegeben werden. Sie können die Daten überprüfen, wenn die Daten in einem-Steuerelement eingegeben werden, indem Sie die Tasten lesen, wenn Sie gedrückt werden, oder häufiger, wenn der Benutzer den Eingabefokus von einem Steuerelement entfernt und zum nächsten wechselt. Diese Vorgehensweise ist nützlich, wenn Sie dem Benutzer umgehend Feedback zu den Daten geben möchten, während diese funktionieren.  
  
 Wenn Sie die implizite Validierung für ein Steuerelement verwenden möchten, müssen Sie die- <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> Eigenschaft dieses Steuer Elements auf `true`festlegen. Wenn Sie das <xref:System.Windows.Forms.Control.Validating> Ereignis abbrechen, wird das Verhalten des Steuer Elements durch den Wert bestimmt, den Sie <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>zugewiesen haben. Wenn Sie zugewiesen <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>haben, führt das Abbrechen des Ereignisses dazu <xref:System.Windows.Forms.Control.Validated> , dass das Ereignis nicht auftritt. Der Eingabefokus bleibt auf dem aktuellen Steuerelement, bis der Benutzer die Daten in eine gültige Eingabe ändert. Wenn Sie zugewiesen <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>haben, <xref:System.Windows.Forms.Control.Validated> tritt das Ereignis nicht auf, wenn Sie das Ereignis abbrechen, aber der Fokus wird weiterhin auf das nächste Steuerelement geändert.  
  
 Durch <xref:System.Windows.Forms.AutoValidate.Disable> die Zuweisung <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> zur-Eigenschaft wird die implizite Validierung vollständig verhindert. Zum Überprüfen der Steuerelemente müssen Sie die explizite Validierung verwenden.  
  
#### <a name="explicit-validation"></a>Explizite Validierung  
 Bei der expliziten Überprüfung werden Daten gleichzeitig überprüft. Sie können die Daten als Reaktion auf eine Benutzeraktion überprüfen, z. b. durch Klicken auf die Schaltfläche Speichern oder einen nächsten Link. Wenn die Benutzeraktion auftritt, können Sie eine explizite Validierung auf eine der folgenden Arten ausführen:  
  
- Ruft <xref:System.Windows.Forms.ContainerControl.Validate%2A> auf, um das letzte Steuerelement zu überprüfen, sodass der Fokus verloren  
  
- Wird <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> aufgerufen, um alle untergeordneten Steuerelemente in einem Formular oder Container Steuerelement zu überprüfen  
  
- Ruft eine benutzerdefinierte Methode auf, um die Daten in den Steuerelementen manuell zu validieren.  
  
#### <a name="default-implicit-validation-behavior-for-windows-forms-controls"></a>Standardmäßiges implizites Validierungs Verhalten für Windows Forms Steuerelemente  
 Verschiedene Windows Forms Steuerelemente haben unterschiedliche Standard <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> Werte für Ihre-Eigenschaft. In der folgenden Tabelle werden die gängigsten Steuerelemente und deren Standardwerte angezeigt.  
  
|Steuerelement|Standard Validierungs Verhalten|  
|-------------|---------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
|<xref:System.Windows.Forms.PropertyGrid>|Eigenschaft nicht verfügbar in Visual Studio|  
|<xref:System.Windows.Forms.ToolStripContainer>|Eigenschaft nicht verfügbar in Visual Studio|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
  
## <a name="closing-the-form-and-overriding-validation"></a>Schließen des Formulars und Überschreiben der Validierung  
 Wenn ein Steuerelement den Fokus erhält, weil die darin enthaltenen Daten ungültig sind, ist es nicht möglich, das übergeordnete Formular auf eine der üblichen Arten zu schließen:  
  
- Durch Klicken auf die Schaltfläche **Schließen** .  
  
- Durch Auswählen von **Schließen** im Menü **System** .  
  
- Durch Programm gesteuertes Aufrufen der <xref:System.Windows.Forms.Form.Close%2A> -Methode.  
  
 In einigen Fällen möchten Sie jedoch möglicherweise, dass der Benutzer das Formular schließt, unabhängig davon, ob die Werte in den Steuerelementen gültig sind. Durch Erstellen eines Handlers für das- <xref:System.Windows.Forms.Form.Closing> Ereignis des Formulars können Sie die Überprüfung überschreiben und ein Formular schließen, das noch ungültige Daten enthält. Legen Sie im-Ereignis die <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> -Eigenschaft `false`auf fest. Dadurch muss das Formular geschlossen werden. Weitere Informationen und ein Beispiel finden Sie unter <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>.  
  
> [!NOTE]
> Wenn Sie erzwingen, dass das Formular auf diese Weise geschlossen wird, gehen alle Daten in den Steuerelementen des Formulars, die noch nicht gespeichert wurden, verloren. Außerdem überprüfen modale Formulare nicht den Inhalt von Steuerelementen, wenn Sie geschlossen werden. Sie können die Steuerelement Validierung weiterhin verwenden, um den Fokus auf ein Steuerelement zu sperren, aber Sie müssen sich nicht um das Verhalten im Zusammenhang mit dem Schließen des Formulars kümmern.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>
- <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType>
- [MaskedTextBox-Steuerelement](./controls/maskedtextbox-control-windows-forms.md)
- [Beispiele für reguläre Ausdrücke](../../standard/base-types/regular-expression-examples.md)

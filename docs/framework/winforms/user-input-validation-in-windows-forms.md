---
title: Validierung von Benutzereingaben in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
ms.openlocfilehash: adc138ad1e277f69f27f9f86fc5c3ea28a8d5cce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541806"
---
# <a name="user-input-validation-in-windows-forms"></a>Validierung von Benutzereingaben in Windows Forms
Wenn Benutzer Daten in die Anwendung eingeben, empfiehlt es sich um sicherzustellen, dass die Daten gültig sind, bevor Sie Ihre Anwendung verwendet. Sie können erforderlich, dass bestimmte Textfelder werden nicht mit der Länge Null, dass ein Feld als eine Telefonnummer oder andere Arten von wohlgeformte Daten formatiert werden, dass eine Zeichenfolge keine unsicheren Zeichen enthält, die verwendet werden können, um die Sicherheit einer Datenbank zu gefährden. Windows Forms bietet mehrere Möglichkeiten zum Überprüfen der Eingabe in der Anwendung.  
  
## <a name="validation-with-the-maskedtextbox-control"></a>Validierung mit dem MaskedTextBox-Steuerelement  
 Wenn Sie Benutzer zur Eingabe von Daten in ein klar definiertes Format aufweisen, z. B. eine Telefonnummer oder eine Teilenummer erfordern müssen Sie erreichen dies schnell und mit minimalem Codeeinsatz mithilfe der <xref:System.Windows.Forms.MaskedTextBox> Steuerelement. Ein *Maske* ist eine Zeichenfolge, die aus der Zeichen in einer anderen Maskierungssprache, der angibt, welche Zeichen an einer bestimmten Position in das Textfeld eingegeben werden können. Das Steuerelement zeigt eine Reihe von Anweisungen für den Benutzer. Wenn der Benutzer einen unzulässigen Eintrag eingibt, z. B. der Benutzer einen Buchstaben eingibt, wenn eine Ziffer erforderlich ist, das Steuerelement die Eingabe automatisch abgelehnt.  
  
 Die Maskierungssprache, die von verwendet wird, <xref:System.Windows.Forms.MaskedTextBox> ist sehr flexibel. Es ermöglicht Ihnen das Festlegen der erforderlichen Zeichen, optionale Zeichen, einem Literalzeichen, z. B. Bindestriche und Klammern, Währungszeichen und Datumstrennzeichen. Das Steuerelement funktioniert auch, auch wenn mit einer Datenquelle gebunden. Die <xref:System.Windows.Forms.Binding.Format> Ereignis auf einer Bindung kann verwendet werden, um eingehende Daten zur Einhaltung der Maske neu zu formatieren und die <xref:System.Windows.Forms.Binding.Parse> Ereignis kann verwendet werden, um die ausgehende Daten zur Einhaltung von der Spezifikationen des Datenfelds neu zu formatieren.  
  
 Weitere Informationen finden Sie unter [MaskedTextBox-Steuerelement](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md).  
  
## <a name="event-driven-validation"></a>Ereignisgesteuerte Validierung  
 Wenn Sie vollständige programmgesteuerte Kontrolle über die Validierung möchten oder komplexe Überprüfungen durchführen müssen, sollten Sie die Validierungsereignisse integriert die meisten Windows Forms-Steuerelemente verwenden. Jedes Steuerelement, das Benutzereingaben Freiform-verfügt über eine <xref:System.Windows.Forms.Control.Validating> Ereignis, das erfolgt, wenn das Steuerelement die Validierung erfordert. In der <xref:System.Windows.Forms.Control.Validating> Ereignisbehandlungsmethode, überprüfen Sie Benutzereingaben auf unterschiedliche Weise. Wenn Sie ein Textfeld, die eine Postleitzahl enthalten muss verfügen, können Sie z. B. die Überprüfung auf folgende Weise ausführen:  
  
-   Wenn die Postleitzahl für eine bestimmte Gruppe von Postleitzahlen gehören muss, können Sie einen Zeichenfolgenvergleich für die Eingabe zum Überprüfen der vom Benutzer eingegebenen Daten ausführen. Z. B. wenn die Postleitzahl in der Menge {10001, 10002, 10003} sein muss, können klicken Sie dann einen Zeichenfolgenvergleich Sie zum Überprüfen der Daten.  
  
-   Wenn die Postleitzahl in einem bestimmten Format sein muss können Sie reguläre Ausdrücke, zum Überprüfen der Daten, die vom Benutzer eingegeben werden. So überprüfen Sie das Formular beispielsweise `#####` oder `#####-####`, können Sie den regulären Ausdruck `^(\d{5})(-\d{4})?$`. So überprüfen Sie das Formular `A#A #A#`, können Sie den regulären Ausdruck `[A-Z]\d[A-Z] \d[A-Z]\d`. Weitere Informationen zu regulären Ausdrücken finden Sie unter [reguläre Ausdrücke von .NET Framework](../../../docs/standard/base-types/regular-expressions.md) und [Beispiele für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-examples.md).  
  
-   Wenn die Postleitzahl in eine gültige Postleitzahl für die USA sein muss, können Sie einen Postleitzahl-Webdienst zum Überprüfen der vom Benutzer eingegebenen Daten aufrufen.  
  
 Die <xref:System.Windows.Forms.Control.Validating> Ereignis angegeben wird ein Objekt des Typs <xref:System.ComponentModel.CancelEventArgs>. Wenn Sie feststellen, dass die Daten des Steuerelements nicht gültig ist, können Sie Abbrechen der <xref:System.Windows.Forms.Control.Validating> -Ereignisses durch Festlegen dieses Objekts <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> Eigenschaft `true`. Wenn Sie nicht festlegen, die <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> -Eigenschaft, Windows Forms werden angenommen, die Validierung für dieses Steuerelement war erfolgreich und Auslösen der <xref:System.Windows.Forms.Control.Validated> Ereignis.  
  
 Ein Codebeispiel, das überprüft eine e-Mail-Adresse in einem <xref:System.Windows.Controls.TextBox>, finden Sie unter <xref:System.Windows.Forms.Control.Validating>.  
  
### <a name="data-binding-and-event-driven-validation"></a>Datenbindung und das ereignisgesteuerte Validierung  
 Validierung ist sehr nützlich, wenn Sie die Steuerelemente mit einer Datenquelle, z. B. eine Datenbanktabelle gebunden haben. Mithilfe der Validierung können Sie sicherstellen kann, dass Daten des Steuerelements erfüllt, die das Format von der Datenquelle erforderlich sind, und, dass sie keine Sonderzeichen wie z. B. Anführungszeichen enthalten und Sichern nicht, die Schrägstriche unsicher sein.  
  
 Wenn Sie die Datenbindung verwenden, die Daten in das Steuerelement synchronisiert mit der Datenquelle während der Ausführung der <xref:System.Windows.Forms.Control.Validating> Ereignis. Wenn Sie "Abbrechen" die <xref:System.Windows.Forms.Control.Validating> Ereignis, die Daten nicht mit der Datenquelle synchronisiert werden.  
  
> [!IMPORTANT]
>  Wenn Sie benutzerdefinierte Validierung, der stattfindet verfügen, nach der <xref:System.Windows.Forms.Control.Validating> Ereignis, wirkt sich nicht dem Datenbindung. Angenommen, Sie über Code verfügen, einem <xref:System.Windows.Forms.Control.Validated> Ereignis, das versucht, die Datenbindung abzubrechen, die Datenbindung wird nach wie vor erfolgen. In diesem Fall wird die Validierung in der <xref:System.Windows.Forms.Control.Validated> Ereignis, ändern Sie das Steuerelement **Datenquellen-Aktualisierungsmodus** Eigenschaft (**unter (Databindings)**\\ **(Erweitert)** ) von **OnValidation** auf **nie**, und fügen *Steuerelement*`.DataBindings["`*\<YOURFIELD >*  `"].WriteValue()` zu Validierungscodes.  
  
### <a name="implicit-and-explicit-validation"></a>Implizite und explizite Validierung  
 Also wenn überprüft ein Steuerelement Daten? Dies ist bis zu Ihnen als Entwickler. Sie können die Überprüfung von entweder implizit oder explizit, je nach den Anforderungen Ihrer Anwendung verwenden.  
  
#### <a name="implicit-validation"></a>Implizite Validierung  
 Der impliziten Validierung überprüft Daten, wie vom Benutzer eingegeben. Sie können die Daten überprüfen, wie die Daten in mindestens ein Steuerelement durch Lesen die Schlüssel gedrückten eingegeben werden, häufig auf, wenn der Benutzer den Eingabefokus von einem Steuerelement hat, und zur nächsten wechselt. Dieser Ansatz ist hilfreich, wenn auf das Benutzer unmittelbar Feedback zu den Daten zu erhalten, wie sie funktionieren sollen.  
  
 Wenn Sie für ein Steuerelement implizite Validierung verwenden möchten, müssen Sie festlegen, dass dieses Steuerelement <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> Eigenschaft `true`. Wenn Sie "Abbrechen" die <xref:System.Windows.Forms.Control.Validating> Ereignis, das Verhalten des Steuerelements sind davon abhängig, was Ihnen zugewiesene Wert <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>. Wenn Sie zugewiesen <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>, Abbrechen des Ereignisses führt dazu, dass die <xref:System.Windows.Forms.Control.Validated> Ereignis nicht auftreten. Eingabefokus verbleiben auf das aktuelle Steuerelement, bis der Benutzer die Daten in einen gültigen Wert ändert. Wenn Sie zugewiesen <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>die <xref:System.Windows.Forms.Control.Validated> Ereignis wird nicht auftreten, wenn Sie das Ereignis "Abbrechen", aber den Fokus sich weiterhin auf das nächste Steuerelement ändert.  
  
 Zuweisen von <xref:System.Windows.Forms.AutoValidate.Disable> auf die <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> Eigenschaft wird die implizite Validierung grundsätzlich verhindert. Um Steuerelemente zu überprüfen, müssen Sie die explizite Validierung verwenden.  
  
#### <a name="explicit-validation"></a>Explizite Validierung  
 Der expliziten Validierung überprüft Daten gleichzeitig an. Sie können die Daten als Antwort auf eine Benutzeraktion, wie das Klicken auf eine Schaltfläche "Speichern" oder einen Link weiter überprüfen. Wenn die Benutzeraktion auftritt, können Sie in einem der folgenden Arten explizite Validierung auslösen:  
  
-   Rufen Sie <xref:System.Windows.Forms.ContainerControl.Validate%2A> So überprüfen Sie das letzte Steuerelement aus, um den Fokus verloren haben.  
  
-   Rufen Sie <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> So überprüfen Sie alle untergeordneten Steuerelemente in einem Formular oder Container-Steuerelement.  
  
-   Rufen Sie eine benutzerdefinierte Methode, um die Daten in den Steuerelementen manuell überprüfen.  
  
#### <a name="default-implicit-validation-behavior-for-windows-forms-controls"></a>Implizite Validierung Standardverhalten für Windows Forms-Steuerelementen  
 Windows Forms-Steuerelemente haben unterschiedliche Standardwerte für ihre <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> Eigenschaft. Die folgende Tabelle zeigt die am häufigsten verwendeten Steuerelemente mit ihren Standardwerten.  
  
|Steuerelement|Standardverhalten für die Validierung|  
|-------------|---------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
|<xref:System.Windows.Forms.PropertyGrid>|Eigenschaft, die nicht in Visual Studio verfügbar gemacht.|  
|<xref:System.Windows.Forms.ToolStripContainer>|Eigenschaft, die nicht in Visual Studio verfügbar gemacht.|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
  
## <a name="closing-the-form-and-overriding-validation"></a>Das Formular geschlossen, und Überschreiben der Validierung  
 Wenn ein Steuerelement den Fokus verwaltet, da die darin enthaltenen Daten ungültig sind, ist es unmöglich, schließen Sie das übergeordnete Formular in einer der üblichen Methoden:  
  
-   Durch Klicken auf die **schließen** Schaltfläche.  
  
-   Durch Auswahl **schließen** in der **System** Menü.  
  
-   Durch Aufrufen der <xref:System.Windows.Forms.Form.Close%2A> -Methode programmgesteuert.  
  
 In einigen Fällen möchten jedoch möglicherweise kann der Benutzer, schließen Sie das Formular unabhängig davon, ob die Werte in den Steuerelementen gültig sind. Sie Überschreiben der Überprüfung und schließen Sie ein Formular, das immer noch ungültige Daten enthält, indem Sie einen Handler für des Formulars erstellen können <xref:System.Windows.Forms.Form.Closing> Ereignis. Legen Sie das Ereignis die <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> Eigenschaft `false`. Dies erzwingt, dass das Formular zu schließen. Weitere Informationen und ein Beispiel finden Sie unter <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Wenn Sie das Formular, um auf diese Weise schließen erzwingen, ist Daten in die Steuerelemente des Formulars, die nicht bereits gespeichert wurde, verloren. Darüber hinaus überprüfen modale Formulare nicht den Inhalt von Steuerelementen geschlossen werden. Weiterhin können Sie Steuerelement-Überprüfung So sperren Sie den Fokus auf ein Steuerelement, aber Sie müssen keine Gedanken über das Verhalten zugeordnet, die das Formular geschlossen werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>  
 <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType>  
 [MaskedTextBox-Steuerelement](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)  
 [Beispiele für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-examples.md)

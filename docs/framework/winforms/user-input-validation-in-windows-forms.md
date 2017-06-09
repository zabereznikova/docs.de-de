---
title: "Validierung von Benutzereingaben in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Benutzereingabe, Validieren in Windows Forms"
  - "Validieren von Benutzereingaben, Windows Forms"
  - "Überprüfung, Windows Forms-Benutzereingabe"
  - "Windows Forms, Validieren von Benutzereingaben"
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Validierung von Benutzereingaben in Windows Forms
Wenn Benutzer Daten in Ihre Anwendung eingeben, möchten Sie vielleicht überprüfen, ob die Daten gültig sind, bevor sie von der Anwendung verwendet werden.  Beispielsweise kann es erforderlich sein, dass bestimmte Textfelder nicht die Länge 0 haben, dass ein Feld als Telefonnummer oder als ähnlich wohlgeformtes Datenformat formatiert wird oder dass eine Zeichenfolge keine unsicheren Zeichen enthält, die die Sicherheit einer Datenbank beeinträchtigen könnten.  Windows Forms bieten mehrere Möglichkeiten, um Eingaben in der Anwendung zu überprüfen.  
  
## Validierung mit dem MaskedTextBox\-Steuerelement  
 Wenn Sie Benutzereingaben in einem wohlgeformten Format benötigen, beispielsweise im Telefon\- oder Teilenummernformat, lässt sich dies schnell und mit wenig Programmieraufwand realisieren. Sie verwenden dazu das <xref:System.Windows.Forms.MaskedTextBox>\-Steuerelement.  Eine *Maske* ist eine Zeichenfolge aus Zeichen in einer Maskingsprache, durch die festgelegt wird, welche Zeichen an einer bestimmten Position im Textfeld eingegeben werden dürfen.  Über das Steuerelement werden dem Benutzer eine Reihe von Aufforderungen angezeigt.  Wenn der Benutzer eine falsche Eingabe macht, also beispielsweise einen Buchstaben eingibt, während eine Ziffer benötigt wird, wird die Eingabe vom Steuerelement automatisch zurückgewiesen.  
  
 Die von <xref:System.Windows.Forms.MaskedTextBox> verwendete Maskingsprache ist sehr flexibel.  Sie ermöglicht es Ihnen, obligatorische Zeichen, optionale Zeichen, literale Zeichen wie Bindestriche und Klammen, Währungszeichen und Datumstrennzeichen festzulegen.  Das Steuerelement funktioniert auch, wenn es an eine Datenquelle gebunden ist.  Das <xref:System.Windows.Forms.Binding.Format>\-Ereignis für eine Datenbindung kann auch zum Neuformatieren eingehender Daten entsprechend der Maske und das <xref:System.Windows.Forms.Binding.Parse>\-Ereignis zum Neuformatieren ausgehender Daten entsprechend den Spezifikationen des Datenfeldes verwendet werden.  
  
 Weitere Informationen finden Sie unter [MaskedTextBox\-Steuerelement](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md).  
  
## Ereignisgesteuerte Validierung  
 Wenn die Validierung vollständig programmgesteuert ablaufen soll oder wenn umfangreiche Validierungen erforderlich sind, sollten Sie die Validierungsereignisse verwenden, die in die meisten Windows Forms\-Steuerelemente integriert sind.  Jedes Steuerelement, das formfreie Benutzereingaben akzeptiert, verfügt über ein <xref:System.Windows.Forms.Control.Validating>\-Ereignis, das eintritt, sobald das Steuerelement eine Datenvalidierung erfordert.  In der <xref:System.Windows.Forms.Control.Validating>\-Ereignisbehandlungsmethode können Sie Benutzereingaben auf mehrere Weisen überprüfen.  Wenn Sie beispielsweise über ein Textfeld verfügen, das eine Postleitzahl enthalten muss, können Sie die Validierung auf folgende Weisen ausführen:  
  
-   Wenn die Postleistzahl einer bestimmten Gruppe von PLZ\-Codes angehören muss, können Sie einen Zeichenfolgenvergleich für die Eingabe ausführen, um die vom Benutzer eingegebenen Daten zu überprüfen.  Wenn sich die Postleitzahl beispielsweise in der Menge {10001, 10002, 10003} befinden muss, können Sie zur Validierung der Daten einen Zeichenfolgenvergleich verwenden.  
  
-   Wenn die Postleitzahl in einem bestimmten Format vorliegen muss, können Sie zur Validierung der vom Benutzer eingegebenen Daten reguläre Ausdrücke verwenden.  Um beispielsweise das Format `#####` oder `#####-####` zu überprüfen, können Sie den regulären Ausdruck `^(\d{5})(-\d{4})?$` verwenden.  Um beispielsweise das Format `A#A #A#` zu überprüfen, können Sie den regulären Ausdruck `[A-Z]\d[A-Z] \d[A-Z]\d` verwenden.  Weitere Informationen zu regulären Ausdrücken finden Sie unter [Reguläre Ausdrücke von .NET Framework](../../../docs/standard/base-types/regular-expressions.md) und [Beispiele für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-examples.md).  
  
-   Wenn die Postleitzahl eine in den USA gültige Postleitzahl sein muss, können Sie einen Postleitzahlen\-Webdienst aufrufen, um die vom Benutzer eingegebenen Daten zu überprüfen.  
  
 Für das <xref:System.Windows.Forms.Control.Validating>\-Ereignis wird ein Objekt des Typs <xref:System.ComponentModel.CancelEventArgs> bereitgestellt.  Wenn Sie feststellen, dass die Daten des Steuerelements ungültig sind, können Sie das <xref:System.Windows.Forms.Control.Validating>\-Ereignis abbrechen, indem Sie die <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>\-Eigenschaft dieses Objekts auf `true` festlegen.  Wenn Sie die <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>\-Eigenschaft nicht festlegen, geht Windows Forms davon aus, dass die Validierung für dieses Steuerelement erfolgreich war, und das <xref:System.Windows.Forms.Control.Validated>\-Ereignis wird ausgelöst.  
  
 Ein Codebeispiel, durch das eine E\-Mail\-Adresse in einem <xref:System.Windows.Controls.TextBox> überprüft wird, finden Sie unter <xref:System.Windows.Forms.Control.Validating>.  
  
### Datenbindung und ereignisgesteuerte Validierung  
 Die Validierung ist sehr hilfreich, wenn Sie Steuerelemente an eine Datenquelle, z. B. eine Datenbanktabelle, gebunden haben.  Mithilfe der Validierung können Sie sicherstellen, dass die Daten des Steuerelements das Format aufweisen, das von der Datenquelle benötigt wird und dass keine Sonderzeichen wie Anführungszeichen und umgekehrte Schrägstriche enthalten sind, die sich als unsicher erweisen könnten.  
  
 Wenn Sie die Datenbindung verwenden, werden die Daten im Steuerelement während der Ausführung des <xref:System.Windows.Forms.Control.Validating>\-Ereignisses mit der Datenquelle synchronisiert.  Wenn Sie das <xref:System.Windows.Forms.Control.Validating>\-Ereignis abbrechen, werden die Daten nicht mit der Datenquelle synchronisiert.  
  
> [!IMPORTANT]
>  Wenn Sie über eine benutzerdefinierte Validierung verfügen, die nach dem <xref:System.Windows.Forms.Control.Validating>\-Ereignis stattfindet, wirkt sich dies nicht auf die Datenbindung aus.  Wenn Sie beispielsweise über Code in einem <xref:System.Windows.Forms.Control.Validated>\-Ereignis verfügen, der versucht, die Datenbindung aufzuheben, bleibt die Datenbindung weiterhin bestehen.  Um in diesem Fall eine Validierung im <xref:System.Windows.Forms.Control.Validated>\-Ereignis auszuführen, ändern Sie die **Datenquellen\-Aktualisierungsmodus**\-Eigenschaft des Steuerelements \(**unter \(Databindings\)**\\**\(Advanced\)**\) von **OnValidation** in **Never** und fügen dem Validierungscode *Control*`.DataBindings["`*\<YOURFIELD\>*`"].WriteValue()` hinzu.  
  
### Implizite und explizite Validierung  
 Wann werden die Daten eines Steuerelements überprüft?  Dies hängt vom Entwickler ab.  Sie können entweder die implizite oder explizite Validierung verwenden, je nachdem, welche Anforderungen Sie an Ihre Anwendung stellen.  
  
#### Implizite Validierung  
 Bei der impliziten Validierung werden die Daten überprüft, wenn sie vom Benutzer eingegeben werden.  Sie können die Daten während der Eingabe in ein Steuerelement überprüfen, indem Sie die Tastatureingaben lesen oder, was häufiger der Fall ist, verfolgen, wann der Benutzer den Eingabefokus von einem Steuerelement zum nächsten verschiebt.  Dieser Ansatz ist hilfreich, wenn Sie dem Benutzer während der Arbeit direktes Feedback zu den Daten geben möchten.  
  
 Wenn Sie die implizite Validierung für ein Steuerelement verwenden möchten, müssen Sie die <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>\-Eigenschaft dieses Steuerelements auf `true` festlegen.  Wenn Sie das <xref:System.Windows.Forms.Control.Validating>\-Ereignis abbrechen, richtet sich das Verhalten des Steuerelements nach dem Wert, den Sie <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> zugewiesen haben.  Wenn Sie <xref:System.Windows.Forms.AutoValidate> zugewiesen haben, bewirkt das Abbrechen des Ereignisses, dass das <xref:System.Windows.Forms.Control.Validated>\-Ereignis nicht eintritt.  Der Eingabefokus verbleibt beim aktuellen Steuerelement, bis der Benutzer die Daten in eine gültige Eingabe ändert.  Wenn Sie <xref:System.Windows.Forms.AutoValidate> zugewiesen haben, tritt das <xref:System.Windows.Forms.Control.Validated>\-Ereignis beim Abbrechen des Ereignisses nicht ein, der Fokus wird jedoch trotzdem an das nächste Steuerelement übergeben.  
  
 Indem Sie <xref:System.Windows.Forms.AutoValidate> zur <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>\-Eigenschaft zuweisen, wird die implizite Validierung grundsätzlich verhindert.  Um Steuerelemente zu überprüfen, müssen Sie die explizite Validierung verwenden.  
  
#### Explizite Validierung  
 Bei der expliziten Validierung werden die Daten zu einem bestimmten Zeitpunkt überprüft.  Sie können die Daten in Reaktion auf eine Benutzeraktion überprüfen, z. B. das Klicken auf eine Schaltfläche zum Speichern oder auf einen weiterführenden Link.  Wenn die Benutzeraktion eintritt, können Sie die explizite Validierung auf eine der folgenden Weisen auslösen:  
  
-   Rufen Sie <xref:System.Windows.Forms.ContainerControl.Validate%2A> auf, um das letzte Steuerelement zu überprüfen, das den Fokus hatte.  
  
-   Rufen Sie <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> auf, um alle untergeordneten Steuerelemente in einem Formular\- oder Containersteuerelement zu überprüfen.  
  
-   Rufen Sie eine benutzerdefinierte Methode auf, um die Daten in den Steuerelementen manuell zu überprüfen.  
  
#### Standardverhalten für Windows Forms\-Steuerelemente bei der impliziten Validierung  
 Windows Forms\-Steuerelemente verfügen jeweils über unterschiedliche Standardwerte für die <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>\-Eigenschaft.  In der folgenden Tabelle werden die am häufigsten verwendeten Steuerelemente mit ihren Standardwerten aufgeführt.  
  
|Steuerelement|Standardverhalten für die Validierung|  
|-------------------|-------------------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate>|  
|<xref:System.Windows.Forms.PropertyGrid>|In Visual Studio nicht verfügbar gemachte Eigenschaft|  
|<xref:System.Windows.Forms.ToolStripContainer>|In Visual Studio nicht verfügbar gemachte Eigenschaft|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate>|  
  
## Schließen des Formulars und Überschreiben der Validierung  
 Wenn ein Steuerelement den Fokus behält, weil die enthaltenen Daten ungültig sind, kann das übergeordnete Formular nicht auf eine der üblichen Weisen geschlossen werden:  
  
-   Durch Klicken auf die Schaltfläche **Schließen**  
  
-   Durch Auswählen von **Schließen** im **Systemmenü**  
  
-   Durch programmgesteuertes Aufrufen der <xref:System.Windows.Forms.Form.Close%2A>\-Methode  
  
 In einigen Fällen soll der Benutzer jedoch möglicherweise das Formular unabhängig davon schließen können, ob die Werte in den Steuerelementen gültig sind.  Die Validierung kann überschrieben und ein Formular mit ungültigen Daten geschlossen werden, wenn Sie einen Handler für das <xref:System.Windows.Forms.Form.Closing>\-Ereignis des Formulars erstellen.  Legen Sie für das Ereignis die <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>\-Eigenschaft auf `false` fest.  Dadurch wird das Formular in jedem Fall geschlossen.  Weitere Informationen und ein Beispiel finden Sie unter <xref:System.Windows.Forms.Form.Closing?displayProperty=fullName>.  
  
> [!NOTE]
>  Wenn das Schließen des Formulars auf diese Weise erzwungen wird, gehen alle nicht gespeicherten Daten in den Steuerelementen des Formulars verloren.  Außerdem wird in modalen Formularen der Inhalt der Steuerelemente beim Schließen nicht überprüft.  Sie können die Validierung von Steuerelementen trotzdem verwenden, um den Fokus auf ein Steuerelement zu fixieren, ohne dass Sie das Verhalten beim Schließen des Formulars beachten müssen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Control.Validating?displayProperty=fullName>   
 <xref:System.Windows.Forms.Form.Closing?displayProperty=fullName>   
 <xref:System.ComponentModel.CancelEventArgs?displayProperty=fullName>   
 [MaskedTextBox\-Steuerelement](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)   
 [Beispiele für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-examples.md)
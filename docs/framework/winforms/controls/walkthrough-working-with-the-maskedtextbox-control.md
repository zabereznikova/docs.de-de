---
title: 'Exemplarische Vorgehensweise: Arbeiten mit dem MaskedTextBox-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
ms.openlocfilehash: 7f25e21008c77ebf5e55e7affbb4cf07db377c5d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623278"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a>Exemplarische Vorgehensweise: Arbeiten mit dem MaskedTextBox-Steuerelement
In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
- Initialisieren der <xref:System.Windows.Forms.MaskedTextBox> Steuerelement  
  
- Mithilfe der <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> -Ereignishandler, um den Benutzer zu warnen, wenn es sich bei der Maske nicht entspricht einem Zeichen  
  
- Zuweisen eines Typs in der <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> -Eigenschaft und unter Verwendung der <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> -Ereignishandler, um den Benutzer zu warnen, wenn der Wert, der sie versuchen, einen commit für den Typ ungültig ist  
  
## <a name="creating-the-project-and-adding-a-control"></a>Erstellen des Projekts und Hinzufügen eines Steuerelements  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a>MaskedTextBox-Steuerelement zum Formular hinzufügen  
  
1. Öffnen Sie das Formular auf dem Sie platzieren möchten die <xref:System.Windows.Forms.MaskedTextBox> Steuerelement.  
  
2. Ziehen Sie eine <xref:System.Windows.Forms.MaskedTextBox> -Steuerelement aus der **Toolbox** zu Ihrem Formular.  
  
3. Klicken Sie auf das Steuerelement, und wählen Sie **Eigenschaften**. In der **Eigenschaften** wählen Sie im Fenster der **Maske** -Eigenschaft, und klicken Sie auf die **...**  (Auslassungspunkte) neben dem Eigenschaftennamen.  
  
4. In der **Eingabeformat** wählen Sie im Dialogfeld die **kurzes Datum** verborgen, und klicken Sie auf **OK**.  
  
5. In der **Eigenschaften** legen die <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> Eigenschaft `true`. Diese Eigenschaft bewirkt, dass einen kurze Signalton ausgegeben, jedes Mal, wenn der Benutzer versucht, ein Zeichen eingeben, die die Maskendefinition verletzt.  
  
 Eine Zusammenfassung der Zeichen, die die Mask-Eigenschaft unterstützt, finden Sie im Abschnitt "Hinweise" der <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Eigenschaft.  
  
## <a name="alert-the-user-to-input-errors"></a>Warnen Sie die Benutzer zur Eingabe von Fehlern  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a>Fügen Sie eine SprechblasenInfo für abgelehnte Maskeneingabe hinzu.  
  
1. Wechseln Sie zurück zur der **Toolbox** und Hinzufügen einer <xref:System.Windows.Forms.ToolTip> zu Ihrem Formular.  
  
2. Erstellen Sie einen Ereignishandler für die <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> -Ereignis, das löst die <xref:System.Windows.Forms.ToolTip> bei einem Eingabe Fehler. QuickInfo-Sprechblase bleibt sichtbar, fünf Sekunden lang oder bis der Benutzer darauf klickt.  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a>Der Benutzer auf einen Typ, der ungültig ist  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a>Fügen Sie eine SprechblasenInfo für ungültige-Datentypen  
  
1. Ihres Formulars <xref:System.Windows.Forms.Form.Load> -Ereignishandler weisen eine <xref:System.Type> Objekt darstellt der <xref:System.DateTime> Geben Sie auf die <xref:System.Windows.Forms.MaskedTextBox> des Steuerelements <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> Eigenschaft:  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2. Fügen Sie einen Ereignishandler für das <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>-Ereignis hinzu:  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.MaskedTextBox>
- [MaskedTextBox-Steuerelement](maskedtextbox-control-windows-forms.md)

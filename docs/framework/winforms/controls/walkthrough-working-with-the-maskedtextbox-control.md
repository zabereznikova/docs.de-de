---
title: 'Exemplarische Vorgehensweise: Arbeiten mit dem MaskedTextBox-Steuerelement'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 006dafe88c5db7cb1499d7c1902d295841bfb5ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a>Exemplarische Vorgehensweise: Arbeiten mit dem MaskedTextBox-Steuerelement
In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Initialisieren der <xref:System.Windows.Forms.MaskedTextBox> Steuerelement  
  
-   Mithilfe der <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> -Ereignishandler, um den Benutzer zu warnen, wenn ein Zeichen nicht der Maske entspricht  
  
-   Zuweisen eines Typs für die <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> -Eigenschaft und die Verwendung der <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> -Ereignishandler, um den Benutzer zu warnen, wenn sie versuchen, einen commit für Wert für den Typ ungültig ist  
  
## <a name="creating-the-project-and-adding-a-control"></a>Erstellen des Projekts und Hinzufügen eines Steuerelements  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a>MaskedTextBox-Steuerelement zum Formular hinzufügen  
  
1.  Öffnen Sie das Formular, das auf dem sollen die <xref:System.Windows.Forms.MaskedTextBox> Steuerelement.  
  
2.  Ziehen Sie eine <xref:System.Windows.Forms.MaskedTextBox> -Steuerelement aus der **Toolbox** in Ihr Formular.  
  
3.  Mit der rechten Maustaste in des Steuerelements, und wählen Sie **Eigenschaften**. In der **Eigenschaften** wählen die **Maske** -Eigenschaft, und klicken Sie auf der **...**  (Schaltfläche) neben dem Eigenschaftennamen.  
  
4.  In der **Eingabeformat** wählen Sie im Dialogfeld die **kurzes Datum** verborgen sind, und klicken Sie auf **OK**.  
  
5.  In der **Eigenschaften** Fenster Satz der <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> Eigenschaft `true`. Diese Eigenschaft bewirkt, dass einen kurze Signalton ausgegeben, jedes Mal, wenn der Benutzer versucht, ein Eingabezeichen, das die Maskendefinition verletzt.  
  
 Eine Zusammenfassung der Zeichen, die die Mask-Eigenschaft unterstützt, finden Sie im Abschnitt "Hinweise" der <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Eigenschaft.  
  
## <a name="alert-the-user-to-input-errors"></a>Benachrichtigt den Benutzer zur Eingabe von Fehlern  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a>Fügen Sie eine SprechblasenInfo für abgelehnte Maskeneingabe hinzu  
  
1.  Zurück zu den **Toolbox** und Hinzufügen einer <xref:System.Windows.Forms.ToolTip> in Ihr Formular.  
  
2.  Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> Ereignis, das löst die <xref:System.Windows.Forms.ToolTip> tritt ein Eingabefehler. Die SprechblasenInfo bleibt sichtbar, fünf Sekunden lang oder bis der Benutzer darauf klickt.  
  
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
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a>Warnen des Benutzers auf einen Typ, der ungültig ist  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a>Fügen Sie eine SprechblasenInfo für ungültige Datentypen  
  
1.  In Ihrem Formulars <xref:System.Windows.Forms.Form.Load> Ereignishandler, d. h. weisen eine <xref:System.Type> Objekt darstellt der <xref:System.DateTime> Geben Sie auf der <xref:System.Windows.Forms.MaskedTextBox> des Steuerelements <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> Eigenschaft:  
  
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
  
2.  Fügen Sie einen Ereignishandler für das <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>-Ereignis hinzu:  
  
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
 <xref:System.Windows.Forms.MaskedTextBox>  
 [MaskedTextBox-Steuerelement](../../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)

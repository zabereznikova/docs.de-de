---
title: 'Vorgehensweise: Hinzufügen bzw. Entfernen von Steuerelementen zu bzw. aus einer Auflistung von Steuerelementen zur Laufzeit'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- run time [Windows Forms], removing controls
- controls [Windows Forms], adding using collections
- controls collections
- collections [Windows Forms], adding items
- run time [Windows Forms], adding controls
- controls [Windows Forms], removing using collections
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
ms.openlocfilehash: 87ad4c957ac5b99438684d398a0c5ad7d126c406
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925047"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a>Vorgehensweise: Hinzufügen bzw. Entfernen von Steuerelementen zu bzw. aus einer Auflistung von Steuerelementen zur Laufzeit
Häufige Aufgaben bei der Anwendungsentwicklung sind das Hinzufügen von Steuerelementen zu und das Entfernen von Steuerelementen aus einem beliebigen <xref:System.Windows.Forms.Panel> Container <xref:System.Windows.Forms.GroupBox> Steuerelement in Ihren Formularen (z. b. das-Steuerelement oder das-Steuerelement) Zur Entwurfszeit können Steuerelemente direkt auf ein Panel oder Gruppenfeld gezogen werden. Zur Laufzeit verwalten diese Steuerelemente eine `Controls`-Auflistung, die protokolliert, welche Steuerelemente darauf platziert werden.  
  
> [!NOTE]
> Das folgende Codebeispiel gilt für jedes Steuerelement, das eine Auflistung von Steuerelementen verwaltet.  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a>So fügen Sie ein Steuerelement programmgesteuert zu einer Auflistung hinzu  
  
1. Erstellen Sie eine Instanz des Steuerelements, das hinzugefügt werden soll.  
  
2. Legen Sie die Eigenschaften des neuen Steuerelements fest.  
  
3. Fügen Sie der `Controls`-Auflistung des übergeordneten Elements das Steuerelement hinzu.  
  
     Im folgenden Codebeispiel wird gezeigt, wie eine Instanz des <xref:System.Windows.Forms.Button> -Steuer Elements erstellt wird. Hierfür ist ein Formular mit einem <xref:System.Windows.Forms.Panel> -Steuerelement erforderlich, und die Ereignis Behandlungsmethode für die Schalt `NewPanelButton_Click`Fläche, die erstellt wird, ist bereits vorhanden.  
  
    ```vb  
    Public NewPanelButton As New Button()  
  
    Public Sub AddNewControl()  
       ' The Add method will accept as a parameter any object that derives  
       ' from the Control class. In this case, it is a Button control.  
       Panel1.Controls.Add(NewPanelButton)  
       ' The event handler indicated for the Click event in the code   
       ' below is used as an example. Substite the appropriate event  
       ' handler for your application.  
       AddHandler NewPanelButton.Click, AddressOf NewPanelButton_Click  
    End Sub  
    ```  
  
    ```csharp  
    public Button newPanelButton = new Button();  
  
    public void addNewControl()  
    {   
       // The Add method will accept as a parameter any object that derives  
       // from the Control class. In this case, it is a Button control.  
       panel1.Controls.Add(newPanelButton);  
       // The event handler indicated for the Click event in the code   
       // below is used as an example. Substitute the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a>So entfernen Sie Steuerelemente programmgesteuert aus einer Auflistung  
  
1. Entfernen Sie den Ereignishandler aus dem Ereignis. Verwenden Sie in Visual Basic das [RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md) -Anweisungs Schlüsselwort. verwenden C#Sie in den [Operator-=](../../../csharp/language-reference/operators/subtraction-operator.md).  
  
2. Verwenden Sie die Methode `Remove`, um das gewünschte Steuerelement aus der `Controls`-Auflistung des Panels zu löschen.  
  
3. Ruft die <xref:System.Windows.Forms.Control.Dispose%2A> -Methode auf, um alle vom-Steuerelement verwendeten Ressourcen freizugeben.  
  
    ```vb  
    Public Sub RemoveControl()  
    ' NOTE: The code below uses the instance of   
    ' the button (NewPanelButton) from the previous example.  
       If Panel1.Controls.Contains(NewPanelButton) Then  
          RemoveHandler NewPanelButton.Click, AddressOf _   
             NewPanelButton_Click  
          Panel1.Controls.Remove(NewPanelButton)  
          NewPanelButton.Dispose()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void removeControl(object sender, System.EventArgs e)  
    {  
    // NOTE: The code below uses the instance of   
    // the button (newPanelButton) from the previous example.  
       if(panel1.Controls.Contains(newPanelButton))  
       {  
          this.newPanelButton.Click -= new System.EventHandler(this.   
             NewPanelButton_Click);  
          panel1.Controls.Remove(newPanelButton);  
          newPanelButton.Dispose();  
       }  
    }  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Panel>
- [Panel-Steuerelement](panel-control-windows-forms.md)

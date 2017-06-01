---
title: "Gewusst wie: Hinzuf&#252;gen bzw. Entfernen von Steuerelementen zu bzw. aus einer Auflistung von Steuerelementen zur Laufzeit | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Auflistungen, Hinzufügen von Elementen"
  - "Steuerelemente [Windows Forms], Hinzufügen mit Auflistungen"
  - "Steuerelemente [Windows Forms], Entfernen mit Auflistungen"
  - "controls-Auflistungen"
  - "Laufzeit, Hinzufügen von Steuerelementen"
  - "Laufzeit, Entfernen von Steuerelementen"
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Hinzuf&#252;gen bzw. Entfernen von Steuerelementen zu bzw. aus einer Auflistung von Steuerelementen zur Laufzeit
Häufige Aufgaben bei der Anwendungsentwicklung sind das Hinzufügen und Entfernen von Steuerelementen zu bzw. aus Containersteuerelementen in Formularen \(wie dem <xref:System.Windows.Forms.Panel>\-Steuerelement, dem <xref:System.Windows.Forms.GroupBox>\-Steuerelement oder sogar dem Formular selbst\).  Zur Entwurfszeit können Steuerelemente direkt auf einen Bereich oder in ein Gruppenfeld gezogen werden.  Zur Laufzeit verwalten diese Steuerelemente eine `Controls`\-Auflistung, in der protokolliert wird, welche anderen Steuerelemente auf ihnen abgelegt werden.  
  
> [!NOTE]
>  Das folgende Codebeispiel gilt für alle Steuerelemente, die eine Auflistung der in ihnen enthaltenen Steuerelemente verwalten.  
  
### So fügen Sie einer Auflistung ein Steuerelement programmgesteuert hinzu  
  
1.  Erstellen Sie eine Instanz des Steuerelements, das hinzugefügt werden soll.  
  
2.  Legen Sie die Eigenschaften des neuen Steuerelements fest.  
  
3.  Fügen Sie das Steuerelement der `Controls`\-Auflistung des übergeordneten Steuerelements hinzu.  
  
     Im folgenden Codebeispiel wird veranschaulicht, wie Sie eine Instanz des <xref:System.Windows.Forms.Button>\-Steuerelements erstellen.  Vorausgesetzt wird ein Formular mit einem <xref:System.Windows.Forms.Panel>\-Steuerelement und eine bereits vorhandene Ereignisbehandlungsmethode für die zu erstellende Schaltfläche `NewPanelButton_Click`.  
  
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
       // below is used as an example. Substite the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### So entfernen Sie Steuerelemente programmgesteuert aus einer Auflistung  
  
1.  Entfernen Sie den Ereignishandler aus dem Ereignis.  Verwenden Sie in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] das [RemoveHandler Statement](../../../../ocs/visual-basic/language-reference/statements/removehandler-statement.md)\-Schlüsselwort und in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] den [Operator \-\=](../Topic/-=%20Operator%20\(C%23%20Reference\)2.md).  
  
2.  Löschen Sie mit der `Remove`\-Methode das gewünschte Steuerelement aus der `Controls`\-Auflistung des Bereichs.  
  
3.  Rufen Sie die <xref:System.Windows.Forms.Control.Dispose%2A>\-Methode auf, um alle vom Steuerelement verwendeten Ressourcen freizugeben.  
  
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
  
## Siehe auch  
 <xref:System.Windows.Forms.Panel>   
 [Panel\-Steuerelement](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)
---
title: "Gewusst wie: Erstellen von Ereignishandlern f&#252;r Windows&#160;Forms zur Laufzeit | Microsoft Docs"
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
  - "Button-Steuerelement [Windows Forms], Ereignishandler"
  - "Ereignishandler, Erstellen"
  - "Beispiele [Windows Forms], Ereignisbehandlung"
  - "Laufzeit, Erstellen von Ereignishandlern"
  - "Windows Forms, Ereignisbehandlung"
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Erstellen von Ereignishandlern f&#252;r Windows&#160;Forms zur Laufzeit
Sie können Ereignisse mit dem Windows Forms\-Designer erstellen und haben zusätzlich die Möglichkeit, einen Ereignishandler zur Laufzeit zu erstellen.  Durch diese Aktion können Sie Ereignishandler auf der Grundlage codeinterner Bedingungen zur Laufzeit verbinden, anstatt sie beim ersten Programmstart verbinden zu lassen.  
  
### So erstellen Sie einen Ereignishandler zur Laufzeit  
  
1.  Öffnen Sie das Formular, dem ein Ereignishandler hinzugefügt werden soll, im Code\-Editor.  
  
2.  Fügen Sie dem Formular eine Methode mit der Methodensignatur für das Ereignis hinzu, das behandelt werden soll.  
  
     Wenn beispielsweise das <xref:System.Windows.Forms.Control.Click>\-Ereignis eines <xref:System.Windows.Forms.Button>\-Steuerelements verarbeitet wird, erstellen Sie eine mit folgendem Beispiel vergleichbare Methode:  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As EventArgs)  
       ' Add event handler code here.  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
    // Add event handler code here.  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          // Add event handler code here.  
       }  
    ```  
  
3.  Fügen Sie dem Ereignishandler den für Ihre Anwendung geeigneten Code hinzu.  
  
4.  Legen Sie fest, für welches Formular oder Steuerelement ein Ereignishandler erstellt werden soll.  
  
5.  Fügen Sie in einer Methode innerhalb der Formularklasse Code hinzu, der den Ereignishandler festlegt, mit dem das Ereignis verarbeitet werden soll.  Durch den folgenden Code wird beispielsweise festgelegt, dass der `button1_Click`\-Ereignishandler das <xref:System.Windows.Forms.Control.Click>\-Ereignis eines <xref:System.Windows.Forms.Button>\-Steuerelements verarbeitet:  
  
    ```vb  
    AddHandler Button1.Click, AddressOf Button1_Click  
  
    ```  
  
    ```csharp  
    button1.Click += new EventHandler(button1_Click);  
  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     Durch die im obigen Visual Basic\-Code gezeigte <xref:System.ComponentModel.EventHandlerList.AddHandler%2A>\-Methode wird ein Click\-Ereignishandler für die Schaltfläche erzeugt.  
  
## Siehe auch  
 [Erstellen von Ereignishandlern in Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)   
 [Übersicht über Ereignishandler](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)   
 [Troubleshooting Inherited Event Handlers in Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md)
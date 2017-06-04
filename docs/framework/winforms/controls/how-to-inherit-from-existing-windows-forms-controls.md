---
title: "Gewusst wie: Erben von vorhandenen Windows Forms-Steuerelementen | Microsoft Docs"
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
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Vererbung"
  - "Vererbung, Benutzerdefinierte Windows Forms-Steuerelemente"
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Gewusst wie: Erben von vorhandenen Windows Forms-Steuerelementen
Wenn die Funktionalität eines vorhandenen Steuerelements erweitert werden soll, kann ein Steuerelement erstellt werden, das durch Vererbung von einem vorhandenen Steuerelement abgeleitet ist.  Mit einem vorhandenen Steuerelement werden die gesamte Funktionalität und die visuellen Eigenschaften dieses Steuerelements geerbt.  Wenn beispielsweise ein Steuerelement erstellt wird, das von <xref:System.Windows.Forms.Button> geerbt wird, wird das neue Steuerelement ebenso dargestellt wie ein standardmäßiges <xref:System.Windows.Forms.Button>\-Steuerelement und wird sich ebenso verhalten.  Anschließend kann die Funktionalität des neuen Steuerelements durch Implementierung benutzerdefinierter Methoden und Eigenschaften erweitert oder geändert werden.  Bei einigen Steuerelementen kann auch die visuelle Darstellung des geerbten Steuerelements geändert werden, indem die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode überschrieben wird.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So erstellen Sie ein geerbtes Steuerelement  
  
1.  Erstellen eines neuen **Windows Forms\-Anwendung**\-Projekts.  
  
2.  Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.  
  
     Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
3.  Doppelklicken Sie im Dialogfeld **Neues Element hinzufügen** auf **Benutzerdefiniertes Steuerelement**.  
  
     Ein neues benutzerdefiniertes Steuerelement wird dem Projekt hinzugefügt.  
  
4.  Klicken Sie in Visual Basic oben im **Projektmappen\-Explorer** auf **Alle Dateien anzeigen**.  Erweitern Sie CustomControl1.vb, und öffnen Sie dann CustomControl1.Designer.vb im Code\-Editor.  
  
5.  Wenn Sie C\# verwenden, öffnen Sie CustomControl1.cs im Code\-Editor.  
  
6.  Suchen Sie die Klassendeklaration, die von <xref:System.Windows.Forms.Control> erbt.  
  
7.  Ändern Sie die Basisklasse in das Steuerelement, von dem geerbt werden soll.  
  
     Angenommen, Sie möchten von <xref:System.Windows.Forms.Button> erben. In diesem Fall ändern Sie die Klassendeklaration wie folgt:  
  
    ```vb  
    Partial Class CustomControl1  
        Inherits System.Windows.Forms.Button  
    ```  
  
    ```csharp  
    public partial class CustomControl1 : System.Windows.Forms.Button  
    ```  
  
8.  Wenn Sie Visual Basic verwenden, speichern und schließen Sie CustomControl1.Designer.vb.  Öffnen Sie CustomControl1.vb im Code\-Editor.  
  
9. Implementieren Sie alle benutzerdefinierten Methoden oder Eigenschaften, die in das Steuerelement eingebunden werden.  
  
10. Wenn Sie die grafische Darstellung des Steuerelements ändern möchten, überschreiben Sie die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode.  
  
    > [!NOTE]
    >  Durch Überschreiben von <xref:System.Windows.Forms.Control.OnPaint%2A> ist es nicht möglich, die Darstellung aller Steuerelemente zu ändern.  Von den Steuerelementen, die vollständig von Windows gezeichnet werden, z. B. <xref:System.Windows.Forms.TextBox>, wird die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode nie aufgerufen. Daher wird benutzerdefinierter Code von diesen nie verwendet.  Ob die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode verfügbar ist, entnehmen Sie der Hilfedokumentation zu dem Steuerelement, das Sie ändern möchten.  Eine Liste aller Windows Form\-Steuerelemente finden Sie unter [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).  Die Darstellung eines Steuerelements, in dem <xref:System.Windows.Forms.Control.OnPaint%2A> nicht als Membermethode aufgeführt wird, können Sie nicht durch Überschreiben dieser Methode ändern.  Weitere Informationen über benutzerdefiniertes Zeichnen finden Sie unter [Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).  
  
    ```vb  
    Protected Overrides Sub OnPaint(ByVal e As _  
       System.Windows.Forms.PaintEventArgs)  
       MyBase.OnPaint(e)  
       ' Insert code to do custom painting.   
       ' If you want to completely change the appearance of your control,  
       ' do not call MyBase.OnPaint(e).  
    End Sub  
  
    ```  
  
    ```csharp  
    protected override void OnPaint(PaintEventArgs pe)  
    {  
       base.OnPaint(pe);  
       // Insert code to do custom painting.  
       // If you want to completely change the appearance of your control,  
       // do not call base.OnPaint(pe).  
    }  
    ```  
  
11. Speichern und testen Sie das Steuerelement.  
  
## Siehe auch  
 [Arten von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)   
 [Gewusst wie: Erben von der Control\-Klasse](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)   
 [Gewusst wie: Erben von der UserControl\-Klasse](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)   
 [Gewusst wie: Erstellen von Steuerelementen für Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)   
 [Troubleshooting Inherited Event Handlers in Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md)   
 [Exemplarische Vorgehensweise: Vererben eines Windows Forms\-Steuerelements mit Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)   
 [Exemplarische Vorgehensweise: Vererben von einem Windows Forms\-Steuerelement mit Visual C\#](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
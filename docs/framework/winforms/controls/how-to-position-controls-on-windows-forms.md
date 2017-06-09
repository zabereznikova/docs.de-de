---
title: "Gewusst wie: Positionieren von Steuerelementen in Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Location"
  - "Location.Y"
  - "Location.X"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Steuerelemente [Windows Forms]"
  - "Steuerelemente [Windows Forms], Verschieben"
  - "Steuerelemente [Windows Forms], Positionieren"
  - "Ausrichtungslinien"
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Gewusst wie: Positionieren von Steuerelementen in Windows&#160;Forms
Verwenden Sie zum Positionieren von Steuerelementen den Windows Forms\-Designer, oder legen Sie die <xref:System.Windows.Forms.Control.Location%2A>\-Eigenschaft fest.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So positionieren Sie ein Steuerelement auf der Entwurfsoberfläche des Windows Forms\-Designers  
  
-   Ziehen Sie das Steuerelement mit der Maus an die geeignete Position.  
  
    > [!NOTE]
    >  Wählen Sie das Steuerelement aus, und verschieben Sie es mithilfe der Pfeiltasten, um es exakter zu positionieren.  Darüber hinaus lassen sich Steuerelemente mithilfe von *Ausrichtungslinien* genauer auf dem Formular positionieren.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
### So positionieren Sie ein Steuerelement über das Eigenschaftenfenster  
  
1.  Klicken Sie auf das zu positionierende Steuerelement.  
  
2.  Geben Sie im **Eigenschaftenfenster** durch Kommas getrennte Werte für die <xref:System.Windows.Forms.Control.Location%2A>\-Eigenschaft ein, um das Steuerelement innerhalb seines Containers zu positionieren.  
  
     Der erste Wert \(X\) entspricht dem Abstand vom linken Containerrand und der zweite Wert \(Y\) dem Abstand vom oberen Rand des Containerbereichs in Pixel.  
  
    > [!NOTE]
    >  Erweitern Sie die <xref:System.Windows.Forms.Control.Location%2A>\-Eigenschaft, um die **X**\- und **Y**\-Werte einzeln einzugeben.  
  
### So positionieren Sie ein Steuerelement programmgesteuert  
  
1.  Legen Sie für die <xref:System.Windows.Forms.Control.Location%2A>\-Eigenschaft des Steuerelements <xref:System.Drawing.Point> fest.  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2.  Ändern Sie die X\-Koordinate der Steuerelementposition mithilfe der untergeordneten <xref:System.Windows.Forms.Control.Left%2A>\-Eigenschaft.  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### So inkrementieren Sie die Position eines Steuerelements programmgesteuert  
  
1.  Legen Sie die untergeordnete <xref:System.Windows.Forms.Control.Left%2A>\-Eigenschaft fest, um die X\-Koordinate des Steuerelements zu inkrementieren.  
  
    ```vb  
    Button1.Left += 200  
    ```  
  
    ```csharp  
    button1.Left += 200;  
    ```  
  
    ```cpp  
    button1->Left += 200;  
    ```  
  
    > [!NOTE]
    >  Verwenden Sie die <xref:System.Windows.Forms.Control.Location%2A>\-Eigenschaft, um die X\- und Y\-Position eines Steuerelements gleichzeitig festzulegen.  Um eine Position individuell festzulegen, verwenden Sie die untergeordnete <xref:System.Windows.Forms.Control.Left%2A>\-Eigenschaft \(**X**\) oder die untergeordnete <xref:System.Windows.Forms.Control.Top%2A>\-Eigenschaft \(**Y**\) des Steuerelements.  Die X\- und Y\-Koordinaten der <xref:System.Drawing.Point>\-Struktur, die die Position der Schaltfläche darstellt, sollten keinesfalls implizit definiert werden, da diese Struktur eine Kopie der Koordinaten der Schaltfläche enthält.  
  
## Siehe auch  
 [Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)   
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)   
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Windows Forms\-Steuerelemente nach Funktion](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)   
 [How to: Set the Screen Location of Windows Forms](http://msdn.microsoft.com/de-de/cb023ab7-dea7-4284-9aa6-8c03c59b60c6)
---
title: "Gewusst wie: Festlegen von QuickInfos f&#252;r Steuerelemente auf einem Windows Form zur Entwurfszeit | Microsoft Docs"
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
  - "Beispiele [Windows Forms], QuickInfo"
  - "QuickInfo [Windows Forms], Für Steuerelemente"
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Gewusst wie: Festlegen von QuickInfos f&#252;r Steuerelemente auf einem Windows Form zur Entwurfszeit
Sie können eine <xref:System.Windows.Forms.ToolTip>\-Zeichenfolge in Code oder im Windows Forms\-Designer festlegen.  Weitere Informationen über die <xref:System.Windows.Forms.ToolTip>\-Komponente finden Sie unter [Übersicht über die ToolTip\-Komponente](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So legen Sie eine QuickInfo programmgesteuert fest  
  
1.  Fügen Sie das Steuerelement hinzu, das die QuickInfo anzeigt.  
  
2.  Verwenden Sie die <xref:System.Windows.Forms.ToolTip.SetToolTip%2A>\-Methode der <xref:System.Windows.Forms.ToolTip>\-Komponente.  
  
    ```vb  
    ' In this example, Button1 is the control to display the ToolTip.  
    ToolTip1.SetToolTip(Button1, "Save changes")  
  
    ```  
  
    ```csharp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1.SetToolTip(button1, "Save changes");  
  
    ```  
  
    ```cpp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1->SetToolTip(button1, "Save changes");  
    ```  
  
### So legen Sie eine QuickInfo im Designer fest  
  
1.  Fügen Sie dem Formular eine <xref:System.Windows.Forms.ToolTip>\-Komponente hinzu.  
  
2.  Wählen Sie das Steuerelement aus, das die QuickInfo anzeigt, oder fügen Sie es zum Formular hinzu.  
  
3.  Legen Sie im **Eigenschaftenfenster** den Wert **ToolTip on ToolTip1** auf eine geeignete Textzeichenfolge fest.  
  
## Siehe auch  
 [Übersicht über die ToolTip\-Komponente](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)   
 [Gewusst wie: Ändern der Verzögerung der ToolTip\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)   
 [ToolTip\-Komponente](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
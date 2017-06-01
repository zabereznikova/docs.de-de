---
title: "Gewusst wie: Kopieren und Einf&#252;gen eines ElementHost-Steuerelements zur Entwurfszeit | Microsoft Docs"
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
  - "ElementHost-Steuerelement, Kopieren und Einfügen zur Entwurfszeit"
  - "Interoperabilität [WPF]"
  - "Windows Forms, Kopieren und Einfügen von Inhalt"
  - "WPF-Benutzersteuerelement, Hosten in Windows Forms"
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Kopieren und Einf&#252;gen eines ElementHost-Steuerelements zur Entwurfszeit
Diese Verfahrensweise zeigt, wie Sie ein Windows Presentation Foundation \(WPF\)\-Steuerelement auf ein Windows Form kopieren.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So kopieren Sie ein ElementHost\-Steuerelement und fügen es zur Entwurfszeit ein  
  
1.  Fügen Sie dem Windows Forms\-Projekt ein neues WPF\-<xref:System.Windows.Controls.UserControl> hinzu.  Verwenden Sie den Standardnamen `UserControl1.xaml` für den Steuerelementtyp.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen neuen WPF\-Inhalts in Windows Forms zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  Legen Sie im **Eigenschaftenfenster** den Wert der <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft und der <xref:System.Windows.FrameworkElement.Height%2A>\-Eigenschaft von `UserControl1` auf `200` fest.  
  
3.  Legen Sie den Wert der <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaft auf `Blue` fest.  
  
4.  Erstellen Sie das Projekt.  
  
5.  Öffnen Sie `Form1` im Windows Forms\-Designer.  
  
6.  Ziehen Sie eine Instanz von `UserControl1` aus der **Toolbox** auf das Formular.  
  
     Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement mit dem Namen `elementHost1` gehostet.  
  
7.  Während `elementHost1` ausgewählt ist, drücken Sie STRG\+C, um das Steuerelement in die Zwischenablage zu kopieren.  
  
8.  Drücken Sie STRG\+V, um das kopierte Steuerelement auf dem Formular einzufügen.  
  
     Ein neues <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement mit dem Namen `elementHost2` wird auf dem Formular erstellt.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Exemplarische Vorgehensweise: Kopieren und Einfügen eines ElementHost\-Steuerelements in separate Windows Forms](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)   
 [Migration und Interoperabilität](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [Verwenden von WPF\-Steuerelementen](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26)
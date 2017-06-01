---
title: "Exemplarische Vorgehensweise: &#196;ndern von Eigenschaften eines gehosteten WPF-Elements zur Entwurfszeit | Microsoft Docs"
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
  - "Interoperabilität [WPF]"
  - "Windows Forms, Ändern der Eigenschaften von WPF-Inhalt zur Entwurfszeit"
  - "WPF-Inhalt [Windows Forms], Ändern der Eigenschaften zur Entwurfszeit"
  - "WPF-Inhalt, Hosten in Windows Forms"
ms.assetid: a1f7a90c-0bbb-4781-8c3c-8cc8bef2488d
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Exemplarische Vorgehensweise: &#196;ndern von Eigenschaften eines gehosteten WPF-Elements zur Entwurfszeit
In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Eigenschaftswerte eines WPF\-Steuerelements \(Windows Presentation Foundation\) geändert werden, das in einem Windows Form\-Objekt gehostet wird.  
  
 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:  
  
-   Erstellen eines Projekts  
  
-   Erstellen des WPF\-Steuerelements  
  
-   Hosten der WPF\-Steuerelemente in einem Windows Form\-Objekt  
  
-   Verwenden des WPF\-Designers für Visual Studio, um Eigenschaftswerte zu ändern  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren**, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## Erstellen des Projekts  
 Zunächst muss das Windows Forms\-Projekt erstellt werden.  
  
> [!NOTE]
>  Beim Hosten von WPF\-Inhalt werden nur C\#\- und Visual Basic\-Projekte unterstützt.  
  
#### So erstellen Sie das Projekt  
  
-   Erstellen Sie in Visual Basic oder Visual C\# ein neues Windows Forms\-Anwendungsprojekt mit dem Namen `WpfHost`.  
  
## Erstellen des WPF\-Steuerelements  
 Nachdem Sie dem Projekt ein WPF\-Steuerelement hinzugefügt haben, können Sie dieses auf dem Formular anordnen.  
  
#### So erstellen Sie ein WPF\-Steuerelement  
  
1.  Fügen Sie dem Projekt ein neues WPF\-<xref:System.Windows.Controls.UserControl>\-Objekt hinzu.  Verwenden Sie den Standardnamen, `UserControl1.xaml`, für den Steuerelementtyp.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen neuen WPF\-Inhalts in Windows Forms zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  Legen Sie im **Eigenschaftenfenster** den Wert der <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaft auf `Blue` fest.  
  
3.  Erstellen Sie das Projekt.  
  
## Ändern von Eigenschaftswerten für das WPF\-Steuerelement  
 Mit dem <xref:System.Windows.Forms.Integration.ElementHost>\-Smarttag lassen sich Eigenschaften von gehostetem WPF\-Inhalt einfach ändern, indem der WPF\-Designer verwendet wird.  
  
#### So hosten Sie ein WPF\-Steuerelement  
  
1.  Öffnen Sie `Form1` im Windows Forms\-Designer.  
  
2.  Doppelklicken Sie in der **Toolbox** auf der Registerkarte **WPF\-Benutzersteuerelemente** auf `UserControl1`, damit auf dem Formular eine Instanz von `UserControl1` erstellt wird.  
  
     Die Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement namens `elementHost1` gehostet.  
  
3.  Wählen Sie im Smarttagbereich **ElementHost\-Aufgaben** die Option **Gehosteten Inhalt bearbeiten** aus.  
  
     Die Datei "UserControl1.xaml" wird im WPF\-Designer geöffnet.  
  
4.  Legen Sie im **Eigenschaftenfenster** den Wert der <xref:System.Windows.Controls.Control.Background%2A>\-Eigenschaft auf `Red` fest.  
  
5.  Erstellen Sie das Projekt neu.  
  
6.  Öffnen Sie `Form1` im Windows Forms\-Designer.  
  
     Die Instanz von `UserControl1` hat einen roten Hintergrund.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)   
 [Gewusst wie: Ausrichten eines Steuerelements an den Rändern eines Formulars zur Entwurfszeit](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)   
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)   
 [Migration und Interoperabilität](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [Verwenden von WPF\-Steuerelementen](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26)
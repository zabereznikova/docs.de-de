---
title: "Exemplarische Vorgehensweise: Zuweisen von WPF-Inhalt in Windows Forms zur Entwurfszeit | Microsoft Docs"
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
  - "ElementHost-Steuerelement, Zuweisen von WPF-Inhalt zur Entwurfszeit"
  - "Interoperabilität [WPF]"
  - "Windows Forms, Inhaltszuweisungen"
  - "WPF-Inhalt [Windows Forms], Zuweisen zur Entwurfszeit"
  - "WPF-Benutzersteuerelement, Hosten in Windows Forms"
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Exemplarische Vorgehensweise: Zuweisen von WPF-Inhalt in Windows Forms zur Entwurfszeit
In dieser exemplarischen Vorgehensweise wird gezeigt, wie die WPF\-Steuerelementtypen \(Windows Presentation Foundation\) ausgewählt werden, die im Formular angezeigt werden sollen.  Sie können alle WPF\-Steuerelementtypen auswählen, die im Projekt enthalten sind.  
  
 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:  
  
-   Erstellen des Projekts.  
  
-   Erstellen der WPF\-Steuerelementtypen.  
  
-   Auswählen der WPF\-Steuerelemente.  
  
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
  
-   Erstellen Sie in Visual Basic oder Visual C\# ein neues Windows Forms\-Anwendungsprojekt mit dem Namen `SelectingWpfContent`.  
  
## Erstellen der WPF\-Steuerelementtypen  
 Nachdem Sie dem Projekt WPF\-Steuerelementtypen hinzugefügt haben, können Sie diese in verschiedenen <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelementen hosten.  
  
#### So erstellen Sie WPF\-Steuerelementtypen  
  
1.  Fügen Sie der Projektmappe ein neues WPF\-<xref:System.Windows.Controls.UserControl>\-Projekt hinzu.  Verwenden Sie den Standardnamen \(`UserControl1.xaml`\) für den Steuerelementtyp.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen neuen WPF\-Inhalts in Windows Forms zur Entwurfszeit](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.  Weitere Informationen finden Sie unter [Gewusst wie: Auswählen und Verschieben von Elementen auf der Entwurfsoberfläche](http://msdn.microsoft.com/de-de/54cb70b6-b35b-46e4-a0cc-65189399c474).  
  
3.  Legen Sie im Fenster **Eigenschaften** den Wert der Eigenschaften <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> auf `200` fest.  
  
4.  Fügen Sie <xref:System.Windows.Controls.UserControl> ein <xref:System.Windows.Controls.TextBox?displayProperty=fullName>\-Steuerelement hinzu, und legen Sie den Wert der Eigenschaft <xref:System.Windows.Controls.TextBox.Text%2A> auf "Hosted Content" fest.  
  
5.  Fügen Sie dem Projekt ein zweites WPF\-<xref:System.Windows.Controls.UserControl> hinzu.  Verwenden Sie den Standardnamen \(`UserControl2.xaml`\) für den Steuerelementtyp.  
  
6.  Legen Sie im Fenster **Eigenschaften** den Wert der Eigenschaften <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> auf `200` fest.  
  
7.  Fügen Sie <xref:System.Windows.Controls.UserControl> ein <xref:System.Windows.Controls.TextBox?displayProperty=fullName>\-Steuerelement hinzu, und legen Sie den Wert der Eigenschaft <xref:System.Windows.Controls.TextBox.Text%2A> auf "Hosted Content 2" fest.  
  
 **Hinweis** Normalerweise sollten Sie anspruchsvolleren WPF\-Inhalt hosten.  Das <xref:System.Windows.Controls.TextBox?displayProperty=fullName>\-Steuerelement wird hier nur zur Veranschaulichung verwendet.  
  
1.  Erstellen Sie das Projekt.  
  
## Auswählen von WPF\-Steuerelementen  
 Sie können einem <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement, das bereits Inhalte hostet, verschiedene WPF\-Inhalte zuweisen.  
  
#### So wählen Sie WPF\-Steuerelemente aus  
  
1.  Öffnen Sie `Form1` im Windows Forms\-Designer.  
  
2.  Doppelklicken Sie in der **Toolbox**, auf `UserControl1`, um eine Instanz von `UserControl1` im Formular zu erstellen.  
  
     Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>Steuerelement namens `elementHost1` gehostet.  
  
3.  Öffnen Sie im Smarttagbereich für `elementHost1` die Dropdownliste **Gehosteten Inhalt auswählen**.  
  
4.  Wählen Sie **UserControl2** aus dem Dropdown\-Listenfeld aus.  
  
     Das `elementHost1`\-Steuerelement hostet jetzt eine Instanz des `UserControl2`\-Typs.  
  
5.  Vergewissern Sie sich im **Eigenschaftenfenster￼**, dass die <xref:System.Windows.Forms.Integration.ElementHost.Child%2A>\-Eigenschaft auf **UserControl2** festgelegt ist.  
  
6.  Ziehen Sie aus der **Toolbox** in der Gruppe **WPF\-Interoperabilität** ein <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement auf das Formular.  
  
     Der Standardname für das neue Steuerelement ist `elementHost2`.  
  
7.  Öffnen Sie im Smarttagbereich für `elementHost2` die Dropdownliste **Gehosteten Inhalt auswählen**.  
  
8.  Wählen Sie **UserControl1** aus der Dropdownliste aus.  
  
9. Das `elementHost2`\-Steuerelement hostet jetzt eine Instanz des `UserControl1`\-Typs.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Migration und Interoperabilität](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [Verwenden von WPF\-Steuerelementen](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26)
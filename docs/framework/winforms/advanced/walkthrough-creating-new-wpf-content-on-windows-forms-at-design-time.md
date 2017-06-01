---
title: "Exemplarische Vorgehensweise: Erstellen neuen WPF-Inhalts in Windows Forms zur Entwurfszeit | Microsoft Docs"
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
  - "ElementHost-Steuerelement"
  - "Hosten von WPF-Inhalt in Windows Forms"
  - "Interoperabilität, WPF und Windows Forms"
  - "WPF-Inhalt, Hosten in Windows Forms"
  - "WPF-Benutzersteuerelement, Hosten in Windows Forms"
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Exemplarische Vorgehensweise: Erstellen neuen WPF-Inhalts in Windows Forms zur Entwurfszeit
In diesem Thema wird veranschaulicht, wie Sie ein Windows Presentation Foundation\-Steuerelement \(WPF\) zur Verwendung in Windows Forms\-basierten Anwendungen erstellen.  
  
 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie folgende Aufgaben aus:  
  
-   Erstellen eines Projekts  
  
-   Erstellen eines neuen WPF\-Steuerelements  
  
-   Hinzufügen des neuen WPF\-Steuerelements zu einem Windows Form.  Das WPF\-Steuerelement wird in einem <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement gehostet.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren**, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## Erstellen des Projekts  
 Zunächst muss das Windows Forms\-Projekt erstellt werden.  
  
> [!NOTE]
>  Beim Hosten von WPF\-Inhalt werden nur C\#\- und Visual Basic\-Projekte unterstützt.  
  
#### So erstellen Sie das Projekt  
  
-   Erstellen Sie in Visual Basic oder Visual C\# ein neues Windows Forms\-Anwendungsprojekt mit dem Namen `HostingWpf`.  
  
## Erstellen eines neuen WPF\-Steuerelements  
 Das Erstellen eines neuen WPF\-Steuerelements und das Hinzufügen des Steuerelements zum Projekt ist genauso einfach wie das Hinzufügen eines beliebigen anderen Elements zum Projekt.  Der Windows Forms\-Designer wird zusammen mit einem bestimmten Steuerelementtyp mit dem Namen *zusammengesetztes Steuerelement* oder *Benutzersteuerelement* verwendet.  Weitere Informationen zu benutzerdefinierten WPF\-Steuerelementen finden Sie unter <xref:System.Windows.Controls.UserControl>.  
  
> [!NOTE]
>  Der <xref:System.Windows.Controls.UserControl?displayProperty=fullName>\-Typ für WPF unterscheidet sich vom Windows Forms\-Benutzersteuerelementtyp, der ebenfalls den Namen <xref:System.Windows.Forms.UserControl?displayProperty=fullName> hat.  
  
#### So erstellen Sie ein neues WPF\-Steuerelement  
  
1.  Fügen Sie im **Projektmappen\-Explorer** ein neues Projekt **WPF\-Benutzersteuerelementbibliothek** zur Projektmappe hinzu.  Verwenden Sie den Standardnamen `WpfControlLibrary1` für die Steuerelementbibliothek.  Der Standardname für das Steuerelement lautet `UserControl1.xaml`.  
  
     Das Hinzufügen des neuen Steuerelements hat folgende Auswirkungen:  
  
    -   Die Datei UserControl1.xaml wird hinzugefügt.  
  
    -   Hinzugefügt wird entweder die Datei UserControl1.xaml.cs oder die Datei UserControl1.xaml.vb.  Diese Datei enthält das Code\-Behind\-Modell für Ereignishandler und andere Implementierungen.  
  
    -   Es werden Verweise auf die WPF\-Assemblys hinzugefügt.  
  
    -   Die Datei UserControl1.xaml wird in [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] geöffnet.  
  
2.  Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist.  Weitere Informationen finden Sie unter [Gewusst wie: Auswählen und Verschieben von Elementen auf der Entwurfsoberfläche](http://msdn.microsoft.com/de-de/54cb70b6-b35b-46e4-a0cc-65189399c474).  
  
3.  Legen Sie im Fenster **Eigenschaften** den Wert der <xref:System.Windows.FrameworkElement.Width%2A>\- und der <xref:System.Windows.FrameworkElement.Height%2A>\-Eigenschaft auf `200` fest.  
  
4.  Ziehen Sie ein <xref:System.Windows.Controls.TextBox?displayProperty=fullName>\-Steuerelement aus der **Toolbox** auf die Entwurfsoberfläche.  
  
5.  Legen Sie im Fenster **Eigenschaften** den Wert der <xref:System.Windows.Controls.TextBox.Text%2A>\-Eigenschaft auf "Hosted Content" fest.  
  
    > [!NOTE]
    >  Normalerweise sollten Sie anspruchsvolleren WPF\-Inhalt hosten.  <xref:System.Windows.Controls.TextBox?displayProperty=fullName>\-Steuerelement wird hier nur zur Veranschaulichung verwendet.  
  
6.  Erstellen Sie das Projekt.  
  
## Hinzufügen eines neuen WPF\-Steuerelements zu einem Windows Form  
 Das neue WPF\-Steuerelement kann jetzt im Formular verwendet werden.  Windows Forms verwendet das <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement zum Hosten des WPF\-Inhalts.  
  
#### So fügen Sie einem Windows Form ein WPF\-Steuerelement hinzu  
  
1.  Öffnen Sie `Form1` im Windows Forms\-Designer.  
  
2.  Suchen Sie in der **Toolbox** die Registerkarte mit der Bezeichnung **WPFUserControlLibrary WPF\-Benutzersteuerelemente**.  
  
3.  Ziehen Sie eine Instanz von `UserControl1` auf das Formular.  
  
    -   Ein <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement wird automatisch zum Hosten des WPF\-Steuerelements auf dem Formular erstellt.  
  
    -   Das <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement hat den Namen `elementHost1`, und im Fenster **Eigenschaften** wird die <xref:System.Windows.Forms.Integration.ElementHost.Child%2A>\-Eigenschaft auf **UserControl1** festgelegt.  
  
    -   Verweise auf WPF\-Assemblys werden dem Projekt hinzugefügt.  
  
    -   Das `elementHost1`\-Steuerelement verfügt über einen Smarttagbereich, in dem die verfügbaren Hostingoptionen anzeigt werden.  
  
4.  Wählen Sie im Smarttagbereich **ElementHost\-Aufgaben** die Option **In übergeordnetem Container andocken** aus.  
  
5.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
## Nächste Schritte  
 Windows Forms und WPF sind unterschiedliche Technologien, wurden aber für eine enge Zusammenarbeit entwickelt.  Um die Darstellung und das Verhalten in Ihren Anwendungen zu optimieren, versuchen Sie Folgendes:  
  
-   Hosten eines Windows Forms\-Steuerelements in einer WPF\-Seite.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Hosten eines Windows Forms\-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).  
  
-   Übernehmen von visuellen Windows Forms\-Stilen für den WPF\-Inhalt.  Weitere Informationen finden Sie unter [Gewusst wie: Aktivieren von visuellen Stilen in einer Hybridanwendung](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).  
  
-   Ändern des Stils des WPF\-Inhalts.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Formatieren von WPF\-Inhalt](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Migration und Interoperabilität](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [Verwenden von WPF\-Steuerelementen](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26)
---
title: 'Exemplarische Vorgehensweise: Erstellen neuen WPF-Inhalts in Windows Forms zur Entwurfszeit'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cfbe9957fa8d18f839ae656ca721c4ee88475a5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time"></a>Exemplarische Vorgehensweise: Erstellen neuen WPF-Inhalts in Windows Forms zur Entwurfszeit
In diesem Thema wird veranschaulicht, wie Sie ein Windows Presentation Foundation-Steuerelement (WPF) zur Verwendung in Windows Forms-basierten Anwendungen erstellen.  
  
 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie folgende Aufgaben aus:  
  
-   Erstellen eines Projekts  
  
-   Erstellen eines neuen WPF-Steuerelements  
  
-   Hinzufügen des neuen WPF-Steuerelements zu einem Windows Form. Das WPF-Steuerelement wird in einem <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement gehostet.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Zunächst muss das Windows Forms-Projekt erstellt werden.  
  
> [!NOTE]
>  Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
-   Erstellen Sie ein neues Windows Forms-Anwendungsprojekt in Visual Basic oder Visual c# mit dem Namen `HostingWpf`.  
  
## <a name="creating-a-new-wpf-control"></a>Erstellen eines neuen WPF-Steuerelements   
 Das Erstellen eines neuen WPF-Steuerelements und das Hinzufügen des Steuerelements zum Projekt ist genauso einfach wie das Hinzufügen eines beliebigen anderen Elements zum Projekt. Windows Forms-Designer funktioniert mit einer bestimmten Art von Steuerelement namens *zusammengesetztes Steuerelement*, oder *Benutzersteuerelement*. Weitere Informationen zu benutzerdefinierten WPF-Steuerelementen finden Sie unter <xref:System.Windows.Controls.UserControl>.  
  
> [!NOTE]
>  Der <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>-Typ für WPF unterscheidet sich vom Windows Forms-Benutzersteuerelementtyp, der ebenfalls den Namen <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType> hat.
  
  
#### <a name="to-create-a-new-wpf-control"></a>So erstellen Sie ein neues WPF-Steuerelement  
  
1.  In **Projektmappen-Explorer**, fügen Sie einen neuen **WPF-Benutzersteuerelementbibliothek** Projekt der Projektmappe. Verwenden Sie den Standardnamen `WpfControlLibrary1` für die Steuerelementbibliothek. Der Standardname für das Steuerelement lautet `UserControl1.xaml`.  
  
     Das Hinzufügen des neuen Steuerelements hat folgende Auswirkungen:  
  
    -   Die Datei UserControl1.xaml wird hinzugefügt.  
  
    -   Hinzugefügt wird entweder die Datei UserControl1.xaml.cs oder die Datei UserControl1.xaml.vb. Diese Datei enthält das Code-Behind-Modell für Ereignishandler und andere Implementierungen.  
  
    -   Es werden Verweise auf die WPF-Assemblys hinzugefügt.  
  
    -   Die Datei UserControl1.xaml wird in [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] geöffnet.  
  
2.  Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist. Weitere Informationen finden Sie unter [Vorgehensweise: auswählen und Verschieben von Elementen auf der Entwurfsoberfläche](http://msdn.microsoft.com/en-us/54cb70b6-b35b-46e4-a0cc-65189399c474).  
  
3.  In der **Eigenschaften** Fenster, legen Sie den Wert von der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften `200`.  
  
4.  Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> -Steuerelement auf der Entwurfsoberfläche angezeigt.  
  
5.  In der **Eigenschaften** Fenster, legen Sie den Wert von der <xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft **gehosteten Inhalt**.  
  
    > [!NOTE]
    >  Normalerweise sollten Sie anspruchsvolleren WPF-Inhalt hosten. <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>-Steuerelement wird hier nur zur Veranschaulichung verwendet.   
  
6.  Erstellen Sie das Projekt.  
  
## <a name="adding-a-wpf-control-to-a-windows-form"></a>Hinzufügen eines neuen WPF-Steuerelements zu einem Windows Form  
 Das neue WPF-Steuerelement kann jetzt im Formular verwendet werden. Windows Forms verwendet das <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement zum Hosten des WPF-Inhalts.  
  
#### <a name="to-add-a-wpf-control-to-a-windows-form"></a>So fügen Sie einem Windows Form ein WPF-Steuerelement hinzu  
  
1.  Öffnen Sie `Form1` im Windows Forms-Designer.  
  
2.  In der **Toolbox**, suchen Sie die Registerkarte mit der Bezeichnung **WPFUserControlLibrary WPF-Benutzersteuerelemente**.  
  
3.  Ziehen Sie eine Instanz von `UserControl1` auf das Formular.  
  
    -   Ein <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement wird automatisch zum Hosten des WPF-Steuerelements auf dem Formular erstellt.  
  
    -   Die <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement heißt `elementHost1` und klicken Sie in der **Eigenschaften** Fenster sehen Sie seine <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> -Eigenschaftensatz auf **"UserControl1"**.  
  
    -   Verweise auf WPF-Assemblys werden dem Projekt hinzugefügt.  
  
    -   Das `elementHost1`-Steuerelement verfügt über einen Smarttagbereich, in dem die verfügbaren Hostingoptionen anzeigt werden.   
  
4.  In der **ElementHost-Aufgaben** wählen Sie im Smarttagbereich **in übergeordnetem Container Andocken**.  
  
5.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Windows Forms und WPF sind unterschiedliche Technologien, wurden aber für eine enge Zusammenarbeit entwickelt. Um die Darstellung und das Verhalten in Ihren Anwendungen zu optimieren, versuchen Sie Folgendes:   
  
-   Hosten eines Windows Forms-Steuerelements in einer WPF-Seite. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).  
  
-   Übernehmen von visuellen Windows Forms-Stilen für den WPF-Inhalt. Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren von visuellen Stilen in einer Hybridanwendung](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).  
  
-   Ändern des Stils des WPF-Inhalts. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Formatieren von WPF-Inhalt](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Migration und Interoperabilität](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [Verwenden von WPF-Steuerelementen](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [WPF-Designer](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)

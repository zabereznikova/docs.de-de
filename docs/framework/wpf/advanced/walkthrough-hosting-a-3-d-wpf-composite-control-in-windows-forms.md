---
title: "Exemplarische Vorgehensweise: Hosten eines zusammengesetzten 3D-WPF-Steuerelements in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Zusammengesetzte Steuerelemente, Hosten von WPF in"
  - "Hosten von WPF-Inhalt in Windows Forms"
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Exemplarische Vorgehensweise: Hosten eines zusammengesetzten 3D-WPF-Steuerelements in Windows Forms
In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie ein zusammengesetztes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Steuerelement erstellen und mithilfe des <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelements in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelementen und \-Formularen hosten.  
  
 In dieser exemplarischen Vorgehensweise implementieren Sie ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-<xref:System.Windows.Controls.UserControl> mit zwei untergeordneten Steuerelementen.  <xref:System.Windows.Controls.UserControl> zeigt einen dreidimensionalen Kegel an.  3D\-Objekte lassen sich mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viel einfacher rendern als mit [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  Daher empfiehlt es sich, eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-<xref:System.Windows.Controls.UserControl>\-Klasse zu hosten, um 3D\-Grafiken in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] zu erstellen.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-<xref:System.Windows.Controls.UserControl>.  
  
-   Erstellen des Windows Forms\-Hostprojekts.  
  
-   Hosten von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-<xref:System.Windows.Controls.UserControl>.  
  
 Eine vollständige Codeauflistung der Aufgaben, die in dieser exemplarischen Vorgehensweise veranschaulicht werden, finden Sie unter [Beispiel zum Hosten eines zusammengesetzten WPF\-3D\-Steuerelements in Windows Forms](http://go.microsoft.com/fwlink/?LinkID=160001) \(möglicherweise in englischer Sprache\).  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
<a name="To_Create_the_UserControl"></a>   
## Erstellen von UserControl  
  
#### So erstellen Sie UserControl  
  
1.  Erstellen Sie ein WPF\-Benutzersteuerelementbibliothek\-Projekt mit dem Namen `HostingWpfUserControlInWf`.  
  
2.  Öffnen Sie die Datei UserControl1.xaml im [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
3.  Ersetzen Sie den generierten Code durch folgenden Code.  
  
     Dieser Code definiert ein <xref:System.Windows.Controls.UserControl?displayProperty=fullName> mit zwei untergeordneten Steuerelementen.  Das erste untergeordnete Steuerelement ist ein <xref:System.Windows.Controls.Label?displayProperty=fullName>\-Steuerelement und das zweite ein <xref:System.Windows.Controls.Viewport3D>\-Steuerelement, das einen 3D\-Kegel anzeigt.  
  
     [!code-xml[HostingWpfUserControlInWf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
<a name="To_Create_the_Windows_Forms_Host_Project"></a>   
## Erstellen des Windows Forms\-Hostprojekts  
  
#### So erstellen Sie das Hostprojekt  
  
1.  Fügen Sie der Projektmappe ein Windows\-Anwendungsprojekt mit dem Namen `WpfUserControlHost` hinzu.  Weitere Informationen finden Sie unter [Gewusst wie: Erstellen eines neuen WPF\-Anwendungsprojekts](http://msdn.microsoft.com/de-de/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
2.  Fügen Sie im Projektmappen\-Explorer einen Verweis auf die WindowsFormsIntegration\-Assembly mit dem Namen WindowsFormsIntegration.dll hinzu.  
  
3.  Fügen Sie Verweise auf die folgenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Assemblys hinzu:  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   WindowsBase  
  
4.  Fügen Sie einen Verweis auf das Projekt `HostingWpfUserControlInWf` hinzu.  
  
5.  Legen Sie `WpfUserControlHost` im Projektmappen\-Explorer als Startprojekt fest.  
  
<a name="To_Host_the_Windows_Presentation_Foundation"></a>   
## Hosten von Windows Presentation Foundation\-UserControl  
  
#### So hosten Sie UserControl  
  
1.  Öffnen Sie Form1 im Windows Forms\-Designer.  
  
2.  Klicken Sie im Eigenschaftenfenster auf **Ereignisse**, und doppelklicken Sie dann auf das <xref:System.Windows.Forms.Form.Load>\-Ereignis, um einen Ereignishandler zu erstellen.  
  
     Der Code\-Editor wird mit dem neu generierten `Form1_Load`\-Ereignishandler geöffnet.  
  
3.  Ersetzen Sie den Code in Form1.cs durch den folgenden Code.  
  
     Der `Form1_Load`\-Ereignishandler erstellt eine Instanz von `UserControl1` und fügt sie `` zur Auflistung der untergeordneten Steuerelemente des <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelements hinzu.  Das <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement wird der Auflistung der untergeordneten Steuerelemente des Formulars hinzugefügt.  
  
     [!code-csharp[HostingWpfUserControlInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]  
  
4.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF\-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)   
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms\-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Beispiel zum Hosten eines zusammengesetzten WPF\-Steuerelements in Windows Forms](http://go.microsoft.com/fwlink/?LinkID=160001)
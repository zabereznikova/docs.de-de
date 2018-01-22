---
title: 'Exemplarische Vorgehensweise: Hosten eines zusammengesetzten 3D-WPF-Steuerelements in Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 064626e3975838062c2d2287d29aa268edb8f21e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a>Exemplarische Vorgehensweise: Hosten eines zusammengesetzten 3D-WPF-Steuerelements in Windows Forms
In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie erstellen können eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zusammengesetzten steuern und hostet es im [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelementen und-Formularen mithilfe der <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement.  
  
 In dieser exemplarischen Vorgehensweise implementieren Sie eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> , zwei untergeordnete Steuerelemente enthält. Die <xref:System.Windows.Controls.UserControl> zeigt einen dreidimensionalen (3D) Kegel. Rendern von 3D-Objekten ist sehr viel einfacher, mit der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] als mit [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Aus diesem Grund ist es sinnvoll, Host eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> -Klasse zur Erstellung von 3D-Grafik in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.  
  
-   Erstellen das Windows Forms-Host-Projekt.  
  
-   Hosten der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.  
  
 Vollständige Codeliste der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Hosten eines 3D zusammengesetzten WPF-Steuerelements in Windows Forms-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160001).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]  
  
<a name="To_Create_the_UserControl"></a>   
## <a name="creating-the-usercontrol"></a>Erstellen von UserControl  
  
#### <a name="to-create-the-usercontrol"></a>So erstellen Sie UserControl  
  
1.  Erstellen Sie ein WPF-Benutzersteuerelementbibliothek-Projekt mit dem Namen `HostingWpfUserControlInWf`.  
  
2.  Öffnen Sie die Datei UserControl1.xaml in der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
3.  Ersetzen Sie den generierten Code durch den folgenden Code ein.  
  
     Dieser Code definiert eine <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> , zwei untergeordnete Steuerelemente enthält. Das erste untergeordnete Steuerelement ist ein <xref:System.Windows.Controls.Label?displayProperty=nameWithType> Steuerelement; das zweite ist ein <xref:System.Windows.Controls.Viewport3D> Steuerelement, das einen 3D-Kegel anzeigt.  
  
     [!code-xaml[HostingWpfUserControlInWf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
<a name="To_Create_the_Windows_Forms_Host_Project"></a>   
## <a name="creating-the-windows-forms-host-project"></a>Erstellen des Windows Forms-Hostprojekts  
  
#### <a name="to-create-the-host-project"></a>So erstellen Sie das Hostprojekt  
  
1.  Fügen Sie ein Windows-Anwendungsprojekt mit dem Namen `WpfUserControlHost` der Projektmappe. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines neuen WPF-Anwendungsprojekts](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
2.  Fügen Sie im Projektmappen-Explorer einen Verweis auf die Assembly mit die Namen WindowsFormsIntegration.dll WindowsFormsIntegration.  
  
3.  Fügen Sie Verweise auf die folgenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Assemblys:  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   WindowsBase  
  
4.  Fügen einen Verweis auf das `HostingWpfUserControlInWf`-Projekt hinzu.  
  
5.  Legen Sie im Projektmappen-Explorer die `WpfUserControlHost` Projekt das Startprojekt sein.  
  
<a name="To_Host_the_Windows_Presentation_Foundation"></a>   
## <a name="hosting-the-windows-presentation-foundation-usercontrol"></a>Hosten von Windows Presentation Foundation UserControl  
  
#### <a name="to-host-the-usercontrol"></a>So hosten Sie UserControl  
  
1.  Öffnen Sie Form1 in der Windows Forms-Designer.  
  
2.  Klicken Sie im Fenster Eigenschaften auf **Ereignisse**, und doppelklicken Sie dann auf die <xref:System.Windows.Forms.Form.Load> Ereignis, um einen Ereignishandler erstellen.  
  
     Der Code-Editor wird geöffnet, auf die neu generierten `Form1_Load` -Ereignishandler.  
  
3.  Ersetzen Sie den Code in "Form1.cs" durch den folgenden Code ein.  
  
     Die `Form1_Load` -Ereignishandler erstellt eine Instanz des `UserControl1` und fügt auf der <xref:System.Windows.Forms.Integration.ElementHost> des Steuerelements Auflistung von untergeordneten Steuerelementen. Die <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement Auflistung der untergeordneten Steuerelemente des Formulars hinzugefügt.  
  
     [!code-csharp[HostingWpfUserControlInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]  
  
4.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF-Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160001)

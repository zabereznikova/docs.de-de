---
title: 'Exemplarische Vorgehensweise: Hosten eines ActiveX-Steuerelements in WPF'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fc4f577da04fb8ed15bae3c0497b35803a46f08f
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a>Exemplarische Vorgehensweise: Hosten eines ActiveX-Steuerelements in WPF
Um verbesserte Interaktion mit Browsern zu aktivieren, können Sie [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] steuert in Ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-basierten Anwendung. In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie hosten können die [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] als ein Steuerelement auf einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Seite.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen des Projekts.  
  
-   Erstellen das ActiveX-Steuerelement.  
  
-   Hosting von ActiveX-Steuerelement auf einer WPF-Seite.  
  
 Wenn Sie diese exemplarische Vorgehensweise abgeschlossen haben, werden Sie wissen, wie mit [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] steuert in Ihrem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]--basierten Anwendung.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] installiert auf dem Computer, auf dem Visual Studio installiert ist.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
  
#### <a name="to-create-and-set-up-the-project"></a>So erstellen und richten Sie das Projekt ein  
  
1.  Erstellen Sie ein WPF-Anwendungsprojekt mit dem Namen `HostingAxInWpf`.  
  
2.  Die Projektmappe ein Windows Forms-Steuerelementbibliothek-Projekt hinzu, und nennen Sie das Projekt `WmpAxLib`.  
  
3.  Fügen Sie im Projekt WmpAxLib einen Verweis auf die Windows Media Player-Assembly, die wmp.dll genannt wird.  
  
4.  Öffnen der **Toolbox**.  
  
5.  Mit der rechten Maustaste die **Toolbox**, und klicken Sie dann auf **Elemente auswählen**.  
  
6.  Klicken Sie auf die **COM-Komponenten** Registerkarte die **Windows Media Player** steuern, und klicken Sie dann auf **OK**.  
  
     Windows Media Player-Steuerelement wird hinzugefügt, um die **Toolbox**.  
  
7.  Klicken Sie im Projektmappen-Explorer mit der Maustaste die **"UserControl1"** Datei, und klicken Sie dann auf **umbenennen**.  
  
8.  Ändern Sie den Namen in `WmpAxControl.vb` oder `WmpAxControl.cs`, abhängig von der Sprache.  
  
9. Wenn Sie aufgefordert werden, alle Verweise umzubenennen, klicken Sie auf **Ja**.  
  
## <a name="creating-the-activex-control"></a>Erstellen des ActiveX-Steuerelements  
 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] generiert automatisch ein <xref:System.Windows.Forms.AxHost> Wrapperklasse für ein [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] steuern, wenn das Steuerelement auf einer Entwurfsoberfläche hinzugefügt wird. Die folgende Prozedur erstellt eine verwaltete Assembly mit dem Namen AxInterop.WMPLib.dll.  
  
#### <a name="to-create-the-activex-control"></a>Beim Erstellen des ActiveX-Steuerelements  
  
1.  Öffnen Sie WmpAxControl.vb oder WmpAxControl.cs in Windows Forms-Designer an.  
  
2.  Aus der **Toolbox**, fügen Sie das Windows Media Player-Steuerelement auf die Entwurfsoberfläche.  
  
3.  Legen Sie im Fenster Eigenschaften den Wert des Windows Media Player-Steuerelements <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Fill>.  
  
4.  Die WmpAxLib-Steuerelementbibliothek-Projekt zu erstellen.  
  
## <a name="hosting-the-activex-control-on-a-wpf-page"></a>Hosting von ActiveX-Steuerelement auf einer WPF-Seite  
  
#### <a name="to-host-the-activex-control"></a>Zum Hosten des ActiveX-Steuerelements  
  
1.  Fügen Sie im HostingAxInWpf-Projekt einen Verweis auf die generierten [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] Interop-Assembly.  
  
     Diese Assembly ist mit dem Namen AxInterop.WMPLib.dll und wurde der Debugordner des Projekts WmpAxLib hinzugefügt, wenn Sie das Windows Media Player-Steuerelement importiert.  
  
2.  Fügen Sie einen Verweis auf die WindowsFormsIntegration-Assembly mit die Namen WindowsFormsIntegration.dll hinzu.  
  
3.  Hinzufügen eines Verweises auf die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Assembly, die System.Windows.Forms.dll genannt wird.  
  
4.  Öffnen Sie "MainWindow.xaml" im WPF-Designer.  
  
5.  Name der <xref:System.Windows.Controls.Grid> Element `grid1`.  
  
     [!code-xaml[HostingAxInWpf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]  
  
6.  Wählen Sie in der Entwurfsansicht oder der XAML-Ansicht, die <xref:System.Windows.Window> Element.  
  
7.  Klicken Sie im Eigenschaftenfenster auf die **Ereignisse** Registerkarte.  
  
8.  Doppelklicken Sie auf die <xref:System.Windows.FrameworkElement.Loaded> Ereignis.  
  
9. Fügen Sie folgenden Code zum Behandeln der <xref:System.Windows.FrameworkElement.Loaded> Ereignis.  
  
     Dieser Code erstellt eine Instanz von der <xref:System.Windows.Forms.Integration.WindowsFormsHost> steuern und fügt Sie eine Instanz von der `AxWindowsMediaPlayer` Steuerelement als untergeordnetes Element.  
  
     [!code-csharp[HostingAxInWpf#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF-Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)

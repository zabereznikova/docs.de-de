---
title: "Gewusst wie: Aktivieren von visuellen Stilen in einer Hybridanwendung | Microsoft Docs"
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
  - "Hybridanwendungen [WPF-Interoperabilität]"
  - "Visuelle Stile [Windows Forms]"
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Aktivieren von visuellen Stilen in einer Hybridanwendung
Dieses Thema veranschaulicht, wie visuelle [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] Stile für ein [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelement aktiviert werden, das in einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-basierten Anwendung gehostet wird.  
  
 Wenn die Anwendung die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>\-Methode aufruft, werden für die meisten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente automatisch visuelle Stile verwendet, sofern die Anwendung unter [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] ausgeführt wird.  Weitere Informationen finden Sie unter [Rendering von Steuerelementen mit visuellen Stilen](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md).  
  
 Eine vollständige Codeauflistung der in diesem Thema veranschaulichten Aufgaben finden Sie unter [Beispiel zum Aktivieren von visuellen Stilen in einer Hybridanwendung](http://go.microsoft.com/fwlink/?LinkID=159986).  
  
## Aktivieren von visuellen Windows Forms\-Stilen  
  
#### So aktivieren Sie visuelle Windows Forms\-Stile  
  
1.  Erstellen Sie ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungsprojekt mit dem Namen `HostingWfWithVisualStyles`.  
  
2.  Fügen Sie im Projektmappen\-Explorer Verweise auf die folgenden Assemblys hinzu.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  Doppelklicken Sie in der Toolbox auf das Symbol <xref:System.Windows.Controls.Grid>, um ein <xref:System.Windows.Controls.Grid>\-Element auf der Entwurfsoberfläche zu platzieren.  
  
4.  Legen Sie im Eigenschaftenfenster den Wert der <xref:System.Windows.FrameworkElement.Height%2A>\-Eigenschaft und der <xref:System.Windows.FrameworkElement.Width%2A>\-Eigenschaft auf **Auto** fest.  
  
5.  Wählen Sie in der Entwurfsansicht oder XAML\-Ansicht <xref:System.Windows.Window> aus.  
  
6.  Klicken Sie im Eigenschaftenfenster auf die Registerkarte **Ereignisse**.  
  
7.  Doppelklicken Sie auf das <xref:System.Windows.FrameworkElement.Loaded>\-Ereignis.  
  
8.  Fügen Sie in "MainWindow.xaml.vb" bzw. "MainWindow.xaml.cs" den folgenden Code ein, um das <xref:System.Windows.FrameworkElement.Loaded>\-Ereignis zu behandeln.  
  
     [!code-csharp[HostingWfWithVisualStyles#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
     Das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelement wird mit visuellen Stilen gezeichnet.  
  
## Deaktivieren von visuellen Windows Forms\-Stilen  
 Um visuelle Stile zu deaktivieren, entfernen Sie einfach den Aufruf der <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>\-Methode.  
  
#### So deaktivieren Sie visuelle Windows Forms\-Stile  
  
1.  Öffnen Sie "MainWindow.xaml.vb" bzw. "MainWindow.xaml.cs" im Code\-Editor.  
  
2.  Kommentieren Sie den Aufruf der <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>\-Methode aus.  
  
3.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
     Das [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelement wird mit dem Standardsystemstil gezeichnet.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>   
 <xref:System.Windows.Forms.VisualStyles>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Rendering von Steuerelementen mit visuellen Stilen](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)   
 [Exemplarische Vorgehensweise: Hosten eines Windows Forms\-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
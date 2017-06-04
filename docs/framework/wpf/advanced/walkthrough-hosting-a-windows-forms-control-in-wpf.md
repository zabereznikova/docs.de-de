---
title: "Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF | Microsoft Docs"
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
  - "Hosten eines Windows Forms-Steuerelements in WPF"
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
caps.latest.revision: 36
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt viele Steuerelemente mit einem umfangreichen Featuresatz bereit.  Es kann jedoch vorkommen, dass Sie auf Ihren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Seiten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente verwenden möchten.  Beispielsweise könnte eine beträchtliche Investition in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelementen vorliegen, oder Sie verfügen über ein [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelement, das eine einzigartige Funktionalität zur Verfügung stellt.  
  
 In dieser exemplarischen Vorgehensweise wird das Hosten eines [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=fullName>\-Steuerelements auf einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Seite mithilfe von Code beschrieben.  
  
 Eine vollständige Codeauflistung der Aufgaben, die in dieser exemplarischen Vorgehensweise gezeigt wurden, finden Sie unter [Beispiel zum Hosten eines Windows Forms\-Steuerelements in WPF](http://go.microsoft.com/fwlink/?LinkID=160057).  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## Hosten des Windows Forms\-Steuerelements  
  
#### So hosten Sie das MaskedTextBox\-Steuerelement  
  
1.  Erstellen Sie ein WPF\-Anwendungsprojekt mit dem Namen `HostingWfInWpf`.  
  
2.  Fügen Sie Verweise auf die folgenden Assemblys hinzu.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  Öffnen Sie im [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] die Datei MainWindow.xaml.  
  
4.  Geben Sie für das <xref:System.Windows.Controls.Grid>\-Element den Namen `grid1` ein.  
  
     [!code-xml[HostingWfInWPF#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]  
  
5.  Wählen Sie in der Designansicht oder XAML\-Ansicht das <xref:System.Windows.Window>\-Element aus.  
  
6.  Klicken Sie im Eigenschaftenfenster auf die Registerkarte **Ereignisse**.  
  
7.  Doppelklicken Sie auf das <xref:System.Windows.FrameworkElement.Loaded>\-Ereignis.  
  
8.  Fügen Sie folgenden Code ein, um das <xref:System.Windows.FrameworkElement.Loaded>\-Ereignis zu behandeln.  
  
     [!code-csharp[HostingWfInWPF#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]  
  
9. Fügen Sie am Anfang der Datei die folgende `Imports`\- oder `using`\-Anweisung hinzu.  
  
     [!code-csharp[HostingWfInWPF#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]  
  
10. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Exemplarische Vorgehensweise: Hosten eines Windows Forms\-Steuerelements in WPF mithilfe von XAML](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)   
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms\-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF\-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)   
 [Windows Forms\-Steuerelemente und äquivalente WPF\-Steuerelemente](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)   
 [Beispiel zum Hosten eines Windows Forms\-Steuerelements in WPF](http://go.microsoft.com/fwlink/?LinkID=160057)
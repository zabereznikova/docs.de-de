---
title: "Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF mithilfe von XAML | Microsoft Docs"
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
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 34
---
# Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF mithilfe von XAML
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt viele Steuerelemente mit einem umfangreichen Featuresatz bereit.  Es kann jedoch vorkommen, dass Sie auf Ihren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Seiten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente verwenden möchten.  Beispielsweise könnte eine beträchtliche Investition in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelementen vorliegen, oder Sie verfügen über ein [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelement, das eine einzigartige Funktionalität zur Verfügung stellt.  
  
 In dieser exemplarischen Vorgehensweise wird das Hosten eines Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=fullName>\-Steuerelements auf einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Seite mithilfe von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] beschrieben.  
  
 Eine vollständige Codeauflistung der Aufgaben, die in dieser exemplarischen Vorgehensweise gezeigt wurden, finden Sie unter [Hosten eines Windows Forms\-Steuerelements in WPF mit XAML\-Beispiel](http://go.microsoft.com/fwlink/?LinkID=160000).  
  
## Vorbereitungsmaßnahmen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## Hosten des Windows Forms\-Steuerelements  
  
#### So hosten Sie das MaskedTextBox\-Steuerelement  
  
1.  Erstellen Sie ein WPF\-Anwendungsprojekt mit dem Namen `HostingWfInWpfWithXaml`.  
  
2.  Fügen Sie Verweise auf die folgenden Assemblys hinzu.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  Öffnen Sie im [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] die Datei MainWindow.xaml.  
  
4.  Fügen Sie im <xref:System.Windows.Window>\-Element die folgende Namespacezuordnung hinzu.  Die `wf`\-Namespacezuordnung erstellt einen Verweis auf die Assembly, die das [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]\-Steuerelement enthält.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  Fügen Sie im <xref:System.Windows.Controls.Grid>\-Element den folgenden XAML\-Code hinzu.  
  
     Das <xref:System.Windows.Forms.MaskedTextBox>\-Steuerelement wird als untergeordnetes Element des <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Steuerelements erstellt.  
  
     [!code-xml[HostingWfInWpfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF\-Designer](http://msdn.microsoft.com/de-de/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Exemplarische Vorgehensweise: Hosten eines Windows Forms\-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)   
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms\-Steuerelements in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF\-Steuerelements in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)   
 [Windows Forms\-Steuerelemente und äquivalente WPF\-Steuerelemente](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)   
 [Beispiel zum Hosten eines Windows Forms\-Steuerelements in WPF mit XAML](http://go.microsoft.com/fwlink/?LinkID=160000)
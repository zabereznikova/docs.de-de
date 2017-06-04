---
title: "Gewusst wie: Aufteilen von Bereichen mithilfe des DockPanel-Elements | Microsoft Docs"
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
  - "Steuerelemente [WPF], DockPanel"
  - "DockPanel-Steuerelement, Bereichspartitionierung"
  - "Bereichspartitionierung"
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Aufteilen von Bereichen mithilfe des DockPanel-Elements
Im folgenden Beispiel wird ein einfaches [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]\-Framework mithilfe eines <xref:System.Windows.Controls.DockPanel>\-Elements erstellt.  Das <xref:System.Windows.Controls.DockPanel> teilt den verfügbaren Platz unter seinen untergeordneten Elementen auf.  
  
## Beispiel  
 In diesem Beispiel wird die <xref:System.Windows.Controls.DockPanel.Dock%2A>\-Eigenschaft \(eine [angefügte Eigenschaft](GTMT)\) verwendet, um zwei identische <xref:System.Windows.Controls.Border>\-Elemente an das <xref:System.Windows.Controls.Dock> des aufgeteilten Bereichs anzudocken.  Ein drittes <xref:System.Windows.Controls.Border>\-Element, dessen Breite auf 200 Pixel festgelegt ist, wird an das <xref:System.Windows.Controls.Dock> angedockt.   Ein viertes <xref:System.Windows.Controls.Border>\-Element wird an das <xref:System.Windows.Controls.Dock> des Bildschirms angedockt.  Das letzte <xref:System.Windows.Controls.Border>\-Element füllt automatisch den verbleibenden Platz aus.  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  In den Standardeinstellungen füllt das letzte untergeordnete Element eines <xref:System.Windows.Controls.DockPanel>\-Elements den übrigen verfügbaren Platz aus.  Wenn Sie dieses Verhalten nicht möchten, legen Sie `LastChildFill="False"` fest.  
  
 Die kompilierte Anwendung ergibt eine neue Benutzeroberfläche, die folgendermaßen aussieht.  
  
 ![Ein typisches DockPanel&#45;Szenario.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.png "panel\_intro\_dockpanel")  
  
## Siehe auch  
 <xref:System.Windows.Controls.DockPanel>   
 [Übersicht über Panel\-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)
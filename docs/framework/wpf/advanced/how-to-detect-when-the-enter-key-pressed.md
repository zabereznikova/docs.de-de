---
title: "Gewusst wie: Erkennen, wenn die EINGABETASTE gedr&#252;ckt wird | Microsoft Docs"
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
  - "Eingabetaste, Ermitteln"
  - "Schlüssel, Eingabe"
ms.assetid: a66f39d2-ef4a-43a5-b454-a4ea0fe88655
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Erkennen, wenn die EINGABETASTE gedr&#252;ckt wird
Dieses Beispiel zeigt, wie Sie erkennen können, wenn auf der Tastatur die <xref:System.Windows.Input.Key>\-Taste gedrückt wird.  
  
 Dieses Beispiel besteht aus einer [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Datei und einer Code\-Behind\-Datei.  
  
## Beispiel  
 Wenn Benutzer die <xref:System.Windows.Input.Key>\-Taste im <xref:System.Windows.Controls.TextBox> drücken, wird die Eingabe des Textfelds in einem anderen Bereich der [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] angezeigt.  
  
 Der folgende [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]\-Code erstellt die Benutzeroberfläche, die die Elemente <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.TextBlock> und <xref:System.Windows.Controls.TextBox> umfasst.  
  
 [!code-xml[keydown#KeyDownUI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml#keydownui)]  
  
 Der folgende Code\-Behind erstellt den <xref:System.Windows.UIElement.KeyDown>\-Ereignishandler.  Wenn es sich bei der gedrückten Taste um die <xref:System.Windows.Input.Key>\-Taste handelt, wird im <xref:System.Windows.Controls.TextBlock> eine Meldung angezeigt.  
  
 [!code-csharp[keydown#KeyDownSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyDown/CSharp/Window1.xaml.cs#keydownsample)]
 [!code-vb[keydown#KeyDownSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyDown/VisualBasic/Window1.xaml.vb#keydownsample)]  
  
## Siehe auch  
 [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
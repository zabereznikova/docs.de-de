---
title: "Gewusst wie: Konfigurieren eines Objekts zum Folgen des Mauszeigers | Microsoft Docs"
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
  - "Cursor (Mauszeiger), Folgen von Objekten"
  - "Folgen des Mauszeigers (Cursor)"
  - "Mauszeiger (Cursor), Folgen von Objekten"
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Konfigurieren eines Objekts zum Folgen des Mauszeigers
Dieses Beispiel zeigt, wie Sie ein Objekt so konfigurieren, dass sich seine Dimensionen ändern, wenn sich der Mauszeiger über den Bildschirm bewegt.  
  
 Das Beispiel umfasst eine [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]\-Datei, die die [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] erstellt, und eine CodeBehind\-Datei, die den Ereignishandler erstellt.  
  
## Beispiel  
 Der folgende [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]\-Code erstellt die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], die aus einer <xref:System.Windows.Shapes.Ellipse> in einem <xref:System.Windows.Controls.StackPanel> besteht, und fügt den Ereignishandler für das <xref:System.Windows.UIElement.MouseMove>\-Ereignis an.  
  
 [!code-xml[mouseMoveWithPointer#MouseMoveWithPointerXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 Der folgende Code\-Behind erstellt den <xref:System.Windows.UIElement.MouseMove>\-Ereignishandler.  Wenn sich der Mauszeiger bewegt, nehmen Höhe und Breite der <xref:System.Windows.Shapes.Ellipse> zu oder ab.  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## Siehe auch  
 [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)
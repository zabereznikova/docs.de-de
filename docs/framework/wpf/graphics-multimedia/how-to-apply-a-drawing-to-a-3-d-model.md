---
title: "Gewusst wie: Anwenden einer Zeichnung auf ein 3D-Modell | Microsoft Docs"
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
  - "3D-Modelle, Anwenden von Zeichnungen auf"
  - "Zeichnungen, Anwenden auf 3D-Modelle"
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Anwenden einer Zeichnung auf ein 3D-Modell
Dieses Beispiel zeigt, wie ein <xref:System.Windows.Media.DrawingBrush>\-Objekt als <xref:System.Windows.Media.Media3D.Material> verwendet wird, um es auf ein [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)]\-Modell anzuwenden.  
  
 Der folgende Code definiert ein <xref:System.Windows.Media.DrawingGroup>\-Objekt als Inhalt eines <xref:System.Windows.Media.DrawingBrush>\-Objekts.  Das <xref:System.Windows.Media.DrawingBrush>\-Objekt ist als <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A>\-Eigenschaft des <xref:System.Windows.Media.Media3D.DiffuseMaterial>\-Objekts festgelegt, das auf eine [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]\-Ebene angewendet wird.  
  
 **Hinweis:** Es ist häufig erstrebenswert, komplexe Objekte und Werte wie die folgende Zeichnung als Ressourcen zu definieren, die erneut verwendet werden können und den Code vereinfachen.  Weitere Informationen finden Sie unter [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 [!code-xml[3DGallery_snip#ApplyDrawingToMaterialInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]  
  
## Beispiel  
 Im folgenden Code wird das gesamte Beispiel dargestellt.  
  
 [!code-xml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]  
  
## Siehe auch  
 [XAML\-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Erstellen einer 3D\-Szene](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Übersicht über 3D\-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
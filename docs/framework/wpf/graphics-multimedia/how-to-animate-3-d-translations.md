---
title: "Gewusst wie: Animieren von 3D-&#220;bersetzungen | Microsoft Docs"
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
  - "3D-Übersetzungen, Animation"
  - "Animation, 3D-Übersetzungen"
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Animieren von 3D-&#220;bersetzungen
Dieses Thema veranschaulicht, wie eine für ein [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)]\-Modell festgelegte Übersetzungstransformation animiert wird.  
  
 Der Code unten zeigt die Anwendung eines <xref:System.Windows.Media.Media3D.TranslateTransform3D>\-Objekts auf die <xref:System.Windows.Media.Media3D.Model3D.Transform%2A>\-Eigenschaft von einem <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
 [!code-xml[Animation3DGallery_snip#Translation3DAnimationInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 Die <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A>\-Eigenschaft dieses <xref:System.Windows.Media.Media3D.TranslateTransform3D>\-Objekts wird mithilfe des unten stehenden Codes animiert.  
  
 [!code-xml[Animation3DGallery_snip#Translation3DAnimationInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## Beispiel  
 Im folgenden Code wird das gesamte Beispiel dargestellt.  
  
 [!code-xml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## Siehe auch  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Erstellen einer 3D\-Szene](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [Übersicht über 3D\-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
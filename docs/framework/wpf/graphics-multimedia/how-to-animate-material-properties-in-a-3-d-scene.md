---
title: "Gewusst wie: Animieren von Material-Eigenschaften in einer 3D-Szene | Microsoft Docs"
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
  - "3-D-Szenen, Animierende Material-Eigenschaften"
  - "Animation, Animierende Eigenschaften in 3D-Szenen"
  - "Material-Eigenschaften, Animieren in 3D-Szenen"
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Animieren von Material-Eigenschaften in einer 3D-Szene
In diesem Beispiel wird die Animation der <xref:System.Windows.Media.Brush.Opacity%2A>\-Eigenschaft des <xref:System.Windows.Media.Media3D.Material>, das auf ein [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)]\-Modell angewendet wird, veranschaulicht.  
  
 Im folgenden Codebeispiel wird der <xref:System.Windows.Media.LinearGradientBrush> definiert, der als <xref:System.Windows.Media.Media3D.Material> verwendet wird, das auf das 3D\-Objekt angewendet wird.  
  
 [!code-xml[Animation3DGallery_snip#AnimateMaterialExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 Die <xref:System.Windows.Media.Brush.Opacity%2A>\-Eigenschaft dieses <xref:System.Windows.Media.LinearGradientBrush>\-Elements wird mithilfe des unten stehenden Codebeispiels animiert.  
  
 [!code-xml[Animation3DGallery_snip#AnimateMaterialExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## Beispiel  
 Im folgenden Code wird das gesamte Beispiel dargestellt.  
  
 [!code-xml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## Siehe auch  
 [Erstellen einer 3D\-Szene](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [Übersicht über 3D\-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
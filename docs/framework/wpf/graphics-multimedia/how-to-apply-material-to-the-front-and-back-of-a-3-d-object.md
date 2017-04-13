---
title: "Gewusst wie: Anwenden von Material auf die Vorder- und R&#252;ckseite eines 3D-Objekts | Microsoft Docs"
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
  - "3D-Objekte, Anwenden der Material-Klasse"
  - "Klassen, Material"
  - "Material-Klasse, Anwenden auf beide Seiten des 3D-Objekts"
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Anwenden von Material auf die Vorder- und R&#252;ckseite eines 3D-Objekts
Im folgenden Beispiel wird veranschaulicht, wie <xref:System.Windows.Media.Media3D.Material> auf die Vorder\- und die Rückseite eines 3D\-Objekts angewendet und das Objekt animiert wird, um es von beiden Seiten anzuzeigen.  Die <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A>\-Eigenschaft von einem <xref:System.Windows.Media.Media3D.GeometryModel3D> wird verwendet, um einen roten <xref:System.Windows.Media.Brush> auf die Vorderseite des Objekts anzuwenden. Mit der <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A>\-Eigenschaft vom <xref:System.Windows.Media.Media3D.GeometryModel3D> wird ein blauer <xref:System.Windows.Media.Brush> auf die Rückseite des Objekts angewendet.  Der folgende Code zeigt die Anwendung der Materialien auf das Objekt:  
  
 [!code-xml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## Beispiel  
 Im folgenden Code wird das gesamte Beispiel dargestellt.  
  
 [!code-xml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## Siehe auch  
 [Erstellen einer 3D\-Szene](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [Übersicht über 3D\-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Animieren von Material\-Eigenschaften in einer 3D\-Szene](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)   
 [Anwenden von Emissive Material auf ein 3D\-Objekt](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-emissive-material-to-a-3-d-object.md)
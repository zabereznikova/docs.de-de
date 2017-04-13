---
title: "Gewusst wie: Anwenden von EmissiveMaterial auf ein 3D-Objekt | Microsoft Docs"
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
  - "3D-Objekte, Anwenden von EmissiveMaterial"
  - "EmissiveMaterial, Anwenden auf 3D-Objekte"
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Anwenden von EmissiveMaterial auf ein 3D-Objekt
Im folgenden Beispiel wird veranschaulicht, wie mit <xref:System.Windows.Media.Media3D.EmissiveMaterial> Farbe, die der Farbe des EmissiveMaterial\-Pinsels entspricht, zu einem bestehenden Material hinzugefügt wird.  Der folgende Code enthält <xref:System.Windows.Media.Media3D.DiffuseMaterial> und <xref:System.Windows.Media.Media3D.EmissiveMaterial>, die gemeinsam angewendet werden, um die Farbe Blau der DiffuseMaterial\-Darstellung hinzuzufügen.  
  
 [!code-xml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 In prozeduralem Code:  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## Beispiel  
 Im folgenden Code wird das gesamte Beispiel in XAML dargestellt.  
  
 [!code-xml[3DGallery_snip#EmissiveMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## Beispiel  
 Im Folgenden wird das gesamte Beispiel in prozeduralem Code dargestellt.  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## Siehe auch  
 [Erstellen einer 3D\-Szene](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [Übersicht über 3D\-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Animieren von Material\-Eigenschaften in einer 3D\-Szene](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)   
 [Anwenden von Material auf die Vorder\- und Rückseite eines 3D\-Objekts](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
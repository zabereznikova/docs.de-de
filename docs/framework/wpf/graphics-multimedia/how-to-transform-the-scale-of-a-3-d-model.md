---
title: "Gewusst wie: Transformieren der Skalierung eines 3D-Modells | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "3D-Objekte, Skalieren"
  - "Skalieren, 3D-Objekte"
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
caps.latest.revision: 3
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# Gewusst wie: Transformieren der Skalierung eines 3D-Modells
Dieses Beispiel zeigt, wie ein 3D\-Objekt skaliert wird.  Um ein 3D\-Objekt zu skalieren, verwenden Sie <xref:System.Windows.Media.Media3D.ScaleTransform3D>.  Die Eigenschaften <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> und <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> ändern die Größe des Elements um den von Ihnen angegebenen Faktor.  Beispielsweise wird ein Objekt durch einen <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>\-Wert von 1,5 auf 150 Prozent der ursprünglichen Breite gestreckt.  Bei einem <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>\-Wert von 0,5 verringert sich die Höhe eines Objekts um 50 Prozent.  Der folgende Code zeigt, wie <xref:System.Windows.Media.Media3D.ScaleTransform3D> als Transformation für ein <xref:System.Windows.Media.Media3D.GeometryModel3D> verwendet wird.  
  
 [!code-xml[3DGallery_snip#ScaleTransform3DExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## Beispiel  
 Im folgenden Code wird das gesamte Beispiel dargestellt.  
  
 [!code-xml[3DGallery_snip#ScaleTransform3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## Siehe auch  
 [Animieren von 3D\-Übersetzungen](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-3-d-translations.md)   
 [Erstellen einer 3D\-Szene](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [Übersicht über 3D\-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
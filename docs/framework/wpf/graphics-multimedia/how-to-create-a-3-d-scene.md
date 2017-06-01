---
title: "Gewusst wie: Erstellen einer 3D-Szene | Microsoft Docs"
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
  - "3-D-Szenen"
  - "Erstellen, 3-D-Szenen"
  - "Szenen, 3D"
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Erstellen einer 3D-Szene
In diesem Beispiel wird gezeigt, wie ein 3D\-Objekt erstellt wird, das wie ein gedrehtes Blatt Papier aussieht.  Zum Erstellen dieser einfachen 3D\-Szene wird ein <xref:System.Windows.Controls.Viewport3D> zusammen mit den folgenden Komponenten verwendet:  
  
-   Eine Kamera wird mit einer <xref:System.Windows.Media.Media3D.PerspectiveCamera> erstellt.  Die Kamera gibt an, welcher Teil der 3D\-Szene angezeigt werden kann.  
  
-   Ein Netz wird erstellt, um die Form des 3D\-Objekts \(Blatt Papier\) mit der <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A>\-Eigenschaft vom <xref:System.Windows.Media.Media3D.GeometryModel3D> anzugeben.  
  
-   Ein Material, das auf der Oberfläche des Objekts \(in diesem Beispiel ein linearer Farbverlauf\) angezeigt wird, wird mit der <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A>\-Eigenschaft vom <xref:System.Windows.Media.Media3D.GeometryModel3D> angegeben.  
  
-   Ein Licht, das auf dem Objekt leuchtet, wird mit <xref:System.Windows.Media.Media3D.DirectionalLight> erstellt.  
  
## Beispiel  
 Der folgende Code zeigt, wie eine 3D\-Szene in XAML erstellt wird.  
  
 [!code-xml[3DGallery_snip#Basic3DShapeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## Beispiel  
 Der folgende Code zeigt, wie die gleiche 3D\-Szene in prozeduralem Code erstellt wird.  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## Siehe auch  
 [Übersicht über 3D\-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
---
title: "Gewusst wie: Testen der Point4D-Struktur auf Gleichheit und Ungleichheit | Microsoft Docs"
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
  - "Gleichheit, Testen von Point4D-Strukturen auf"
  - "Ungleichheit, Testen von Point4D-Strukturen auf"
  - "Point4D-Strukturen, Testen auf Gleichheit"
  - "Point4D-Strukturen, Testen auf Ungleichheit"
  - "Testen, Point4D-Strukturen auf Gleichheit"
  - "Testen, Point4D-Strukturen auf Ungleichheit"
ms.assetid: e004a67e-db7f-4af8-a31f-e6b2a44ccf34
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Testen der Point4D-Struktur auf Gleichheit und Ungleichheit
In diesem Beispiel wird gezeigt, wie <xref:System.Windows.Media.Media3D.Point4D>\-Strukturen auf Gleichheit und Ungleichheit getestet werden.  
  
 Im folgenden Code wird veranschaulicht, wie <xref:System.Windows.Media.Media3D.Point4D>\-Strukturen mit den <xref:System.Windows.Media.Media3D.Point4D>\-Gleichheitsmethoden auf Gleichheit und Ungleichheit getestet werden.  Die <xref:System.Windows.Media.Media3D.Point4D>\-Strukturen werden mit dem überladenen Operator \(`==`\) auf Gleichheit getestet. Dann werden sie mit dem überladenen Operator \(`!=`\) auf Ungleichheit getestet. Schließlich werden eine <xref:System.Windows.Media.Media3D.Point3D>\-Struktur und eine <xref:System.Windows.Media.Media3D.Point4D>\-Struktur mit der statischen <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>\-Methode auf Gleichheit getestet.  
  
## Beispiel  
 [!code-csharp[3DGallery_procedural_snip#Point4DEqualityExample_csharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Misc3DOperationsExample.cs#point4dequalityexample_csharp)]  
  
## Siehe auch  
 <xref:System.Windows.Media.Media3D.Point4D.op_Equality%2A>   
 <xref:System.Windows.Media.Media3D.Point4D.op_Inequality%2A>   
 <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>
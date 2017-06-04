---
title: "Einschr&#228;nken der Zeichenfl&#228;che in GDI+ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Clipping, Verwenden von GDI+"
  - "GDI+, Clipping"
  - "GDI+, Einschränken der Zeichenoberfläche"
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Einschr&#228;nken der Zeichenfl&#228;che in GDI+
Beim Clipping wird das Zeichnen auf ein bestimmtes Rechteck oder einen bestimmten Bereich beschränkt.  Die folgende Abbildung zeigt die auf einen herzförmigen Bereich zugeschnittene Zeichenfolge "Hello".  
  
 ![Eingeschränkte Zeichnungsoberfläche](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art30.png "AboutGdip02\_Art30")  
  
## Clipping mit Bereichen  
 Bereiche können aus Pfaden konstruiert werden, und Pfade können die Umrisse von Schriftzeichen enthalten. Folglich können Sie Textumrisse für das Clipping verwenden.  Die folgende Abbildung zeigt eine Gruppe von konzentrischen Ellipsen, die auf die Innenfläche einer Textzeichenfolge zugeschnitten wurde.  
  
 ![Eingeschränkte Zeichnungsoberfläche](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art31.png "AboutGdip02\_Art31")  
  
 Um mit der Clippingfunktion zu zeichnen, erstellen Sie ein <xref:System.Drawing.Graphics>\-Objekt, legen dessen <xref:System.Drawing.Graphics.Clip%2A>\-Eigenschaft fest und rufen dann die Zeichenmethoden dieses <xref:System.Drawing.Graphics>\-Objekts auf:  
  
 [!code-csharp[LinesCurvesAndShapes#91](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## Siehe auch  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Region?displayProperty=fullName>   
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Verwenden von Bereichen](../../../../docs/framework/winforms/advanced/using-regions.md)
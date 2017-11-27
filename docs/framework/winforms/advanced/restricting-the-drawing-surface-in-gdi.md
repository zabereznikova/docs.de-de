---
title: "Einschränken der Zeichenfläche in GDI+"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 213f0afefa1f8635d2b70d2e3626b7fbe748b42c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="restricting-the-drawing-surface-in-gdi"></a>Einschränken der Zeichenfläche in GDI+
Clipping wird das Zeichnen für eine bestimmte Rechteck oder eine Region beschränkt. Die folgende Abbildung zeigt die Zeichenfolge "Hello" in einer Region herzförmige abgeschnitten.  
  
 ![Eingeschränkte Zeichnungsoberfläche](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art30.gif "AboutGdip02_Art30")  
  
## <a name="clipping-with-regions"></a>Clipping mit Bereichen  
 Regionen aus Pfaden konstruiert werden können, und Pfade können die Umrisse von Zeichenfolgen enthalten, damit Sie für das Clipping gegliederten Text verwenden können. Die folgende Abbildung zeigt eine Reihe von konzentrischen Ellipsen, die das Innere einer Textzeichenfolge zugeschnitten.  
  
 ![Eingeschränkte Zeichnungsoberfläche](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art31.gif "AboutGdip02_Art31")  
  
 Um Clipping zu zeichnen, erstellen Sie eine <xref:System.Drawing.Graphics> -Objekt, legen Sie seine <xref:System.Drawing.Graphics.Clip%2A> -Eigenschaft, und klicken Sie dann die Zeichnung Methoden, die gleichen aufgerufen <xref:System.Drawing.Graphics> Objekt:  
  
 [!code-csharp[LinesCurvesAndShapes#91](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [Linien, Kurven und Formen](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Verwenden von Bereichen](../../../../docs/framework/winforms/advanced/using-regions.md)

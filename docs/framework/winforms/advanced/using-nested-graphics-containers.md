---
title: Verwenden geschachtelter Grafikcontainer
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
- graphics [Windows Forms], nested containers
- graphics [Windows Forms], clipping
- graphics [Windows Forms], transformations in nested objects
ms.assetid: a0d9f178-43a4-4323-bb5a-d3e3f77ae6c1
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 512c8903611f025364a1af2cb6cbaaffc8d759eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="using-nested-graphics-containers"></a>Verwenden geschachtelter Grafikcontainer
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]stellt Container, die Sie verwenden können, vorübergehend zu ersetzen oder erweitern Teil des Zustands in einem <xref:System.Drawing.Graphics> Objekt. Erstellen Sie einen Container durch Aufrufen der <xref:System.Drawing.Graphics.BeginContainer%2A> Methode von einem <xref:System.Drawing.Graphics> Objekt. Sie können Aufrufen <xref:System.Drawing.Graphics.BeginContainer%2A> wiederholt, um geschachtelte Container zu bilden. Jeder Aufruf von <xref:System.Drawing.Graphics.BeginContainer%2A> muss mit einem Aufruf von gekoppelt werden <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
## <a name="transformations-in-nested-containers"></a>Transformationen in geschachtelten Containern  
 Das folgende Beispiel erstellt eine <xref:System.Drawing.Graphics> Objekt und einen Container innerhalb der <xref:System.Drawing.Graphics> Objekt. Die globale Transformation für das <xref:System.Drawing.Graphics> -Objekt ist eine Verschiebung 100 Einheiten in der X-Richtung und 80 Einheiten in der y-Richtung. Die globale Transformation des Containers ist eine 30 Grad drehen. Der Code führt den Aufruf `DrawRectangle(pen, -60, -30, 120, 60)` zweimal. Der erste Aufruf von <xref:System.Drawing.Graphics.DrawRectangle%2A> wird innerhalb des Containers; d. h. der Aufruf ist zwischen den Aufrufen <xref:System.Drawing.Graphics.BeginContainer%2A> und <xref:System.Drawing.Graphics.EndContainer%2A>. Der zweite Aufruf von <xref:System.Drawing.Graphics.DrawRectangle%2A> wird nach dem Aufruf von <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 Im vorangehenden Code innerhalb des Containers gezeichnete Rechteck zunächst durch die globale Transformation des Containers (Drehung), und klicken Sie dann durch die globale Transformation für transformiert die <xref:System.Drawing.Graphics> Objekt (Übersetzung). Das Rechteck gezeichnet von außerhalb des Containers wird nur durch die globale Transformation für transformiert die <xref:System.Drawing.Graphics> Objekt (Übersetzung). Die folgende Abbildung zeigt die zwei Rechtecken.  
  
 ![Geschachtelte Container](../../../../docs/framework/winforms/advanced/media/csnestedcontainers1.png "csnestedcontainers1")  
  
## <a name="clipping-in-nested-containers"></a>Clipping in geschachtelten Containern  
 Im folgende Beispiel wird veranschaulicht, wie geschachtelte Container Clippingbereiche zu behandeln. Der Code erstellt ein <xref:System.Drawing.Graphics> Objekt und einen Container innerhalb der <xref:System.Drawing.Graphics> Objekt. Der Ausschneidebereich der <xref:System.Drawing.Graphics> Objekt ist ein Rechteck, und der Ausschneidebereich des Containers ist eine Ellipse. Der Code führt die beiden Aufrufe von der <xref:System.Drawing.Graphics.DrawLine%2A> Methode. Der erste Aufruf von <xref:System.Drawing.Graphics.DrawLine%2A> befindet sich innerhalb der Container, und der zweite Aufruf von <xref:System.Drawing.Graphics.DrawLine%2A> außerhalb des Containers (nach dem Aufruf von <xref:System.Drawing.Graphics.EndContainer%2A>). Die erste Zeile ist durch die Schnittmenge der beiden Clipping Regionen abgeschnitten. Die zweite Zeile wird nur durch den rechteckigen Ausschneidebereich abgeschnitten der <xref:System.Drawing.Graphics> Objekt.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 Die folgende Abbildung zeigt die Zeilen abgeschnitten.  
  
 ![Geschachtelte Container](../../../../docs/framework/winforms/advanced/media/nestedcontainers2.png "nestedcontainers2")  
  
 Wie die beiden vorherigen Beispiele zeigen, sind die Transformationen und Regionen Clipping in geschachtelten Containern kumulativ. Wenn Sie die World-Transformationen des Containers festlegen und die <xref:System.Drawing.Graphics> -Objekt beide Transformationen gelten für Elemente, die von innerhalb des Containers gezeichnet. Die Transformation des Containers werden zuerst angewendet, und die Transformation für das <xref:System.Drawing.Graphics> Objekt angewendet. Wenn Sie die Regionen Clipping des Containers festlegen und die <xref:System.Drawing.Graphics> -Objekt, Elemente aus, die innerhalb des Containers werden durch die Schnittmenge von zwei Clipping Regionen abgeschnitten werden.  
  
## <a name="quality-settings-in-nested-containers"></a>Qualität Einstellungen in geschachtelten Containern  
 Qualität (<xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.TextRenderingHint%2A>, und Like) in geschachtelter Container sind nicht kumulativ; vielmehr die Einstellungen für die Qualität des Containers vorübergehend zu ersetzen die Qualität Einstellungen ein <xref:System.Drawing.Graphics> Objekt. Wenn Sie einen neuen Container erstellen, werden die Quality-Einstellungen für diesen Container auf Standardwerte festgelegt. Nehmen wir beispielsweise an, Sie haben eine <xref:System.Drawing.Graphics> Objekt mit Glättungsmodus <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. Wenn Sie einen Container erstellen, ist der Glättungsmodus innerhalb des Containers automatisch zum Standardmodus. Sie sind frei, um den Glättungsmodus des Containers festgelegt, und alle Elemente, die von innerhalb des Containers entsprechend dem von Ihnen festgelegten Modus gezeichnet werden. Elemente, die nach dem Aufruf von <xref:System.Drawing.Graphics.EndContainer%2A> gemäß den Glättungsmodus gezeichnet wird (<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>) wurde bereits vor dem Aufruf von <xref:System.Drawing.Graphics.BeginContainer%2A>.  
  
## <a name="several-layers-of-nested-containers"></a>Mehrere Ebenen geschachtelter Container  
 Sie sind nicht beschränkt auf einen Container in einem <xref:System.Drawing.Graphics> Objekt. Können Sie eine Sequenz von Containern erstellen und Sie können angeben, die globale Transformation, Ausschneidebereich und Qualität Einstellungen der einzelnen diese geschachtelten Container jeweils in den vorherigen geschachtelt. Wenn Sie eine Zeichnung Methode aus dem innersten Container aufrufen, werden die Transformationen in der Reihenfolge, mit dem innersten Container beginnt und endet mit dem äußersten Container angewendet werden. Elemente, die aus dem innersten Container gezeichnet werden durch die Schnittmenge aller Bereiche einer Clipping abgeschnitten.  
  
 Das folgende Beispiel erstellt eine <xref:System.Drawing.Graphics> -Objekt und legt dessen Text renderinghinweis auf <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. Der Code erstellt zwei Container, in einer anderen geschachtelten. Der Text-Rendering-Hinweis des äußeren Containers wird festgelegt, um <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>, und der Text-renderinghinweis auf die inneren Container festgelegt ist <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. Der Code zeichnet drei Zeichenfolgen: aus dem inneren Container, eine aus dem äußeren Container und eine aus der <xref:System.Drawing.Graphics> Objekt selbst.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 Die folgende Abbildung zeigt die drei Zeichenfolgen. Die Zeichenfolgen, die gezeichnet wird, aus dem inneren Container und die <xref:System.Drawing.Graphics> Objekt durch Antialiasing geglättet werden. Die Zeichenfolge, die von der äußeren Containers gezeichnet wird nicht durch Antialiasing geglättet, da die <xref:System.Drawing.Graphics.TextRenderingHint%2A> -Eigenschaftensatz auf <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>.  
  
 ![Geschachtelte Container](../../../../docs/framework/winforms/advanced/media/nestedcontainers3.png "nestedcontainers3")  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Graphics>  
 [Verwalten des Zustands eines Graphics-Objekts](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)

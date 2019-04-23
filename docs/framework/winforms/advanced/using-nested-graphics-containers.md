---
title: Verwenden geschachtelter Grafikcontainer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], nested containers
- graphics [Windows Forms], clipping
- graphics [Windows Forms], transformations in nested objects
ms.assetid: a0d9f178-43a4-4323-bb5a-d3e3f77ae6c1
ms.openlocfilehash: 6bbf7918ccff184e597204b35aa005ab17d8d8af
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104298"
---
# <a name="using-nested-graphics-containers"></a>Verwenden geschachtelter Grafikcontainer
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] enthält der Container, die Sie verwenden können, um vorübergehend zu ersetzen oder erweitern Teil des Zustands in einer <xref:System.Drawing.Graphics> Objekt. Sie erstellen einen Container durch Aufrufen der <xref:System.Drawing.Graphics.BeginContainer%2A> Methode eine <xref:System.Drawing.Graphics> Objekt. Rufen Sie <xref:System.Drawing.Graphics.BeginContainer%2A> wiederholt, um geschachtelte Container zu erstellen. Jeder Aufruf von <xref:System.Drawing.Graphics.BeginContainer%2A> muss mit einem Aufruf von kombiniert werden <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
## <a name="transformations-in-nested-containers"></a>Transformationen in geschachtelten Containern  
 Das folgende Beispiel erstellt eine <xref:System.Drawing.Graphics> Objekt und einen Container innerhalb der <xref:System.Drawing.Graphics> Objekt. Die globale Transformation für das <xref:System.Drawing.Graphics> Objekt ist ein Übersetzungseinheiten 100 in X-Richtung und 80 Einheiten in der y-Richtung. Die globale Transformation des Containers ist eine 30-Grad-Drehung. Der Code führt den Aufruf `DrawRectangle(pen, -60, -30, 120, 60)` zweimal. Der erste Aufruf <xref:System.Drawing.Graphics.DrawRectangle%2A> innerhalb des Containers; ist der Aufruf wird zwischen den Aufrufen <xref:System.Drawing.Graphics.BeginContainer%2A> und <xref:System.Drawing.Graphics.EndContainer%2A>. Der zweite Aufruf von <xref:System.Drawing.Graphics.DrawRectangle%2A> wird nach dem Aufruf von <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 Im vorangehenden Code innerhalb des Containers gezeichnete Rechteck zunächst nach der globalen Transformation des Containers (Drehung) und dann durch die globale Transformation transformiert die <xref:System.Drawing.Graphics> Objekt (Translation). Außerhalb des Containers gezeichnete Rechteck transformiert wird, nur durch die globale Transformation für das <xref:System.Drawing.Graphics> Objekt (Translation). Die folgende Abbildung zeigt die beiden Rechtecke: 
  
 ![Abbildung der geschachtelte Container.](./media/using-nested-graphics-containers/nested-containers-illustration.png)  
  
## <a name="clipping-in-nested-containers"></a>Clipping in verschachtelten Containern  
 Im folgende Beispiel wird veranschaulicht, wie geschachtelte Container Ausschneidebereiche behandeln. Der Code erstellt eine <xref:System.Drawing.Graphics> Objekt und einen Container innerhalb der <xref:System.Drawing.Graphics> Objekt. Der Ausschneidebereich der <xref:System.Drawing.Graphics> Objekt ist ein Rechteck, und der Ausschneidebereich des Containers ist eine Ellipse. Der Code werden zwei Aufrufe der <xref:System.Drawing.Graphics.DrawLine%2A> Methode. Der erste Aufruf <xref:System.Drawing.Graphics.DrawLine%2A> befindet sich innerhalb des Containers und der zweite Aufruf von <xref:System.Drawing.Graphics.DrawLine%2A> außerhalb des Containers (nach dem Aufruf von <xref:System.Drawing.Graphics.EndContainer%2A>). Die erste Zeile wird durch die Schnittmenge der beiden Ausschneidebereiche abgeschnitten. In der zweite Zeile wird abgeschnitten, nur durch den rechteckigen Ausschneidebereich der <xref:System.Drawing.Graphics> Objekt.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 Die folgende Abbildung zeigt die beiden abgeschnittenen Zeilen:
  
 ![Abbildung der einen geschachtelten Container mit abgeschnittenen Zeilen.](./media/using-nested-graphics-containers/nested-container-clipped-lines.png)  
  
 Wie die beiden vorherigen Beispiele zeigen, sind Transformationen und Ausschneidebereiche kumulative in verschachtelten Containern. Wenn Sie die globalen Transformationen des Containers festlegen und die <xref:System.Drawing.Graphics> Objekt, beide Transformationen gelten für Elemente, die von innerhalb des Containers gezeichnet. Die Transformation des Containers werden zuerst und die Transformation die <xref:System.Drawing.Graphics> Objekt angewendet. Wenn Sie festlegen, dass die Ausschneidebereiche des Containers und der <xref:System.Drawing.Graphics> Objekt, Elemente aus, die innerhalb des Containers werden durch die Schnittmenge der beiden Ausschneidebereiche abgeschnitten werden.  
  
## <a name="quality-settings-in-nested-containers"></a>Einstellungen für die Qualität in verschachtelten Containern  
 Einstellungen von Quality (<xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.TextRenderingHint%2A>, usw.) in geschachtelte Container sind nicht kumulativ; vielmehr die Einstellungen der Qualität des Containers vorübergehend ersetzen Sie die Qualität Einstellungen von einer <xref:System.Drawing.Graphics> Objekt. Wenn Sie einen neuen Container erstellen, werden die Qualität-Einstellungen für diesen Container auf Standardwerte festgelegt. Nehmen wir beispielsweise an, Sie haben eine <xref:System.Drawing.Graphics> Objekt mit Glättungsmodus <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. Wenn Sie einen Container erstellen, ist der Glättungsmodus innerhalb des Containers automatisch zum Modus. Sie können den Glättungsmodus des Containers festgelegt, und alle Elemente innerhalb des Containers entnommen werden entsprechend dem festgelegten Modus gezeichnet werden. Elemente, die nach dem Aufruf von <xref:System.Drawing.Graphics.EndContainer%2A> wird gezeichnet werden, die der Glättungsmodus (<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>) war vor dem Aufruf von <xref:System.Drawing.Graphics.BeginContainer%2A>.  
  
## <a name="several-layers-of-nested-containers"></a>Mehrere Ebenen geschachtelter Container  
 Sie sind nicht beschränkt auf einen Container in einem <xref:System.Drawing.Graphics> Objekt. Können Sie eine Sequenz von Containern erstellen, jeweils in der vorherigen geschachtelt sind und Sie können angeben, die globale Transformation Ausschneidebereich und Einstellungen für die Qualität der einzelnen dieser geschachtelten Container. Wenn Sie eine Zeichenmethode aus dem innersten Container aufrufen, werden die Transformationen in der Reihenfolge, mit dem innersten Container beginnt und endet mit dem äußersten Container angewendet werden. Elemente, die von dem innersten Container gezeichnet werden durch die Schnittmenge aller Clipping Regionen abgeschnitten.  
  
 Das folgende Beispiel erstellt eine <xref:System.Drawing.Graphics> Objekt und seine Text-Rendering-Hinweis auf <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. Der Code erstellt zwei Container, in einer anderen geschachtelten. Der Text-Rendering-Hinweis des äußeren Containers nastaven NA hodnotu <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>, und der Text-Rendering-Hinweis für den inneren Container nastaven NA hodnotu <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. Der Code zeichnet drei Zeichenfolgen: eine aus dem inneren Container aus dem äußeren Container und einen aus der <xref:System.Drawing.Graphics> Objekt selbst.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 Die folgende Abbildung zeigt die drei Zeichenfolgen. Die Zeichenfolgen, die gezeichnet wird, aus dem inneren Container und die <xref:System.Drawing.Graphics> Objekt durch Antialiasing geglättet werden. Die Zeichenfolge aus dem äußeren Container wird nicht durch Antialiasing geglättet, da die <xref:System.Drawing.Graphics.TextRenderingHint%2A> -Eigenschaftensatz auf <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>.  
  
 ![Abbildung der Zeichenfolgen von geschachtelten Containern gezeichnet werden.](./media/using-nested-graphics-containers/nested-containers-three-strings.png)  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Graphics>
- [Verwalten des Zustands eines Graphics-Objekts](managing-the-state-of-a-graphics-object.md)

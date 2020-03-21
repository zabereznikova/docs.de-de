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
ms.openlocfilehash: 460ebb37ee62691a1e282f756840121fd378ebd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182462"
---
# <a name="using-nested-graphics-containers"></a>Verwenden geschachtelter Grafikcontainer
GDI+ stellt Container bereit, mit denen Sie einen Teil <xref:System.Drawing.Graphics> des Zustands in einem Objekt vorübergehend ersetzen oder erweitern können. Sie erstellen einen Container, indem Sie die <xref:System.Drawing.Graphics.BeginContainer%2A> Methode eines <xref:System.Drawing.Graphics> Objekts aufrufen. Sie können <xref:System.Drawing.Graphics.BeginContainer%2A> wiederholt aufrufen, verschachtelte Container zu bilden. Jeder Aufruf <xref:System.Drawing.Graphics.BeginContainer%2A> an muss mit <xref:System.Drawing.Graphics.EndContainer%2A>einem Aufruf von gekoppelt werden.  
  
## <a name="transformations-in-nested-containers"></a>Transformationen in verschachtelten Containern  
 Im folgenden Beispiel <xref:System.Drawing.Graphics> werden ein Objekt <xref:System.Drawing.Graphics> und ein Container innerhalb dieses Objekts erstellt. Die Welttransformation <xref:System.Drawing.Graphics> des Objekts ist eine Übersetzung 100 Einheiten in x-Richtung und 80 Einheiten in y-Richtung. Die Weltumwandlung des Containers ist eine 30-Grad-Rotation. Der Code führt `DrawRectangle(pen, -60, -30, 120, 60)` den Anruf zweimal aus. Der erste <xref:System.Drawing.Graphics.DrawRectangle%2A> Aufruf befindet sich im Container. d. h., der Anruf <xref:System.Drawing.Graphics.BeginContainer%2A> befindet <xref:System.Drawing.Graphics.EndContainer%2A>sich zwischen den Anrufen von und . Der zweite <xref:System.Drawing.Graphics.DrawRectangle%2A> Aufruf ist nach <xref:System.Drawing.Graphics.EndContainer%2A>dem Aufruf von .  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 Im vorhergehenden Code wird das rechteckige Rechteck, das aus dem Inneren des Containers gezeichnet wird, zuerst durch die Welttransformation des Containers (Rotation) und dann durch die Welttransformation des <xref:System.Drawing.Graphics> Objekts (Übersetzung) transformiert. Das von außerhalb des Containers gezeichnete Rechteck <xref:System.Drawing.Graphics> wird nur durch die Welttransformation des Objekts (Übersetzung) transformiert. Die folgende Abbildung zeigt die beiden Rechtecke:
  
 ![Abbildung, die verschachtelte Container zeigt.](./media/using-nested-graphics-containers/nested-containers-illustration.png)  
  
## <a name="clipping-in-nested-containers"></a>Clipping in verschachtelten Containern  
 Im folgenden Beispiel wird veranschaulicht, wie verschachtelte Container Clipping-Bereiche verarbeiten. Der Code <xref:System.Drawing.Graphics> erstellt ein Objekt <xref:System.Drawing.Graphics> und einen Container innerhalb dieses Objekts. Der Schnittbereich des <xref:System.Drawing.Graphics> Objekts ist ein Rechteck, und der Schnittbereich des Containers ist eine Ellipse. Der Code führt zwei <xref:System.Drawing.Graphics.DrawLine%2A> Aufrufe der Methode aus. Der erste <xref:System.Drawing.Graphics.DrawLine%2A> Aufruf befindet sich innerhalb des <xref:System.Drawing.Graphics.DrawLine%2A> Containers, und der zweite <xref:System.Drawing.Graphics.EndContainer%2A>Aufruf befindet sich außerhalb des Containers (nach dem Aufruf von ). Die erste Zeile wird durch den Schnittpunkt der beiden Schnittbereiche abgeschnitten. Die zweite Zeile wird nur durch den rechteckigen Schnittbereich des <xref:System.Drawing.Graphics> Objekts abgeschnitten.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 Die folgende Abbildung zeigt die beiden abgeschnittenen Linien:
  
 ![Abbildung, die einen verschachtelten Container mit abgeschnittenen Linien zeigt.](./media/using-nested-graphics-containers/nested-container-clipped-lines.png)  
  
 Wie die beiden vorhergehenden Beispiele zeigen, sind Transformationen und Zuschneidebereiche in verschachtelten Containern kumulativ. Wenn Sie die Welttransformationen des <xref:System.Drawing.Graphics> Containers und des Objekts festlegen, gelten beide Transformationen für Elemente, die aus dem Container stammen. Die Transformation des Containers wird zuerst angewendet, <xref:System.Drawing.Graphics> und die Transformation des Objekts wird an zweiter Stelle angewendet. Wenn Sie die Zuschneidebereiche des <xref:System.Drawing.Graphics> Containers und des Objekts festlegen, werden Elemente, die aus dem Container gezeichnet werden, durch den Schnittpunkt der beiden Clipping-Bereiche abgeschnitten.  
  
## <a name="quality-settings-in-nested-containers"></a>Qualitätseinstellungen in verschachtelten Containern  
 Qualitätseinstellungen<xref:System.Drawing.Graphics.SmoothingMode%2A>( <xref:System.Drawing.Graphics.TextRenderingHint%2A>, und dergleichen) in verschachtelten Containern sind nicht kumulativ. Vielmehr ersetzen die Qualitätseinstellungen des Containers vorübergehend <xref:System.Drawing.Graphics> die Qualitätseinstellungen eines Objekts. Wenn Sie einen neuen Container erstellen, werden die Qualitätseinstellungen für diesen Container auf Standardwerte festgelegt. Angenommen, Sie haben <xref:System.Drawing.Graphics> ein Objekt mit dem <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>Glättungsmodus von . Wenn Sie einen Container erstellen, ist der Glättungsmodus innerhalb des Containers der Standardglättungsmodus. Sie können den Glättungsmodus des Containers festlegen, und alle Elemente, die aus dem Container gezogen werden, werden entsprechend dem von Ihnen festgelegten Modus gezeichnet. Elemente, die nach <xref:System.Drawing.Graphics.EndContainer%2A> dem Aufruf gezeichnet wurden,<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>werden entsprechend dem Glättungsmodus ( ) gezeichnet, der vor dem Aufruf von <xref:System.Drawing.Graphics.BeginContainer%2A>vorhanden war.  
  
## <a name="several-layers-of-nested-containers"></a>Mehrere Schichten verschachtelter Container  
 Sie sind nicht auf einen <xref:System.Drawing.Graphics> Container in einem Objekt beschränkt. Sie können eine Sequenz von Containern erstellen, die jeweils in den vorherigen Containern geschachtelt sind, und Sie können die Welttransformation, den Schnittbereich und die Qualitätseinstellungen der einzelnen verschachtelten Container angeben. Wenn Sie eine Zeichnungsmethode innerhalb des innersten Containers aufrufen, werden die Transformationen in der Reihenfolge angewendet, beginnend mit dem innersten Container und endend mit dem äußersten Container. Elemente, die aus dem innersten Container gezeichnet werden, werden durch den Schnittpunkt aller Clipping-Bereiche abgeschnitten.  
  
 Im folgenden Beispiel <xref:System.Drawing.Graphics> wird ein Objekt erstellt <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>und der Textrenderinghinweis auf festgelegt. Der Code erstellt zwei Container, von dem einer in dem anderen verschachtelt ist. Der Textrendering-Hinweis des äußeren <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>Containers ist auf festgelegt, und der <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>Textrendering-Hinweis des inneren Containers ist auf festgelegt. Der Code zeichnet drei Zeichenfolgen: eine aus dem inneren Container, <xref:System.Drawing.Graphics> eine aus dem äußeren Container und eine aus dem Objekt selbst.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 Die folgende Abbildung zeigt die drei Zeichenfolgen. Die Auszüge aus dem inneren <xref:System.Drawing.Graphics> Behälter und aus dem Objekt werden durch Antialiasing geglättet. Die vom äußeren Container gezeichnete Zeichenfolge wird nicht <xref:System.Drawing.Graphics.TextRenderingHint%2A> durch Antialiasing geglättet, da die Eigenschaft auf <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>festgelegt ist.  
  
 ![Abbildung, die die Zeichenfolgen zeigt, die aus verschachtelten Containern gezeichnet werden.](./media/using-nested-graphics-containers/nested-containers-three-strings.png)  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Drawing.Graphics>
- [Verwalten des Zustands eines Graphics-Objekts](managing-the-state-of-a-graphics-object.md)

---
title: 'Gewusst wie: Rendern eines visuellen Stilelements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- visual themes [Windows Forms], applying to elements of Windows Forms applications
- professional appearance [Windows Forms], applying to elements of Windows Forms applications
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: a207781b-1baa-4ce9-b788-1e951bd4b5df
ms.openlocfilehash: 284fca2d3f2b8f47b60e4d9c639df4a6bd43c701
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537617"
---
# <a name="how-to-render-a-visual-style-element"></a>Gewusst wie: Rendern eines visuellen Stilelements
Die <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> Namespace macht <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> Objekte, die die Windows-Benutzer darstellen Benutzeroberflächenelemente (UI) von visuelle Stile unterstützt. In diesem Thema veranschaulicht, wie die <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> Klasse zum Rendern der <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> darstellt, die die **Abmelden** und **Herunterfahren** Schaltflächen im Startmenü.  
  
### <a name="to-render-a-visual-style-element"></a>Zum Rendern eines visuellen Stilelements  
  
1.  Erstellen einer <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> und legen Sie es auf das Element gezeichnet werden sollen. Beachten Sie die Verwendung der <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> Eigenschaft und die <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> Methode; die <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> Konstruktors löst eine Ausnahme aus, wenn visuelle Stile deaktiviert sind oder ein Element nicht definiert ist.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#4)]  
  
2.  Rufen Sie die <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> Methode, um dem Element zu rendern, die die <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> darstellt.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#6)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein benutzerdefiniertes Steuerelement abgeleitet aus dem <xref:System.Windows.Forms.Control> Klasse.  
  
-   Ein <xref:System.Windows.Forms.Form> , die das benutzerdefinierte Steuerelement hostet.  
  
-   Verweise auf die <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, und <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> Namespaces.  
  
## <a name="see-also"></a>Siehe auch  
 [Rendering von Steuerelementen mit visuellen Stilen](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)

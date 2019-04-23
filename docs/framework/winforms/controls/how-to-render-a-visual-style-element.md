---
title: 'Vorgehensweise: Rendern eines visuellen Stilelements'
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
ms.openlocfilehash: 57c2bc5722f77338225d70b514345344211656dc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59312396"
---
# <a name="how-to-render-a-visual-style-element"></a>Vorgehensweise: Rendern eines visuellen Stilelements
Die <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> Namespace weist <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> den Windows-Benutzer darstellende – Objekte Schnittstellenelemente (UI) von visuellen Stilen unterstützt. In diesem Thema wird veranschaulicht, wie Sie mit der <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> -Klasse zum Rendern der <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> darstellt, die die **Abmelden** und **Herunterfahren** Schaltflächen des Startmenüs auf.  
  
### <a name="to-render-a-visual-style-element"></a>Um ein visuelles Stilelement zu rendern.  
  
1. Erstellen Sie eine <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> und legen Sie es auf das Element, das Sie zeichnen möchten. Beachten Sie die Verwendung der <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> Eigenschaft und die <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> Methode; die <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> Konstruktor wird eine Ausnahme ausgelöst, wenn visuelle Stile deaktiviert sind, oder ein Element nicht definiert ist.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#4)]  
  
2. Rufen Sie die <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> Methode, um dem Element gerendert werden, die die <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> darstellt.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#6)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein benutzerdefiniertes Steuerelement abgeleitet wird, aus der <xref:System.Windows.Forms.Control> Klasse.  
  
-   Ein <xref:System.Windows.Forms.Form> , die das benutzerdefinierte Steuerelement hostet.  
  
-   Verweise auf die <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, und <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> Namespaces.  
  
## <a name="see-also"></a>Siehe auch

- [Rendering von Steuerelementen mit visuellen Stilen](rendering-controls-with-visual-styles.md)

---
title: 'Vorgehensweise: Verwenden einer Steuerelementwiedergabeklasse'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- visual themes [Windows Forms], applying to Windows Forms controls
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
ms.openlocfilehash: a0f450ff5f169026007002a0d2907ee35e79b29d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630552"
---
# <a name="how-to-use-a-control-rendering-class"></a>Vorgehensweise: Verwenden einer Steuerelementwiedergabeklasse
In diesem Beispiel wird veranschaulicht, wie die <xref:System.Windows.Forms.ComboBoxRenderer> Klasse auf den Dropdownpfeil neben einem Kombinationsfeld-Steuerelement zu rendern. Das Beispiel besteht aus den <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode der ein einfaches benutzerdefiniertes Steuerelement. Die <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> Eigenschaft wird verwendet, um zu bestimmen, ob visuelle Stile im Clientbereich von Anwendungsfenstern aktiviert sind. Wenn visuelle Stile aktiviert sind, gibt die <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> Methode rendert den Dropdown-Pfeil mit visuellen Stilen; andernfalls der <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> Methode rendert den Dropdown-Pfeil in der klassischen Windows-Stil.  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Ein benutzerdefiniertes Steuerelement abgeleitet wird, aus der <xref:System.Windows.Forms.Control> Klasse.  
  
- Ein <xref:System.Windows.Forms.Form> , die das benutzerdefinierte Steuerelement hostet.  
  
- Verweise auf die <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, und <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> Namespaces.  
  
## <a name="see-also"></a>Siehe auch

- [Rendering von Steuerelementen mit visuellen Stilen](rendering-controls-with-visual-styles.md)

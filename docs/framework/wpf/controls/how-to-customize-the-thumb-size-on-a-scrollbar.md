---
title: 'Vorgehensweise: Anpassen der Größe des Ziehpunkts auf einer Bildlaufleiste'
ms.date: 03/30/2017
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
ms.openlocfilehash: 30fc72e3f0631b01777bf058c7a7470cc376a547
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354322"
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a>Vorgehensweise: Anpassen der Größe des Ziehpunkts auf einer Bildlaufleiste
In diesem Thema erläutert das Einrichten der <xref:System.Windows.Controls.Primitives.Thumb> von eine <xref:System.Windows.Controls.Primitives.ScrollBar> eine feste Größe und eine Mindestgröße für angeben der <xref:System.Windows.Controls.Primitives.Thumb> von eine <xref:System.Windows.Controls.Primitives.ScrollBar>.  
  
## <a name="example"></a>Beispiel  
  
## <a name="description"></a>Beschreibung  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Primitives.ScrollBar> , bei dem ein <xref:System.Windows.Controls.Primitives.Thumb> mit fester Größe. Im Beispiel wird die <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> Eigenschaft der <xref:System.Windows.Controls.Primitives.Thumb> zu <xref:System.Double.NaN> und legt die Höhe des der <xref:System.Windows.Controls.Primitives.Thumb>.  Zum Erstellen einer horizontalen <xref:System.Windows.Controls.Primitives.ScrollBar> mit einer <xref:System.Windows.Controls.Primitives.Thumb> , der eine feste Breite hat, legen Sie die Breite der <xref:System.Windows.Controls.Primitives.Thumb>.  
  
## <a name="code"></a>Code  
 [!code-xaml[ScrollBarCustomThumbSize#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a>Beschreibung  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Primitives.ScrollBar> , bei dem ein <xref:System.Windows.Controls.Primitives.Thumb> mit einer Mindestgröße. Im Beispiel wird den Wert des <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>. Zum Erstellen einer horizontalen <xref:System.Windows.Controls.Primitives.ScrollBar> mit einem <xref:System.Windows.Controls.Primitives.Thumb> , die eine minimale Breite hat, legen Sie die <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.  
  
## <a name="code"></a>Code  
 [!code-xaml[ScrollBarCustomThumbSize#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a>Siehe auch
- [ScrollBar-Stile und -Vorlagen](scrollbar-styles-and-templates.md)

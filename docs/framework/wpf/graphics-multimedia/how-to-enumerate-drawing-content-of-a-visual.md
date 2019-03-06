---
title: 'Vorgehensweise: Auflisten des Zeichnungsinhalts eines visuellen Objekts'
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 6414026090766544585c8e5e940ef9f0c62566d2
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360010"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a>Vorgehensweise: Auflisten des Zeichnungsinhalts eines visuellen Objekts
Die <xref:System.Windows.Media.Drawing> Objekt stellt ein Objektmodell bereit, für das Auflisten des Inhalts einer <xref:System.Windows.Media.Visual>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> Methode zum Abrufen der <xref:System.Windows.Media.DrawingGroup> Wert eine <xref:System.Windows.Media.Visual> zählt Sie ihn.  
  
> [!NOTE]
>  Wenn Sie den Inhalt des visuellen Objekts auflisten, rufen Sie <xref:System.Windows.Media.Drawing> Objekte und nicht die zugrunde liegende Darstellung der Renderingdaten als Anweisungsliste für Vektorgrafiken. Weitere Informationen finden Sie unter [Übersicht über das WPF-Grafikenrendering](wpf-graphics-rendering-overview.md).  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.VisualTreeHelper>
- [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md)
- [Übersicht über das WPF-Grafikrendering](wpf-graphics-rendering-overview.md)

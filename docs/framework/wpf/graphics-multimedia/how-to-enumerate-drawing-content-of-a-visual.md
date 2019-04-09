---
title: 'Vorgehensweise: Auflisten des Zeichnungsinhalts eines visuellen Objekts'
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 4f0afc1075fe66c7f154fcef3cd883709db55316
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108003"
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

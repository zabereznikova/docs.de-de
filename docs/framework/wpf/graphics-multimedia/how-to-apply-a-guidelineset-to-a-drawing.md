---
title: 'Vorgehensweise: Anwenden eines Führungsliniensatzes auf eine Zeichnung'
ms.date: 03/30/2017
helpviewer_keywords:
- GuidelineSet property [WPF], applying to drawings
- graphics [WPF], GuidelineSet property
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
ms.openlocfilehash: 4bd2ee349f2c1855a9af6b4c00f2630cd50a9108
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493377"
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a>Vorgehensweise: Anwenden eines Führungsliniensatzes auf eine Zeichnung
Dieses Beispiel veranschaulicht das Anwenden einer <xref:System.Windows.Media.GuidelineSet> auf eine <xref:System.Windows.Media.DrawingGroup>.  
  
 Die <xref:System.Windows.Media.DrawingGroup> Klasse ist die einzige Art von <xref:System.Windows.Media.Drawing> , bei dem ein <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> Eigenschaft. Anzuwendende eine <xref:System.Windows.Media.GuidelineSet> in einen anderen Typ von <xref:System.Windows.Media.Drawing>, Hinzufügen einer <xref:System.Windows.Media.DrawingGroup> und wenden Sie dann die <xref:System.Windows.Media.GuidelineSet> auf Ihre <xref:System.Windows.Media.DrawingGroup>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt zwei <xref:System.Windows.Media.DrawingGroup> Objekte, die sind nahezu identisch; der einzige Unterschied besteht: zweiten <xref:System.Windows.Media.DrawingGroup> hat eine <xref:System.Windows.Media.GuidelineSet> und nicht für die erste.  
  
 Die folgende Abbildung zeigt die Ausgabe des Beispiels. Da das Rendern zu den Unterschieden zwischen den beiden <xref:System.Windows.Media.DrawingGroup> Objekte nur sehr schwer, Teile der Zeichnung vergrößert werden.  
  
 ![Eine DrawingGroup mit und ohne ein GuidelineSet](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "Graphicsmm_drawinggroup_guidelineset")  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.GuidelineSet>
- [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)

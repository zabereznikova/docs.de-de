---
title: 'Vorgehensweise: Anwenden eines Führungsliniensatzes auf eine Zeichnung'
ms.date: 03/30/2017
helpviewer_keywords:
- GuidelineSet property [WPF], applying to drawings
- graphics [WPF], GuidelineSet property
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
ms.openlocfilehash: 134236c5beca806b747d45f20764cc82ddd8a4e8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699054"
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a>Vorgehensweise: Anwenden eines Führungsliniensatzes auf eine Zeichnung
Dieses Beispiel veranschaulicht das Anwenden einer <xref:System.Windows.Media.GuidelineSet> auf eine <xref:System.Windows.Media.DrawingGroup>.  
  
 Die <xref:System.Windows.Media.DrawingGroup> Klasse ist die einzige Art von <xref:System.Windows.Media.Drawing> , bei dem ein <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> Eigenschaft. Anzuwendende eine <xref:System.Windows.Media.GuidelineSet> in einen anderen Typ von <xref:System.Windows.Media.Drawing>, Hinzufügen einer <xref:System.Windows.Media.DrawingGroup> und wenden Sie dann die <xref:System.Windows.Media.GuidelineSet> auf Ihre <xref:System.Windows.Media.DrawingGroup>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt zwei <xref:System.Windows.Media.DrawingGroup> Objekte, die sind nahezu identisch; der einzige Unterschied besteht: zweiten <xref:System.Windows.Media.DrawingGroup> hat eine <xref:System.Windows.Media.GuidelineSet> und nicht für die erste.  
  
 Die folgende Abbildung zeigt die Ausgabe des Beispiels. Da das Rendern zu den Unterschieden zwischen den beiden <xref:System.Windows.Media.DrawingGroup> Objekte nur sehr schwer, Teile der Zeichnung vergrößert werden.  
  
 ![Eine DrawingGroup mit und ohne ein GuidelineSet](./media/graphicsmm-drawinggroup-guidelineset.png "Graphicsmm_drawinggroup_guidelineset")  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.GuidelineSet>
- [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md)

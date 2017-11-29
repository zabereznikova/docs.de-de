---
title: "Gewusst wie: Anwenden eines Führungsliniensatzes auf eine Zeichnung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GuidelineSet property [WPF], applying to drawings
- graphics [WPF], GuidelineSet property
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dd8d93d128c03cb9ee482860603e5734e96c6fc2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a>Gewusst wie: Anwenden eines Führungsliniensatzes auf eine Zeichnung
In diesem Beispiel wird gezeigt, wie zum Anwenden einer <xref:System.Windows.Media.GuidelineSet> auf eine <xref:System.Windows.Media.DrawingGroup>.  
  
 Die <xref:System.Windows.Media.DrawingGroup> Klasse ist der einzige Typ von <xref:System.Windows.Media.Drawing> , besitzt eine <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> Eigenschaft. Anwenden einer <xref:System.Windows.Media.GuidelineSet> in einen anderen Typ von <xref:System.Windows.Media.Drawing>, fügen Sie diese eine <xref:System.Windows.Media.DrawingGroup> und wenden Sie dann die <xref:System.Windows.Media.GuidelineSet> zu Ihrer <xref:System.Windows.Media.DrawingGroup>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt zwei <xref:System.Windows.Media.DrawingGroup> Objekte, die sind nahezu identisch sind; der einzige Unterschied ist: das zweite <xref:System.Windows.Media.DrawingGroup> verfügt über eine <xref:System.Windows.Media.GuidelineSet> und das erste nicht.  
  
 Die folgende Abbildung zeigt die Ausgabe des Beispiels. Da das Rendering zu den Unterschieden zwischen den beiden <xref:System.Windows.Media.DrawingGroup> Objekte ist schwer erkennbare, Teile der Zeichnung vergrößert werden.  
  
 ![Eine DrawingGroup mit und ohne ein GuidelineSet](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "Graphicsmm_drawinggroup_guidelineset")  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.DrawingGroup>  
 <xref:System.Windows.Media.GuidelineSet>  
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)

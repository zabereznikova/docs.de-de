---
title: 'Gewusst wie: Auflisten des Zeichnungsinhalts eines visuellen Objekts'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5e498bc8e425198e479d7ce0b2328e0efa3ede70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a>Gewusst wie: Auflisten des Zeichnungsinhalts eines visuellen Objekts
Die <xref:System.Windows.Media.Drawing> Objekt enthalten ein Objektmodell zum Aufzählen der Inhalt von einem <xref:System.Windows.Media.Visual>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> Methode zum Abrufen der <xref:System.Windows.Media.DrawingGroup> Wert, der eine <xref:System.Windows.Media.Visual> und aufgelistet.  
  
> [!NOTE]
>  Wenn Sie den Inhalt des visuellen Elements auflisten, rufen Sie <xref:System.Windows.Media.Drawing> Objekte und nicht die zugrunde liegende Darstellung der Renderingdaten als Anweisungsliste für Vektor. Weitere Informationen finden Sie unter [Übersicht über das WPF-Grafikenrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Drawing>  
 <xref:System.Windows.Media.DrawingGroup>  
 <xref:System.Windows.Media.VisualTreeHelper>  
 [Übersicht über Zeichnungsobjekte](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Übersicht über das WPF-Grafikrendering](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)

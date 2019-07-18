---
title: 'Vorgehensweise: Positionieren von untergeordneten Elementen mithilfe der angefügten Eigenschaften von Canvas'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- attached properties [WPF Designer]
- Canvas control [WPF], attached properties
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
ms.openlocfilehash: 347c8502bd4c5fafcde7a142327f85bfb75b9954
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699070"
---
# <a name="how-to-use-the-attached-properties-of-canvas-to-position-child-elements"></a>Vorgehensweise: Positionieren von untergeordneten Elementen mithilfe der angefügten Eigenschaften von Canvas
Dieses Beispiel zeigt, wie Sie mit der angefügten Eigenschaften von <xref:System.Windows.Controls.Canvas> zum Positionieren der untergeordneten Elemente.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel fügt vier <xref:System.Windows.Controls.Button> -Elemente als untergeordnete Elemente eines übergeordneten Elements <xref:System.Windows.Controls.Canvas>. Jedes Element wird dargestellt, indem eine <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, und <xref:System.Windows.Controls.Canvas.Top%2A>.
Jede <xref:System.Windows.Controls.Button> befindet sich relativ zum übergeordneten <xref:System.Windows.Controls.Canvas> und entsprechend des zugeordneten Eigenschaftswerts.  
  
 [!code-cpp[CanvasAttachedProperties#1](~/samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.Canvas.Bottom%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- <xref:System.Windows.Controls.Canvas.Right%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Button>
- [Übersicht über Panel-Elemente](panels-overview.md)
- [Themen zu Vorgehensweisen](canvas-how-to-topics.md)
- [Übersicht über angefügte Eigenschaften](../advanced/attached-properties-overview.md)

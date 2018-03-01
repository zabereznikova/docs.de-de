---
title: 'Gewusst wie: Erstellen eines Elements von Grid'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], grid instance
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 30fdd89a46e5d2027e9c525b0ca8cfcfb1d11ed2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-grid-element"></a>Gewusst wie: Erstellen eines Elements von Grid
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie zum Erstellen und Verwenden einer Instanz von <xref:System.Windows.Controls.Grid> entweder [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] oder Code. In diesem Beispiel verwendet drei <xref:System.Windows.Controls.ColumnDefinition> Objekte und drei <xref:System.Windows.Controls.RowDefinition> Objekte, um ein Raster erstellen, das neun Zellen, z. B. in einem Arbeitsblatt. Jede Zelle enthält eine <xref:System.Windows.Controls.TextBlock> Element, das Daten sowie die oberste Zeile darstellt, enthält eine <xref:System.Windows.Controls.TextBlock> mit der <xref:System.Windows.Controls.Grid.ColumnSpan%2A> -Eigenschaft angewendet. Zum Anzeigen der Grenzen jeder Zelle der <xref:System.Windows.Controls.Grid.ShowGridLines%2A> -Eigenschaft aktiviert ist.  
  
 [!code-csharp[Grid#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xaml[Grid#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Grid>  
 [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)

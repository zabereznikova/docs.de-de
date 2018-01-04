---
title: 'Gewusst wie: Angeben einer benutzerdefinierten Popup-Position'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae10153f31b79a220b84cae7a6525eca0ce0bd9c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-a-custom-popup-position"></a>Gewusst wie: Angeben einer benutzerdefinierten Popup-Position
In diesem Beispiel wird gezeigt, wie eine benutzerdefinierte Position für an einer <xref:System.Windows.Controls.Primitives.Popup> steuern, wann die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.  
  
## <a name="example"></a>Beispiel  
 Wenn die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, die <xref:System.Windows.Controls.Primitives.Popup> Ruft eine definierte Instanz von der <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegieren. Dieser Delegat gibt einen Satz von möglichen Punkten, die relativ zu der oberen linken Ecke des Zielbereichs und der oberen linken Ecke des sind die <xref:System.Windows.Controls.Primitives.Popup>. Die <xref:System.Windows.Controls.Primitives.Popup> Platzierung tritt auf, an dem Punkt, der die beste Sichtbarkeit bereitstellt.  
  
 Das folgende Beispiel zeigt, wie die Position des definiert eine <xref:System.Windows.Controls.Primitives.Popup> durch Festlegen der <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Eigenschaft <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. Außerdem wird gezeigt, wie zum Erstellen und Zuweisen einer <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> Delegaten zum Positionieren der <xref:System.Windows.Controls.Primitives.Popup>.  Der Rückrufdelegat gibt zwei <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> Objekte.  Wenn die <xref:System.Windows.Controls.Primitives.Popup> verborgen ist, indem eine Bildschirmkante der erste Position der <xref:System.Windows.Controls.Primitives.Popup> an zweiter Stelle platziert wird.  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 Das vollständige Beispiel finden Sie unter [Popup-Platzierung Sample](http://go.microsoft.com/fwlink/?LinkID=160032).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [Übersicht über Popups](../../../../docs/framework/wpf/controls/popup-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)

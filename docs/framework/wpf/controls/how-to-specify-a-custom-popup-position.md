---
title: 'Gewusst wie: Angeben einer benutzerdefinierten Popup-Position'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: e6e81a6e0819ba3eb39a1c568e6872414e671544
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2018
ms.locfileid: "47235425"
---
# <a name="how-to-specify-a-custom-popup-position"></a>Gewusst wie: Angeben einer benutzerdefinierten Popup-Position
Dieses Beispiel zeigt, wie eine benutzerdefinierte Position für ein <xref:System.Windows.Controls.Primitives.Popup> steuern, wann die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.  
  
## <a name="example"></a>Beispiel  
 Wenn die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, <xref:System.Windows.Controls.Primitives.Popup> Ruft eine definierte Instanz von der <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegieren. Dieser Delegat gibt eine Reihe von möglichen Punkte, die relativ zu der oberen linken Ecke des Zielbereichs und der oberen linken Ecke des sind die <xref:System.Windows.Controls.Primitives.Popup>. Die <xref:System.Windows.Controls.Primitives.Popup> Platzierung tritt ein, an dem Punkt, der der besten Sichtbarkeit.  
  
 Das folgende Beispiel zeigt, wie Sie die Position des definieren eine <xref:System.Windows.Controls.Primitives.Popup> durch Festlegen der <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Eigenschaft <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. Darüber hinaus wird zum Erstellen und Zuweisen einer <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> Delegat zum Positionieren der <xref:System.Windows.Controls.Primitives.Popup>.  Gibt der Callback-Delegaten zurück, zwei <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> Objekte.  Wenn die <xref:System.Windows.Controls.Primitives.Popup> von einem Bildschirmrand bei der ersten Position wird ausgeblendet, die <xref:System.Windows.Controls.Primitives.Popup> an zweiter Stelle platziert.  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel](https://go.microsoft.com/fwlink/?LinkID=160032).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [Übersicht über Popups](../../../../docs/framework/wpf/controls/popup-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)

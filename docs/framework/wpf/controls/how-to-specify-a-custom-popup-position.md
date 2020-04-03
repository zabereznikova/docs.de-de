---
title: 'Gewusst wie: Angeben einer benutzerdefinierten Popup-Position'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: b48dedc044b418062642af5c5bb40afab78a3c97
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635751"
---
# <a name="how-to-specify-a-custom-popup-position"></a>Gewusst wie: Angeben einer benutzerdefinierten Popup-Position
In diesem Beispiel wird gezeigt, <xref:System.Windows.Controls.Primitives.Popup> wie Sie <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> eine benutzerdefinierte Position für ein Steuerelement angeben, wenn die Eigenschaft auf <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>festgelegt ist.  
  
## <a name="example"></a>Beispiel  
 Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> die Eigenschaft <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>auf <xref:System.Windows.Controls.Primitives.Popup> festgelegt ist, ruft <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> der eine definierte Instanz des Delegaten auf. Dieser Delegat gibt eine Reihe möglicher Punkte zurück, die relativ zur oberen linken <xref:System.Windows.Controls.Primitives.Popup>Ecke des Zielbereichs und der oberen linken Ecke des sind. Die <xref:System.Windows.Controls.Primitives.Popup> Platzierung erfolgt an dem Punkt, der die beste Sichtbarkeit bietet.  
  
 Das folgende Beispiel zeigt, wie <xref:System.Windows.Controls.Primitives.Popup> Sie die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Position <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>von a definieren, indem Sie die Eigenschaft auf festlegen. Außerdem wird gezeigt, wie <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> Sie einen Delegaten <xref:System.Windows.Controls.Primitives.Popup>erstellen und zuweisen, um die zu positionieren.  Der Rückrufseleger gibt zwei <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> Objekte zurück.  Wenn <xref:System.Windows.Controls.Primitives.Popup> der durch eine Bildschirmkante an der <xref:System.Windows.Controls.Primitives.Popup> ersten Position ausgeblendet wird, wird der an der zweiten Position platziert.  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 Das vollständige Beispiel finden Sie unter [Popup-Platzierungsbeispiel](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Primitives.Popup>
- [Popup-Übersicht](popup-overview.md)
- [How-to-Artikel](popup-how-to-topics.md)

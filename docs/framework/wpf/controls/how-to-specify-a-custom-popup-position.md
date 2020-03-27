---
title: 'Gewusst wie: Angeben einer benutzerdefinierten Popup-Position'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: ea8d73c51dd018608b95104f00bf341ff434225c
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344953"
---
# <a name="how-to-specify-a-custom-popup-position"></a>Gewusst wie: Angeben einer benutzerdefinierten Popup-Position
In diesem Beispiel wird gezeigt, <xref:System.Windows.Controls.Primitives.Popup> wie Sie <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> eine benutzerdefinierte Position für ein Steuerelement angeben, wenn die Eigenschaft auf <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>festgelegt ist.  
  
## <a name="example"></a>Beispiel  
 Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> die Eigenschaft <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>auf <xref:System.Windows.Controls.Primitives.Popup> festgelegt ist, ruft <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> der eine definierte Instanz des Delegaten auf. Dieser Delegat gibt eine Reihe möglicher Punkte zurück, die relativ zur oberen <xref:System.Windows.Controls.Primitives.Popup>linken Ecke des Zielbereichs und der oberen linken Ecke des sind. Die <xref:System.Windows.Controls.Primitives.Popup> Platzierung erfolgt an dem Punkt, der die beste Sichtbarkeit bietet.  
  
 Das folgende Beispiel zeigt, wie <xref:System.Windows.Controls.Primitives.Popup> Sie die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Position <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>von a definieren, indem Sie die Eigenschaft auf festlegen. Außerdem wird gezeigt, wie <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> Sie einen Delegaten <xref:System.Windows.Controls.Primitives.Popup>erstellen und zuweisen, um die zu positionieren.  Der Rückrufseleger gibt zwei <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> Objekte zurück.  Wenn <xref:System.Windows.Controls.Primitives.Popup> der durch eine Bildschirmkante an der <xref:System.Windows.Controls.Primitives.Popup> ersten Position ausgeblendet wird, wird der an der zweiten Position platziert.  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 Das vollständige Beispiel finden Sie unter [Popup-Platzierungsbeispiel](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Primitives.Popup>
- [Übersicht über Popups](popup-overview.md)
- [Gewusst wie-Themen](popup-how-to-topics.md)

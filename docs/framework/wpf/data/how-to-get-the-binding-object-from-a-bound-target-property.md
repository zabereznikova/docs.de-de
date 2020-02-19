---
title: 'Gewusst wie: Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: c528515124898c7deb6114e620ce21766123ab3c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453051"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a>Gewusst wie: Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft
Dieses Beispiel zeigt, wie das Bindungsobjekt aus einer datengebundenen Zieleigenschaft abgerufen wird.

## <a name="example"></a>Beispiel
 Sie können Folgendes ausführen, um das <xref:System.Windows.Data.Binding> Objekt zu erhalten:

 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]

> [!NOTE]
> Sie müssen die Abhängigkeitseigenschaft für die abzurufende Bindung angeben, da eventuell mehrere Eigenschaften des Zielobjekts die Datenbindung verwenden.

 Alternativ dazu können Sie den <xref:System.Windows.Data.BindingExpression> erhalten und dann den Wert der Eigenschaft <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> erhalten.

 Das vollständige Beispiel finden Sie unter [Beispiel für Bindungsvalidierung](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).

> [!NOTE]
> Wenn die Bindung eine <xref:System.Windows.Data.MultiBinding>ist, verwenden Sie <xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A?displayProperty=nameWithType>. Wenn es sich um einen <xref:System.Windows.Data.PriorityBinding>handelt, verwenden Sie <xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A?displayProperty=nameWithType>. Wenn Sie nicht sicher sind, ob die Ziel Eigenschaft über eine <xref:System.Windows.Data.Binding>, eine <xref:System.Windows.Data.MultiBinding>oder eine <xref:System.Windows.Data.PriorityBinding>gebunden ist, können Sie <xref:System.Windows.Data.BindingOperations.GetBindingBase%2A?displayProperty=nameWithType>verwenden.

## <a name="see-also"></a>Siehe auch

- [Erstellen einer Bindung in Code](how-to-create-a-binding-in-code.md)
- [How-to Topics (Themen zur Vorgehensweise)](data-binding-how-to-topics.md)

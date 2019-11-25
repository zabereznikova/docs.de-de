---
title: 'Gewusst wie: Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: cf2ddc93a7c46ee6956d2731a786289f64086360
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976425"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a>Gewusst wie: Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft
Dieses Beispiel zeigt, wie das Bindungsobjekt aus einer datengebundenen Zieleigenschaft abgerufen wird.

## <a name="example"></a>Beispiel
 Sie können Folgendes ausführen, um das <xref:System.Windows.Data.Binding> Objekt zu erhalten:

 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]

> [!NOTE]
> Sie müssen die Abhängigkeitseigenschaft für die abzurufende Bindung angeben, da eventuell mehrere Eigenschaften des Zielobjekts die Datenbindung verwenden.

 Alternativ dazu können Sie den <xref:System.Windows.Data.BindingExpression> erhalten und dann den Wert der Eigenschaft <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> erhalten.

 Das vollständige Beispiel finden Sie unter [Beispiel für Bindungsvalidierung](https://go.microsoft.com/fwlink/?LinkID=159972).

> [!NOTE]
> Wenn die Bindung eine <xref:System.Windows.Data.MultiBinding>ist, verwenden Sie <xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A?displayProperty=nameWithType>. Wenn es sich um einen <xref:System.Windows.Data.PriorityBinding>handelt, verwenden Sie <xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A?displayProperty=nameWithType>. Wenn Sie nicht sicher sind, ob die Ziel Eigenschaft über eine <xref:System.Windows.Data.Binding>, eine <xref:System.Windows.Data.MultiBinding>oder eine <xref:System.Windows.Data.PriorityBinding>gebunden ist, können Sie <xref:System.Windows.Data.BindingOperations.GetBindingBase%2A?displayProperty=nameWithType>verwenden.

## <a name="see-also"></a>Siehe auch

- [Erstellen einer Bindung in Code](how-to-create-a-binding-in-code.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)

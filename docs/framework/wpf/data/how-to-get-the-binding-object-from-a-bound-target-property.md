---
title: 'Gewusst wie: Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: 0bc793d4c95f8919517a83e434cf795e971dcd32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556730"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a>Gewusst wie: Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft
Dieses Beispiel zeigt, wie das Bindungsobjekt aus einer datengebundenen Zieleigenschaft abgerufen wird.  
  
## <a name="example"></a>Beispiel  
 Sie können Folgendes zum Abrufen der <xref:System.Windows.Data.Binding> Objekt:  
  
 [!code-csharp[BindValidation#GetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
>  Sie müssen die Abhängigkeitseigenschaft für die abzurufende Bindung angeben, da eventuell mehrere Eigenschaften des Zielobjekts die Datenbindung verwenden.  
  
 Alternativ können Sie Abrufen der <xref:System.Windows.Data.BindingExpression> und rufen Sie anschließend den Wert, der die <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> Eigenschaft.  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für Bindungsvalidierung](http://go.microsoft.com/fwlink/?LinkID=159972).  
  
> [!NOTE]
>  Wenn die Bindung ist eine <xref:System.Windows.Data.MultiBinding>, verwenden Sie <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>. Es ist ein <xref:System.Windows.Data.PriorityBinding>, verwenden Sie <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>. Wenn Sie unsicher sind, ob die Eigenschaft gebunden ist mit einem <xref:System.Windows.Data.Binding>, eine <xref:System.Windows.Data.MultiBinding>, oder ein <xref:System.Windows.Data.PriorityBinding>, können Sie <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen einer Bindung in Code](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

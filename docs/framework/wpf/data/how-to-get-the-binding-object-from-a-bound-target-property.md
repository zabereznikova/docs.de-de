---
title: 'Vorgehensweise: Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
ms.openlocfilehash: c7aacc2145ffe98ec7b58afb3b2e3dca151ef0ad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965437"
---
# <a name="how-to-get-the-binding-object-from-a-bound-target-property"></a>Vorgehensweise: Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft
Dieses Beispiel zeigt, wie das Bindungsobjekt aus einer datengebundenen Zieleigenschaft abgerufen wird.  
  
## <a name="example"></a>Beispiel  
 Zum erhalten des <xref:System.Windows.Data.Binding> -Objekts können Sie Folgendes ausführen:  
  
 [!code-csharp[BindValidation#GetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
> Sie müssen die Abhängigkeitseigenschaft für die abzurufende Bindung angeben, da eventuell mehrere Eigenschaften des Zielobjekts die Datenbindung verwenden.  
  
 Alternativ können Sie das <xref:System.Windows.Data.BindingExpression> - <xref:System.Windows.Data.BindingExpression.ParentBinding%2A> Objekt und dann den Wert der-Eigenschaft erhalten.  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für Bindungsvalidierung](https://go.microsoft.com/fwlink/?LinkID=159972).  
  
> [!NOTE]
> Wenn die Bindung eine <xref:System.Windows.Data.MultiBinding>ist, verwenden <xref:System.Windows.Data.BindingOperations>Sie.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A> Wenn es sich um <xref:System.Windows.Data.PriorityBinding>einen handelt <xref:System.Windows.Data.BindingOperations>,<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>verwenden Sie. Wenn Sie nicht sicher sind, ob die Ziel Eigenschaft mit einem <xref:System.Windows.Data.Binding>, einem <xref:System.Windows.Data.MultiBinding>oder einem <xref:System.Windows.Data.PriorityBinding>gebunden ist, können Sie <xref:System.Windows.Data.BindingOperations>verwenden<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen einer Bindung in Code](how-to-create-a-binding-in-code.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)

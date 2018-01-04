---
title: 'Gewusst wie: Abrufen des Bindungsobjekts aus einer gebundenen Zieleigenschaft'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], getting binding objects from bound target properties
- properties [WPF], getting binding objects from
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f5369bc770a31aa99f1fb11bfec790eb8fe091d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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

---
title: 'Gewusst wie: Binden der Eigenschaften von zwei Steuerelementen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ff3da19d33e747ec514de9cd24fa08ccd6ab13bd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>Gewusst wie: Binden der Eigenschaften von zwei Steuerelementen
In diesem Beispiel wird gezeigt, wie zum Binden der Eigenschaft des Steuerelements mit einem instanziierten an, die von einem anderen mithilfe der <xref:System.Windows.Data.Binding.ElementName%2A> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie binden die <xref:System.Windows.Controls.Panel.Background%2A> Eigenschaft eine <xref:System.Windows.Controls.Canvas> auf die <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft eine <xref:System.Windows.Controls.ComboBox>:  
  
 [!code-xaml[BindDptoDp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 Bei Rendern dieses Beispiels sieht es folgendermaßen aus:  
  
 ![Canvas mit grünem Hintergrund](../../../../docs/framework/wpf/data/media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")  
  
 **Hinweis** Bindungsziel-Eigenschaft (in diesem Beispiel wird die <xref:System.Windows.Controls.Panel.Background%2A> Eigenschaft) muss eine Abhängigkeitseigenschaft. Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Angeben der Bindungsquelle](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

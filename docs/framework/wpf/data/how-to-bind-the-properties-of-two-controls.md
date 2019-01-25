---
title: 'Vorgehensweise: Binden der Eigenschaften von zwei Steuerelementen'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 63584872c027ed3a80698304a7221c161c8d928a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570251"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>Vorgehensweise: Binden der Eigenschaften von zwei Steuerelementen
Dieses Beispiel zeigt, wie Sie die Eigenschaft eines instanziierten Steuerelements an, die von einem anderen mit binden die <xref:System.Windows.Data.Binding.ElementName%2A> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie binden die <xref:System.Windows.Controls.Panel.Background%2A> Eigenschaft eine <xref:System.Windows.Controls.Canvas> auf die <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A> -Eigenschaft einer <xref:System.Windows.Controls.ComboBox>:  
  
 [!code-xaml[BindDptoDp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 Bei Rendern dieses Beispiels sieht es folgendermaßen aus:  
  
 ![Canvas mit grünem Hintergrund](../../../../docs/framework/wpf/data/media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")  
  
 **Beachten Sie** die Bindungsziel-Eigenschaft (in diesem Beispiel die <xref:System.Windows.Controls.Panel.Background%2A> Eigenschaft) muss eine Abhängigkeitseigenschaft sein. Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
## <a name="see-also"></a>Siehe auch
- [Angeben der Bindungsquelle](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

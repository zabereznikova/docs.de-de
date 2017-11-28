---
title: 'Gewusst wie: Angeben der Bindungsrichtung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bdcda02a61f0114bfbbe5d5c411cb397cddcf683
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>Gewusst wie: Angeben der Bindungsrichtung
In diesem Beispiel wird erläutert, wie sich angeben lässt, ob die Bindung nur die Eigenschaft „Bindungsziel (Ziel)“, „Bindungsquelle (Quelle)“ oder sowohl die Ziel- als auch die Quelleigenschaft aktualisiert.  
  
## <a name="example"></a>Beispiel  
 Verwenden Sie die <xref:System.Windows.Data.Binding.Mode%2A> Eigenschaft, um die Richtung der Bindung anzugeben. In der folgenden Enumerationsliste werden die verfügbaren Optionen für Bindungsaktualisierungen angezeigt:  
  
-   <xref:System.Windows.Data.BindingMode.TwoWay>Wenn die Zieleigenschaft oder die Quelleigenschaft ändert die Zieleigenschaft oder der Eigenschaft aktualisiert werden soll.  
  
-   <xref:System.Windows.Data.BindingMode.OneWay>aktualisiert die Eigenschaft an, sobald sich die Quelleigenschaft ändert.  
  
-   <xref:System.Windows.Data.BindingMode.OneTime>aktualisiert die Eigenschaft nur verwendet werden, wenn die Anwendung gestartet oder der <xref:System.Windows.FrameworkElement.DataContext%2A> eine Änderung vorgenommen.  
  
-   <xref:System.Windows.Data.BindingMode.OneWayToSource>aktualisiert die Quelleigenschaft, wenn die Zieleigenschaft geändert wird.  
  
-   <xref:System.Windows.Data.BindingMode.Default>bewirkt, dass der <xref:System.Windows.Data.Binding.Mode%2A> Wert der Zieleigenschaft verwendet werden.  
  
 Weitere Informationen finden Sie unter der <xref:System.Windows.Data.BindingMode>-Enumeration.  
  
 Im folgenden Beispiel wird das Festlegen der <xref:System.Windows.Data.Binding.Mode%2A>-Eigenschaft veranschaulicht.  
  
 [!code-xaml[DirectionalBinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 Datenquellenänderungen erkannt (gilt für <xref:System.Windows.Data.BindingMode.OneWay> und <xref:System.Windows.Data.BindingMode.TwoWay> Bindungen), muss die Quelle einen Änderungsbenachrichtigungsmechanismus geeignete Eigenschaft z. B. implementieren <xref:System.ComponentModel.INotifyPropertyChanged>. Finden Sie unter [implementieren Änderungsbenachrichtigung](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) ein Beispiel für eine <xref:System.ComponentModel.INotifyPropertyChanged> Implementierung.  
  
 Für <xref:System.Windows.Data.BindingMode.TwoWay> oder <xref:System.Windows.Data.BindingMode.OneWayToSource> Bindungen, Sie können die zeitliche Steuerung der Quelle Updates durch Festlegen der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Eigenschaft. Weitere Informationen finden Sie unter <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Data.Binding>  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

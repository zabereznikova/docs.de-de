---
title: 'Vorgehensweise: Angeben der Bindungsrichtung'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 265271cee16d203d7652281c5416b93759e66d4b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378218"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>Vorgehensweise: Angeben der Bindungsrichtung
In diesem Beispiel wird erläutert, wie sich angeben lässt, ob die Bindung nur die Eigenschaft „Bindungsziel (Ziel)“, „Bindungsquelle (Quelle)“ oder sowohl die Ziel- als auch die Quelleigenschaft aktualisiert.  
  
## <a name="example"></a>Beispiel  
 Sie verwenden die <xref:System.Windows.Data.Binding.Mode%2A> Eigenschaft, um die Richtung der Bindung anzugeben. In der folgenden Enumerationsliste werden die verfügbaren Optionen für Bindungsaktualisierungen angezeigt:  
  
-   <xref:System.Windows.Data.BindingMode.TwoWay> aktualisiert die Zieleigenschaft bzw. die Eigenschaft, wenn sich die Zieleigenschaft oder die Quelleigenschaft ändert.  
  
-   <xref:System.Windows.Data.BindingMode.OneWay> aktualisiert die Zieleigenschaft, nur, wenn die Quelleigenschaft ändert.  
  
-   <xref:System.Windows.Data.BindingMode.OneTime> aktualisiert die Zieleigenschaft, nur, wenn die Anwendung gestartet wird oder wenn die <xref:System.Windows.FrameworkElement.DataContext%2A> wird eine Änderung vorgenommen.  
  
-   <xref:System.Windows.Data.BindingMode.OneWayToSource> Aktualisiert die Quelleigenschaft, wenn die Zieleigenschaft ändert.  
  
-   <xref:System.Windows.Data.BindingMode.Default> bewirkt, dass der <xref:System.Windows.Data.Binding.Mode%2A> Wert der Zieleigenschaft verwendet werden.  
  
 Weitere Informationen finden Sie unter der <xref:System.Windows.Data.BindingMode>-Enumeration.  
  
 Im folgenden Beispiel wird das Festlegen der <xref:System.Windows.Data.Binding.Mode%2A>-Eigenschaft veranschaulicht.  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 Zum Erkennen von quelländerungen (gilt für <xref:System.Windows.Data.BindingMode.OneWay> und <xref:System.Windows.Data.BindingMode.TwoWay> Bindungen), muss die Quelle einen Änderungsbenachrichtigungsmechanismus von geeigneten wie z. B. implementieren <xref:System.ComponentModel.INotifyPropertyChanged>. Finden Sie unter [bei Eigenschaftenänderungen implementieren](how-to-implement-property-change-notification.md) ein Beispiel für eine <xref:System.ComponentModel.INotifyPropertyChanged> Implementierung.  
  
 Für <xref:System.Windows.Data.BindingMode.TwoWay> oder <xref:System.Windows.Data.BindingMode.OneWayToSource> Bindungen können Sie die zeitplanung für die Quelle aktualisiert steuern, durch Festlegen der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Eigenschaft. Weitere Informationen finden Sie unter <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Data.Binding>
- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)

---
title: 'Gewusst wie: Angeben der Bindungsrichtung'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 8f7d843382ee3409047d7cf9549267d582883984
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459093"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>Gewusst wie: Angeben der Bindungs Richtung

In diesem Beispiel wird erläutert, wie sich angeben lässt, ob die Bindung nur die Eigenschaft „Bindungsziel (Ziel)“, „Bindungsquelle (Quelle)“ oder sowohl die Ziel- als auch die Quelleigenschaft aktualisiert.  
  
## <a name="example"></a>Beispiel  
 Verwenden Sie die <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType>-Eigenschaft, um die Bindungs Richtung anzugeben. Im folgenden finden Sie die verfügbaren Optionen für das Binden von Updates:  
  
- <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> aktualisiert die Ziel Eigenschaft oder die-Eigenschaft, wenn sich entweder die Ziel Eigenschaft oder die Quell Eigenschaft ändert.  
  
- <xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> aktualisiert die Ziel Eigenschaft nur, wenn sich die Quell Eigenschaft ändert.  
  
- <xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> aktualisiert die Ziel Eigenschaft nur, wenn die Anwendung gestartet wird oder wenn die <xref:System.Windows.FrameworkElement.DataContext%2A> eine Änderung durchläuft.  
  
- <xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> aktualisiert die Quell Eigenschaft, wenn die Ziel Eigenschaft geändert wird.  
  
- <xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> bewirkt, dass der standardmäßige <xref:System.Windows.Data.Binding.Mode%2A> Wert der Ziel Eigenschaft verwendet wird.  
  
 Weitere Informationen finden Sie unter der <xref:System.Windows.Data.BindingMode>-Enumeration.  
  
 Im folgenden Beispiel wird das Festlegen der <xref:System.Windows.Data.Binding.Mode%2A>-Eigenschaft veranschaulicht.  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 Zum Erkennen von Quell Änderungen (anwendbar auf <xref:System.Windows.Data.BindingMode.OneWay>-und <xref:System.Windows.Data.BindingMode.TwoWay> Bindungen) muss die Quelle einen geeigneten Benachrichtigungs Mechanismus für die Eigenschafts Änderung implementieren, z. b. <xref:System.ComponentModel.INotifyPropertyChanged>. Ein Beispiel für eine <xref:System.ComponentModel.INotifyPropertyChanged> Implementierung finden Sie unter [Implementieren von Benachrichtigungen über Eigenschafts Änderungen](how-to-implement-property-change-notification.md) .  
  
 Bei <xref:System.Windows.Data.BindingMode.TwoWay>-oder <xref:System.Windows.Data.BindingMode.OneWayToSource>-Bindungen können Sie die zeitliche Steuerung der Quell Updates steuern, indem Sie die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>-Eigenschaft festlegen. Weitere Informationen finden Sie unter <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.Binding>
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)

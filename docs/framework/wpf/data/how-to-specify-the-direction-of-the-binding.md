---
title: 'Vorgehensweise: Angeben der Bindungsrichtung'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 023cd42ad5fb321e7ffa65f08673cb4145f49af4
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817913"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>Vorgehensweise: Angeben der Bindungs Richtung

In diesem Beispiel wird erläutert, wie sich angeben lässt, ob die Bindung nur die Eigenschaft „Bindungsziel (Ziel)“, „Bindungsquelle (Quelle)“ oder sowohl die Ziel- als auch die Quelleigenschaft aktualisiert.  
  
## <a name="example"></a>Beispiel  
 Verwenden Sie die <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> -Eigenschaft, um die Bindungs Richtung anzugeben. Im folgenden finden Sie die verfügbaren Optionen für das Binden von Updates:  
  
- <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType>Aktualisiert die Ziel Eigenschaft oder die-Eigenschaft, wenn sich entweder die Ziel Eigenschaft oder die Quell Eigenschaft ändert.  
  
- <xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType>Aktualisiert die Ziel Eigenschaft nur, wenn sich die Quell Eigenschaft ändert.  
  
- <xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType>Aktualisiert die Ziel Eigenschaft nur, wenn die Anwendung gestartet wird oder <xref:System.Windows.FrameworkElement.DataContext%2A> wenn eine Änderung durchläuft.  
  
- <xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType>Aktualisiert die Quell Eigenschaft, wenn die Ziel Eigenschaft geändert wird.  
  
- <xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType>bewirkt, dass <xref:System.Windows.Data.Binding.Mode%2A> der Standardwert der Ziel Eigenschaft verwendet wird.  
  
 Weitere Informationen finden Sie unter der <xref:System.Windows.Data.BindingMode>-Enumeration.  
  
 Im folgenden Beispiel wird das Festlegen der <xref:System.Windows.Data.Binding.Mode%2A>-Eigenschaft veranschaulicht.  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 Zum Erkennen von Quell Änderungen (anwendbar <xref:System.Windows.Data.BindingMode.OneWay> auf <xref:System.Windows.Data.BindingMode.TwoWay> -und-Bindungen) muss die Quelle einen geeigneten Mechanismus für die Eigenschafts <xref:System.ComponentModel.INotifyPropertyChanged>Änderungs Benachrichtigung implementieren, z. b. Ein Beispiel für eine <xref:System.ComponentModel.INotifyPropertyChanged> -Implementierung finden Sie unter Implementieren von Benachrichtigungen über [Eigenschafts Änderungen](how-to-implement-property-change-notification.md) .  
  
 Für <xref:System.Windows.Data.BindingMode.TwoWay> - <xref:System.Windows.Data.BindingMode.OneWayToSource> oder-Bindungen können Sie die zeitliche Steuerung der Quell Aktualisierungen steuern, indem <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Sie die-Eigenschaft festlegen. Weitere Informationen finden Sie unter <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.Binding>
- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)

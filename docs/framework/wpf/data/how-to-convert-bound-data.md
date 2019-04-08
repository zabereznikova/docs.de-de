---
title: 'Vorgehensweise: Konvertieren von gebundenen Daten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
ms.openlocfilehash: 40699bec1c6cd775f7f8495b7a49eda15fb2ed83
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093799"
---
# <a name="how-to-convert-bound-data"></a>Vorgehensweise: Konvertieren von gebundenen Daten
Dieses Beispiel zeigt, wie Sie die Konvertierung aus, um Daten anwenden, die in Bindungen verwendet wird.  
  
 Zum Konvertieren von Daten während der Bindung, müssen Sie erstellen eine Klasse, implementiert die <xref:System.Windows.Data.IValueConverter> -Schnittstelle, die umfasst die <xref:System.Windows.Data.IValueConverter.Convert%2A> und <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> Methoden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Implementierung eines Datenkonverters ab, der den Date-Wert übergeben, damit sie nur das Jahr, Monat und Tag anzeigt konvertiert. Bei der Implementierung der <xref:System.Windows.Data.IValueConverter> -Schnittstelle, es hat sich bewährt, ergänzen Sie die Implementierung mit einer <xref:System.Windows.Data.ValueConversionAttribute> Attribut für die Entwicklung an tools, die Datentypen, die bei der Konvertierung, wie im folgenden Beispiel:  
  
 [!code-csharp[DataBindingLab#18](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 Nachdem Sie einen Konverter erstellt haben, können Sie es hinzufügen, als Ressource in Ihrem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei. Im folgenden Beispiel *Src* ordnet den Namespace, in dem *DateConverter* definiert ist.  
  
 [!code-xaml[DataBindingLab#15](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 Schließlich können Sie den Konverter in der Bindung mit der folgenden Syntax verwenden. Im folgenden Beispiel den Inhalt der Text der <xref:System.Windows.Controls.TextBlock> gebunden ist *"StartDate"*, dies ist eine Eigenschaft einer externen Datenquelle.  
  
 [!code-xaml[DataBindingLab#17](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 Formatressourcen stehen im Beispiel oben verwiesen wird, werden in ein Abschnitt mit Ressourcen in diesem Thema nicht gezeigt definiert.  
  
## <a name="see-also"></a>Siehe auch

- [Implementieren der Bindungsvalidierung](how-to-implement-binding-validation.md)
- [Übersicht über die Datenbindung](data-binding-overview.md)
- [Gewusst wie-Themen](data-binding-how-to-topics.md)

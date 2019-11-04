---
title: 'Gewusst wie: Konvertieren von gebundenen Daten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
ms.openlocfilehash: f9ad390626092d481bf47f017f643a29302c1b29
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458860"
---
# <a name="how-to-convert-bound-data"></a>Gewusst wie: Konvertieren von gebundenen Daten
In diesem Beispiel wird gezeigt, wie die Konvertierung auf Daten angewendet wird, die in Bindungen verwendet werden.  
  
 Zum Konvertieren von Daten während der Bindung müssen Sie eine Klasse erstellen, die die <xref:System.Windows.Data.IValueConverter>-Schnittstelle implementiert, die die Methoden <xref:System.Windows.Data.IValueConverter.Convert%2A> und <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> enthält.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Implementierung eines Datums Konverters, der den Wert für den Datumswert konvertiert, sodass er nur das Jahr, den Monat und den Tag anzeigt. Wenn Sie die <xref:System.Windows.Data.IValueConverter>-Schnittstelle implementieren, empfiehlt es sich, die-Implementierung mit einem <xref:System.Windows.Data.ValueConversionAttribute>-Attribut zu versehen, um den Entwicklungs Tools die Datentypen anzuzeigen, die an der Konvertierung beteiligt sind, wie im folgenden Beispiel gezeigt:  
  
 [!code-csharp[DataBindingLab#18](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 Nachdem Sie einen Konverter erstellt haben, können Sie ihn als Ressource in ihrer [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei hinzufügen. Im folgenden Beispiel wird *src* dem-Namespace zugeordnet, in dem *DateConverter* definiert ist.  
  
 [!code-xaml[DataBindingLab#15](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 Schließlich können Sie den Konverter in der Bindung verwenden, indem Sie die folgende Syntax verwenden. Im folgenden Beispiel wird der Text Inhalt des <xref:System.Windows.Controls.TextBlock> an *StartDate*gebunden, das eine Eigenschaft einer externen Datenquelle ist.  
  
 [!code-xaml[DataBindingLab#17](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 Die im obigen Beispiel referenzierten Stil Ressourcen werden in einem Ressourcenabschnitt definiert, der in diesem Thema nicht angezeigt wird.  
  
## <a name="see-also"></a>Siehe auch

- [Implementieren der Bindungsvalidierung](how-to-implement-binding-validation.md)
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)

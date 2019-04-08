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
# <a name="how-to-convert-bound-data"></a><span data-ttu-id="5ff48-102">Vorgehensweise: Konvertieren von gebundenen Daten</span><span class="sxs-lookup"><span data-stu-id="5ff48-102">How to: Convert Bound Data</span></span>
<span data-ttu-id="5ff48-103">Dieses Beispiel zeigt, wie Sie die Konvertierung aus, um Daten anwenden, die in Bindungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5ff48-103">This example shows how to apply conversion to data that is used in bindings.</span></span>  
  
 <span data-ttu-id="5ff48-104">Zum Konvertieren von Daten während der Bindung, müssen Sie erstellen eine Klasse, implementiert die <xref:System.Windows.Data.IValueConverter> -Schnittstelle, die umfasst die <xref:System.Windows.Data.IValueConverter.Convert%2A> und <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> Methoden.</span><span class="sxs-lookup"><span data-stu-id="5ff48-104">To convert data during binding, you must create a class that implements the <xref:System.Windows.Data.IValueConverter> interface, which includes the <xref:System.Windows.Data.IValueConverter.Convert%2A> and <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ff48-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5ff48-105">Example</span></span>  
 <span data-ttu-id="5ff48-106">Das folgende Beispiel zeigt die Implementierung eines Datenkonverters ab, der den Date-Wert übergeben, damit sie nur das Jahr, Monat und Tag anzeigt konvertiert.</span><span class="sxs-lookup"><span data-stu-id="5ff48-106">The following example shows the implementation of a date converter that converts the date value passed in so that it only shows the year, the month, and the day.</span></span> <span data-ttu-id="5ff48-107">Bei der Implementierung der <xref:System.Windows.Data.IValueConverter> -Schnittstelle, es hat sich bewährt, ergänzen Sie die Implementierung mit einer <xref:System.Windows.Data.ValueConversionAttribute> Attribut für die Entwicklung an tools, die Datentypen, die bei der Konvertierung, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5ff48-107">When implementing the <xref:System.Windows.Data.IValueConverter> interface, it is a good practice to decorate the implementation with a <xref:System.Windows.Data.ValueConversionAttribute> attribute to indicate to development tools the data types involved in the conversion, as in the following example:</span></span>  
  
 [!code-csharp[DataBindingLab#18](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 <span data-ttu-id="5ff48-108">Nachdem Sie einen Konverter erstellt haben, können Sie es hinzufügen, als Ressource in Ihrem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei.</span><span class="sxs-lookup"><span data-stu-id="5ff48-108">Once you have created a converter, you can add it as a resource in your [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="5ff48-109">Im folgenden Beispiel *Src* ordnet den Namespace, in dem *DateConverter* definiert ist.</span><span class="sxs-lookup"><span data-stu-id="5ff48-109">In the following example, *src* maps to the namespace in which *DateConverter* is defined.</span></span>  
  
 [!code-xaml[DataBindingLab#15](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 <span data-ttu-id="5ff48-110">Schließlich können Sie den Konverter in der Bindung mit der folgenden Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="5ff48-110">Finally, you can use the converter in your binding using the following syntax.</span></span> <span data-ttu-id="5ff48-111">Im folgenden Beispiel den Inhalt der Text der <xref:System.Windows.Controls.TextBlock> gebunden ist *"StartDate"*, dies ist eine Eigenschaft einer externen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="5ff48-111">In the following example, the text content of the <xref:System.Windows.Controls.TextBlock> is bound to *StartDate*, which is a property of an external data source.</span></span>  
  
 [!code-xaml[DataBindingLab#17](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 <span data-ttu-id="5ff48-112">Formatressourcen stehen im Beispiel oben verwiesen wird, werden in ein Abschnitt mit Ressourcen in diesem Thema nicht gezeigt definiert.</span><span class="sxs-lookup"><span data-stu-id="5ff48-112">The style resources referenced in the above example are defined in a resource section not shown in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff48-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ff48-113">See also</span></span>

- [<span data-ttu-id="5ff48-114">Implementieren der Bindungsvalidierung</span><span class="sxs-lookup"><span data-stu-id="5ff48-114">Implement Binding Validation</span></span>](how-to-implement-binding-validation.md)
- [<span data-ttu-id="5ff48-115">Übersicht über die Datenbindung</span><span class="sxs-lookup"><span data-stu-id="5ff48-115">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="5ff48-116">Gewusst wie-Themen</span><span class="sxs-lookup"><span data-stu-id="5ff48-116">How-to Topics</span></span>](data-binding-how-to-topics.md)

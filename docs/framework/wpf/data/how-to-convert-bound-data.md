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
# <a name="how-to-convert-bound-data"></a><span data-ttu-id="b725c-102">Gewusst wie: Konvertieren von gebundenen Daten</span><span class="sxs-lookup"><span data-stu-id="b725c-102">How to: Convert Bound Data</span></span>
<span data-ttu-id="b725c-103">In diesem Beispiel wird gezeigt, wie die Konvertierung auf Daten angewendet wird, die in Bindungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b725c-103">This example shows how to apply conversion to data that is used in bindings.</span></span>  
  
 <span data-ttu-id="b725c-104">Zum Konvertieren von Daten während der Bindung müssen Sie eine Klasse erstellen, die die <xref:System.Windows.Data.IValueConverter>-Schnittstelle implementiert, die die Methoden <xref:System.Windows.Data.IValueConverter.Convert%2A> und <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> enthält.</span><span class="sxs-lookup"><span data-stu-id="b725c-104">To convert data during binding, you must create a class that implements the <xref:System.Windows.Data.IValueConverter> interface, which includes the <xref:System.Windows.Data.IValueConverter.Convert%2A> and <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b725c-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b725c-105">Example</span></span>  
 <span data-ttu-id="b725c-106">Das folgende Beispiel zeigt die Implementierung eines Datums Konverters, der den Wert für den Datumswert konvertiert, sodass er nur das Jahr, den Monat und den Tag anzeigt.</span><span class="sxs-lookup"><span data-stu-id="b725c-106">The following example shows the implementation of a date converter that converts the date value passed in so that it only shows the year, the month, and the day.</span></span> <span data-ttu-id="b725c-107">Wenn Sie die <xref:System.Windows.Data.IValueConverter>-Schnittstelle implementieren, empfiehlt es sich, die-Implementierung mit einem <xref:System.Windows.Data.ValueConversionAttribute>-Attribut zu versehen, um den Entwicklungs Tools die Datentypen anzuzeigen, die an der Konvertierung beteiligt sind, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b725c-107">When implementing the <xref:System.Windows.Data.IValueConverter> interface, it is a good practice to decorate the implementation with a <xref:System.Windows.Data.ValueConversionAttribute> attribute to indicate to development tools the data types involved in the conversion, as in the following example:</span></span>  
  
 [!code-csharp[DataBindingLab#18](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 <span data-ttu-id="b725c-108">Nachdem Sie einen Konverter erstellt haben, können Sie ihn als Ressource in ihrer [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b725c-108">Once you have created a converter, you can add it as a resource in your [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="b725c-109">Im folgenden Beispiel wird *src* dem-Namespace zugeordnet, in dem *DateConverter* definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b725c-109">In the following example, *src* maps to the namespace in which *DateConverter* is defined.</span></span>  
  
 [!code-xaml[DataBindingLab#15](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 <span data-ttu-id="b725c-110">Schließlich können Sie den Konverter in der Bindung verwenden, indem Sie die folgende Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="b725c-110">Finally, you can use the converter in your binding using the following syntax.</span></span> <span data-ttu-id="b725c-111">Im folgenden Beispiel wird der Text Inhalt des <xref:System.Windows.Controls.TextBlock> an *StartDate*gebunden, das eine Eigenschaft einer externen Datenquelle ist.</span><span class="sxs-lookup"><span data-stu-id="b725c-111">In the following example, the text content of the <xref:System.Windows.Controls.TextBlock> is bound to *StartDate*, which is a property of an external data source.</span></span>  
  
 [!code-xaml[DataBindingLab#17](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 <span data-ttu-id="b725c-112">Die im obigen Beispiel referenzierten Stil Ressourcen werden in einem Ressourcenabschnitt definiert, der in diesem Thema nicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b725c-112">The style resources referenced in the above example are defined in a resource section not shown in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b725c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b725c-113">See also</span></span>

- [<span data-ttu-id="b725c-114">Implementieren der Bindungsvalidierung</span><span class="sxs-lookup"><span data-stu-id="b725c-114">Implement Binding Validation</span></span>](how-to-implement-binding-validation.md)
- [<span data-ttu-id="b725c-115">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="b725c-115">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="b725c-116">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="b725c-116">How-to Topics</span></span>](data-binding-how-to-topics.md)

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
ms.openlocfilehash: 526305f32280fb75e95538b9014c34c11ed8bffa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556639"
---
# <a name="how-to-convert-bound-data"></a><span data-ttu-id="0f9bd-102">Gewusst wie: Konvertieren von gebundenen Daten</span><span class="sxs-lookup"><span data-stu-id="0f9bd-102">How to: Convert Bound Data</span></span>
<span data-ttu-id="0f9bd-103">Dieses Beispiel zeigt, wie die Konvertierung in Daten angewendet, die in Bindungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0f9bd-103">This example shows how to apply conversion to data that is used in bindings.</span></span>  
  
 <span data-ttu-id="0f9bd-104">Um Daten während der Bindung zu konvertieren, müssen Sie eine Klasse, die implementiert erstellen die <xref:System.Windows.Data.IValueConverter> -Schnittstelle, die umfasst die <xref:System.Windows.Data.IValueConverter.Convert%2A> und <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> Methoden.</span><span class="sxs-lookup"><span data-stu-id="0f9bd-104">To convert data during binding, you must create a class that implements the <xref:System.Windows.Data.IValueConverter> interface, which includes the <xref:System.Windows.Data.IValueConverter.Convert%2A> and <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> methods.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f9bd-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0f9bd-105">Example</span></span>  
 <span data-ttu-id="0f9bd-106">Das folgende Beispiel zeigt die Implementierung für einen Datum-Konverter, der den Date-Wert übergeben, damit das Jahr, Monat und Tag nur zeigt konvertiert.</span><span class="sxs-lookup"><span data-stu-id="0f9bd-106">The following example shows the implementation of a date converter that converts the date value passed in so that it only shows the year, the month, and the day.</span></span> <span data-ttu-id="0f9bd-107">Bei der Implementierung der <xref:System.Windows.Data.IValueConverter> -Schnittstelle, es wird empfohlen, ergänzen die Implementierung mit einem <xref:System.Windows.Data.ValueConversionAttribute> Attribut an, dass für die Entwicklung tools die Datentypen bei der Konvertierung, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0f9bd-107">When implementing the <xref:System.Windows.Data.IValueConverter> interface, it is a good practice to decorate the implementation with a <xref:System.Windows.Data.ValueConversionAttribute> attribute to indicate to development tools the data types involved in the conversion, as in the following example:</span></span>  
  
 [!code-csharp[DataBindingLab#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 <span data-ttu-id="0f9bd-108">Nachdem Sie einen Konverter erstellt haben, können Sie ihn hinzufügen, als Ressource in Ihre [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei.</span><span class="sxs-lookup"><span data-stu-id="0f9bd-108">Once you have created a converter, you can add it as a resource in your [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="0f9bd-109">Im folgenden Beispiel *Src* ordnet den Namespace, in dem *DateConverter* definiert ist.</span><span class="sxs-lookup"><span data-stu-id="0f9bd-109">In the following example, *src* maps to the namespace in which *DateConverter* is defined.</span></span>  
  
 [!code-xaml[DataBindingLab#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 <span data-ttu-id="0f9bd-110">Schließlich können Sie den Konverter in der Bindung mithilfe der folgenden Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="0f9bd-110">Finally, you can use the converter in your binding using the following syntax.</span></span> <span data-ttu-id="0f9bd-111">Im folgenden Beispiel werden die von der Textinhalt der <xref:System.Windows.Controls.TextBlock> gebunden ist *"StartDate"*, also eine Eigenschaft einer externen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="0f9bd-111">In the following example, the text content of the <xref:System.Windows.Controls.TextBlock> is bound to *StartDate*, which is a property of an external data source.</span></span>  
  
 [!code-xaml[DataBindingLab#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 <span data-ttu-id="0f9bd-112">Die Style-Ressourcen, die im obigen Beispiel verwiesen werden in einem Ressourcenabschnitt nicht angezeigt, in diesem Thema definiert.</span><span class="sxs-lookup"><span data-stu-id="0f9bd-112">The style resources referenced in the above example are defined in a resource section not shown in this topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f9bd-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f9bd-113">See Also</span></span>  
 [<span data-ttu-id="0f9bd-114">Implementieren der Bindungsvalidierung</span><span class="sxs-lookup"><span data-stu-id="0f9bd-114">Implement Binding Validation</span></span>](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [<span data-ttu-id="0f9bd-115">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="0f9bd-115">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="0f9bd-116">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="0f9bd-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

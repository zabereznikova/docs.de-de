---
title: 'Vorgehensweise: Erstellen und Verwenden eines GridLengthConverter-Objekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], GridLengthConverter objects
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
ms.openlocfilehash: 498d2b9c531f391f4cbeb1478469a99d381deec7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770767"
---
# <a name="how-to-create-and-use-a-gridlengthconverter-object"></a><span data-ttu-id="dc13c-102">Vorgehensweise: Erstellen und Verwenden eines GridLengthConverter-Objekts</span><span class="sxs-lookup"><span data-stu-id="dc13c-102">How to: Create and Use a GridLengthConverter Object</span></span>
## <a name="example"></a><span data-ttu-id="dc13c-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dc13c-103">Example</span></span>  
 <span data-ttu-id="dc13c-104">Das folgende Beispiel zeigt das Erstellen und verwenden Sie eine Instanz des <xref:System.Windows.GridLengthConverter>.</span><span class="sxs-lookup"><span data-stu-id="dc13c-104">The following example shows how to create and use an instance of <xref:System.Windows.GridLengthConverter>.</span></span> <span data-ttu-id="dc13c-105">Das Beispiel definiert eine benutzerdefinierte Methode namens `changeCol`, übergibt die <xref:System.Windows.Controls.ListBoxItem> auf eine <xref:System.Windows.GridLengthConverter> , konvertiert der <xref:System.Windows.Controls.ContentControl.Content%2A> von einer <xref:System.Windows.Controls.ListBoxItem> mit einer Instanz von <xref:System.Windows.GridLength>.</span><span class="sxs-lookup"><span data-stu-id="dc13c-105">The example defines a custom method called `changeCol`, which passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.GridLengthConverter> that converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.GridLength>.</span></span> <span data-ttu-id="dc13c-106">Der konvertierte Wert wird dann wieder als der Wert der übergeben der <xref:System.Windows.Controls.ColumnDefinition.Width%2A> Eigenschaft der <xref:System.Windows.Controls.ColumnDefinition> Element.</span><span class="sxs-lookup"><span data-stu-id="dc13c-106">The converted value is then passed back as the value of the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> property of the <xref:System.Windows.Controls.ColumnDefinition> element.</span></span>  
  
 <span data-ttu-id="dc13c-107">Das Beispiel definiert auch eine zweite benutzerdefinierte Methode namens `changeColVal`.</span><span class="sxs-lookup"><span data-stu-id="dc13c-107">The example also defines a second custom method, called `changeColVal`.</span></span> <span data-ttu-id="dc13c-108">Diese benutzerdefinierte Methode konvertiert die <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> von eine <xref:System.Windows.Controls.Slider> auf eine <xref:System.String> aus und klicken Sie dann übergibt, der Wert wieder in die <xref:System.Windows.Controls.ColumnDefinition> als die <xref:System.Windows.Controls.ColumnDefinition.Width%2A> des Elements.</span><span class="sxs-lookup"><span data-stu-id="dc13c-108">This custom method converts the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> of a <xref:System.Windows.Controls.Slider> to a <xref:System.String> and then passes that value back to the <xref:System.Windows.Controls.ColumnDefinition> as the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of the element.</span></span>  
  
 <span data-ttu-id="dc13c-109">Beachten Sie, dass eine Separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei definiert den Inhalt einer <xref:System.Windows.Controls.ListBoxItem>.</span><span class="sxs-lookup"><span data-stu-id="dc13c-109">Note that a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file defines the contents of a <xref:System.Windows.Controls.ListBoxItem>.</span></span>  
  
 [!code-csharp[gridlengthConverterGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="dc13c-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc13c-110">See also</span></span>

- <xref:System.Windows.GridLengthConverter>
- <xref:System.Windows.GridLength>

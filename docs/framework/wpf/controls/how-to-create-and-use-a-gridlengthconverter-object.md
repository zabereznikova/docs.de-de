---
title: 'Gewusst wie: Erstellen und Verwenden eines GridLengthConverter-Objekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], GridLengthConverter objects
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
ms.openlocfilehash: 7c31b9e6599557783097c73468305dacfb19fc4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551855"
---
# <a name="how-to-create-and-use-a-gridlengthconverter-object"></a><span data-ttu-id="c3177-102">Gewusst wie: Erstellen und Verwenden eines GridLengthConverter-Objekts</span><span class="sxs-lookup"><span data-stu-id="c3177-102">How to: Create and Use a GridLengthConverter Object</span></span>
## <a name="example"></a><span data-ttu-id="c3177-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c3177-103">Example</span></span>  
 <span data-ttu-id="c3177-104">Im folgende Beispiel wird gezeigt, wie zum Erstellen und Verwenden einer Instanz von <xref:System.Windows.GridLengthConverter>.</span><span class="sxs-lookup"><span data-stu-id="c3177-104">The following example shows how to create and use an instance of <xref:System.Windows.GridLengthConverter>.</span></span> <span data-ttu-id="c3177-105">Im Beispiel definiert eine benutzerdefinierte Methode wird aufgerufen, `changeCol`, übergibt der <xref:System.Windows.Controls.ListBoxItem> auf eine <xref:System.Windows.GridLengthConverter> , konvertiert der <xref:System.Windows.Controls.ContentControl.Content%2A> des eine <xref:System.Windows.Controls.ListBoxItem> mit einer Instanz von <xref:System.Windows.GridLength>.</span><span class="sxs-lookup"><span data-stu-id="c3177-105">The example defines a custom method called `changeCol`, which passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.GridLengthConverter> that converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Windows.GridLength>.</span></span> <span data-ttu-id="c3177-106">Der konvertierte Wert wird dann wieder als Wert des übergeben der <xref:System.Windows.Controls.ColumnDefinition.Width%2A> Eigenschaft von der <xref:System.Windows.Controls.ColumnDefinition> Element.</span><span class="sxs-lookup"><span data-stu-id="c3177-106">The converted value is then passed back as the value of the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> property of the <xref:System.Windows.Controls.ColumnDefinition> element.</span></span>  
  
 <span data-ttu-id="c3177-107">Im Beispiel definiert auch eine zweite benutzerdefinierte Methode namens `changeColVal`.</span><span class="sxs-lookup"><span data-stu-id="c3177-107">The example also defines a second custom method, called `changeColVal`.</span></span> <span data-ttu-id="c3177-108">Diese benutzerdefinierte Methode konvertiert die <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> des eine <xref:System.Windows.Controls.Slider> auf eine <xref:System.String> und übergibt dann, den Wert zum Sichern der <xref:System.Windows.Controls.ColumnDefinition> als die <xref:System.Windows.Controls.ColumnDefinition.Width%2A> des Elements.</span><span class="sxs-lookup"><span data-stu-id="c3177-108">This custom method converts the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> of a <xref:System.Windows.Controls.Slider> to a <xref:System.String> and then passes that value back to the <xref:System.Windows.Controls.ColumnDefinition> as the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of the element.</span></span>  
  
 <span data-ttu-id="c3177-109">Beachten Sie, dass eine Separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei definiert den Inhalt einer <xref:System.Windows.Controls.ListBoxItem>.</span><span class="sxs-lookup"><span data-stu-id="c3177-109">Note that a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file defines the contents of a <xref:System.Windows.Controls.ListBoxItem>.</span></span>  
  
 [!code-csharp[gridlengthConverterGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c3177-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3177-110">See Also</span></span>  
 <xref:System.Windows.GridLengthConverter>  
 <xref:System.Windows.GridLength>

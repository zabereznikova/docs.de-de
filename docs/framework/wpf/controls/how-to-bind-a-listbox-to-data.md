---
title: 'Vorgehensweise: Binden eines ListBox-Objekts an Daten'
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 4dea53a524247d18628b3e7e7b2c06906dced53d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106435"
---
# <a name="how-to-bind-a-listbox-to-data"></a><span data-ttu-id="a862b-102">Vorgehensweise: Binden eines ListBox-Objekts an Daten</span><span class="sxs-lookup"><span data-stu-id="a862b-102">How to: Bind a ListBox to Data</span></span>
<span data-ttu-id="a862b-103">Erstellen Sie ein Anwendungsentwickler kann <xref:System.Windows.Controls.ListBox> Steuerelemente ohne Angabe des Inhalts der einzelnen <xref:System.Windows.Controls.ListBoxItem> getrennt.</span><span class="sxs-lookup"><span data-stu-id="a862b-103">An application developer can create <xref:System.Windows.Controls.ListBox> controls without specifying the contents of each <xref:System.Windows.Controls.ListBoxItem> separately.</span></span> <span data-ttu-id="a862b-104">Sie können die Datenbindung verwenden, zum Binden von Daten an die einzelnen Elemente.</span><span class="sxs-lookup"><span data-stu-id="a862b-104">You can use data binding to bind data to the individual items.</span></span>  
  
 <span data-ttu-id="a862b-105">Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.ListBox> auffüllt, die die <xref:System.Windows.Controls.ListBoxItem> Elemente durch die Datenbindung an eine Datenquelle namens *Farben*.</span><span class="sxs-lookup"><span data-stu-id="a862b-105">The following example shows how to create a <xref:System.Windows.Controls.ListBox> that populates the <xref:System.Windows.Controls.ListBoxItem> elements by data binding to a data source called *Colors*.</span></span> <span data-ttu-id="a862b-106">In diesem Fall ist es nicht erforderlich, mit <xref:System.Windows.Controls.ListBoxItem> Tags aus, um den Inhalt jedes Elements anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a862b-106">In this case it is not necessary to use <xref:System.Windows.Controls.ListBoxItem> tags to specify the content of each item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a862b-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a862b-107">Example</span></span>  
 [!code-xaml[ListBoxEvent#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="a862b-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a862b-108">See also</span></span>

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.Controls.ListBoxItem>
- [<span data-ttu-id="a862b-109">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="a862b-109">Controls</span></span>](../advanced/optimizing-performance-controls.md)

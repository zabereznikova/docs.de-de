---
title: 'Gewusst wie: Binden eines Listenfelds an Daten'
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 186d25750c5ce196a5e46c02f0f56e2440ea3a25
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552830"
---
# <a name="how-to-bind-a-listbox-to-data"></a><span data-ttu-id="421f9-102">Gewusst wie: Binden eines Listenfelds an Daten</span><span class="sxs-lookup"><span data-stu-id="421f9-102">How to: Bind a ListBox to Data</span></span>
<span data-ttu-id="421f9-103">Ein Anwendungsentwickler kann erstellen <xref:System.Windows.Controls.ListBox> Steuerelemente ohne Angabe des Inhalts der einzelnen <xref:System.Windows.Controls.ListBoxItem> getrennt.</span><span class="sxs-lookup"><span data-stu-id="421f9-103">An application developer can create <xref:System.Windows.Controls.ListBox> controls without specifying the contents of each <xref:System.Windows.Controls.ListBoxItem> separately.</span></span> <span data-ttu-id="421f9-104">Sie können die Datenbindung verwenden, zum Binden von Daten an die einzelnen Elemente.</span><span class="sxs-lookup"><span data-stu-id="421f9-104">You can use data binding to bind data to the individual items.</span></span>  
  
 <span data-ttu-id="421f9-105">Im folgende Beispiel wird gezeigt, wie zum Erstellen einer <xref:System.Windows.Controls.ListBox> , auffüllt, die die <xref:System.Windows.Controls.ListBoxItem> Elemente nach dem Datenbindung an eine Datenquelle namens *Farben*.</span><span class="sxs-lookup"><span data-stu-id="421f9-105">The following example shows how to create a <xref:System.Windows.Controls.ListBox> that populates the <xref:System.Windows.Controls.ListBoxItem> elements by data binding to a data source called *Colors*.</span></span> <span data-ttu-id="421f9-106">In diesem Fall ist es nicht notwendig, verwenden <xref:System.Windows.Controls.ListBoxItem> Tags aus, um den Inhalt jedes Elements anzugeben.</span><span class="sxs-lookup"><span data-stu-id="421f9-106">In this case it is not necessary to use <xref:System.Windows.Controls.ListBoxItem> tags to specify the content of each item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="421f9-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="421f9-107">Example</span></span>  
 [!code-xaml[ListBoxEvent#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="421f9-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="421f9-108">See Also</span></span>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.Controls.ListBoxItem>  
 [<span data-ttu-id="421f9-109">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="421f9-109">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)

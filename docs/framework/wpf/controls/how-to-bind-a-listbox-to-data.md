---
title: 'Vorgehensweise: Binden eines Listenfelds an Daten'
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox controls [WPF], binding data to
- data binding [WPF], ListBox control
- binding data [WPF], to ListBox control
ms.assetid: de93a907-709a-44a7-84bf-578b846a3d8b
ms.openlocfilehash: 2cbcb0fb859605c33e2d92559b4a47aa1725472c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372880"
---
# <a name="how-to-bind-a-listbox-to-data"></a><span data-ttu-id="2a6a6-102">Vorgehensweise: Binden eines Listenfelds an Daten</span><span class="sxs-lookup"><span data-stu-id="2a6a6-102">How to: Bind a ListBox to Data</span></span>
<span data-ttu-id="2a6a6-103">Erstellen Sie ein Anwendungsentwickler kann <xref:System.Windows.Controls.ListBox> Steuerelemente ohne Angabe des Inhalts der einzelnen <xref:System.Windows.Controls.ListBoxItem> getrennt.</span><span class="sxs-lookup"><span data-stu-id="2a6a6-103">An application developer can create <xref:System.Windows.Controls.ListBox> controls without specifying the contents of each <xref:System.Windows.Controls.ListBoxItem> separately.</span></span> <span data-ttu-id="2a6a6-104">Sie können die Datenbindung verwenden, zum Binden von Daten an die einzelnen Elemente.</span><span class="sxs-lookup"><span data-stu-id="2a6a6-104">You can use data binding to bind data to the individual items.</span></span>  
  
 <span data-ttu-id="2a6a6-105">Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.ListBox> auffüllt, die die <xref:System.Windows.Controls.ListBoxItem> Elemente durch die Datenbindung an eine Datenquelle namens *Farben*.</span><span class="sxs-lookup"><span data-stu-id="2a6a6-105">The following example shows how to create a <xref:System.Windows.Controls.ListBox> that populates the <xref:System.Windows.Controls.ListBoxItem> elements by data binding to a data source called *Colors*.</span></span> <span data-ttu-id="2a6a6-106">In diesem Fall ist es nicht erforderlich, mit <xref:System.Windows.Controls.ListBoxItem> Tags aus, um den Inhalt jedes Elements anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2a6a6-106">In this case it is not necessary to use <xref:System.Windows.Controls.ListBoxItem> tags to specify the content of each item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a6a6-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2a6a6-107">Example</span></span>  
 [!code-xaml[ListBoxEvent#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#7)]  
[!code-xaml[ListBoxEvent#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxEvent/CSharp/Pane1.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="2a6a6-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a6a6-108">See also</span></span>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.Controls.ListBoxItem>
- [<span data-ttu-id="2a6a6-109">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="2a6a6-109">Controls</span></span>](../advanced/optimizing-performance-controls.md)

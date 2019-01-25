---
title: 'Vorgehensweise: Implementieren einer CompositeCollection'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: 2021ed83a8f2a6896631fa69d5dd55a74cad8a8d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691865"
---
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="7a7b6-102">Vorgehensweise: Implementieren einer CompositeCollection</span><span class="sxs-lookup"><span data-stu-id="7a7b6-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="7a7b6-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7a7b6-103">Example</span></span>  
 <span data-ttu-id="7a7b6-104">Das folgende Beispiel zeigt, wie Sie mehrere Auflistungen und Elemente anzeigen, wie eine Liste mit den <xref:System.Windows.Data.CompositeCollection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="7a7b6-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="7a7b6-105">In diesem Beispiel `GreekGods` ist ein <xref:System.Collections.ObjectModel.ObservableCollection%601> von `GreekGod` benutzerdefinierter Objekte.</span><span class="sxs-lookup"><span data-stu-id="7a7b6-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="7a7b6-106">Datenvorlagen werden definiert, damit `GreekGod` Objekte und `GreekHero` Objekte werden mit einem "Gold" und eine Zyan Vordergrundfarbe.</span><span class="sxs-lookup"><span data-stu-id="7a7b6-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7a7b6-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a7b6-107">See also</span></span>
- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [<span data-ttu-id="7a7b6-108">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="7a7b6-108">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="7a7b6-109">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="7a7b6-109">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

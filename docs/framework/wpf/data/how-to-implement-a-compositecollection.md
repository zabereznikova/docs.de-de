---
title: 'Vorgehensweise: Implementieren einer CompositeCollection-Klasse'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: 8361c2bfa9c125aeadf0a62ca86af1855e5c3dbc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091160"
---
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="084d2-102">Vorgehensweise: Implementieren einer CompositeCollection-Klasse</span><span class="sxs-lookup"><span data-stu-id="084d2-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="084d2-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="084d2-103">Example</span></span>  
 <span data-ttu-id="084d2-104">Das folgende Beispiel zeigt, wie Sie mehrere Auflistungen und Elemente anzeigen, wie eine Liste mit den <xref:System.Windows.Data.CompositeCollection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="084d2-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="084d2-105">In diesem Beispiel `GreekGods` ist ein <xref:System.Collections.ObjectModel.ObservableCollection%601> von `GreekGod` benutzerdefinierter Objekte.</span><span class="sxs-lookup"><span data-stu-id="084d2-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="084d2-106">Datenvorlagen werden definiert, damit `GreekGod` Objekte und `GreekHero` Objekte werden mit einem "Gold" und eine Zyan Vordergrundfarbe.</span><span class="sxs-lookup"><span data-stu-id="084d2-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="084d2-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="084d2-107">See also</span></span>

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [<span data-ttu-id="084d2-108">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="084d2-108">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="084d2-109">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="084d2-109">How-to Topics</span></span>](data-binding-how-to-topics.md)

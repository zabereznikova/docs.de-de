---
title: 'Gewusst wie: Implementieren von CompositeCollection'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d7d9610c6c507ebdebdb5690dcb7aec19599ee80
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="708fe-102">Gewusst wie: Implementieren von CompositeCollection</span><span class="sxs-lookup"><span data-stu-id="708fe-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="708fe-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="708fe-103">Example</span></span>  
 <span data-ttu-id="708fe-104">Im folgende Beispiel wird gezeigt, wie mehrere Auflistungen und Elemente als eine Liste mit Anzeigen der <xref:System.Windows.Data.CompositeCollection> Klasse.</span><span class="sxs-lookup"><span data-stu-id="708fe-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="708fe-105">In diesem Beispiel `GreekGods` ist ein <xref:System.Collections.ObjectModel.ObservableCollection%601> von `GreekGod` benutzerdefinierten Objekte.</span><span class="sxs-lookup"><span data-stu-id="708fe-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="708fe-106">Datenvorlagen werden definiert, damit `GreekGod` Objekte und `GreekHero` Objekte werden mit der Gold eine Zyan Vordergrundfarbe.</span><span class="sxs-lookup"><span data-stu-id="708fe-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="708fe-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="708fe-107">See Also</span></span>  
 <xref:System.Windows.Data.CollectionContainer>  
 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>  
 <xref:System.Windows.Data.XmlDataProvider>  
 <xref:System.Windows.DataTemplate>  
 [<span data-ttu-id="708fe-108">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="708fe-108">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="708fe-109">Themen zur Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="708fe-109">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

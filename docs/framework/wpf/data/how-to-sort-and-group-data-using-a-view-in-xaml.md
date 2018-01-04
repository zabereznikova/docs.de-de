---
title: 'Gewusst wie: Sortieren und Gruppieren von Daten mit einer Ansicht in XAML'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], grouping data in views in XAML
- XAML [WPF], sorting data in views
- grouping data in views in XAML [WPF]
- data binding [WPF], sorting data in views in XAML
- sorting data in views in XAML [WPF]
- XAML [WPF], grouping data in views
- views [WPF], sorting data
- views [WPF], grouping data
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1bfa1941e6352372712debb5a5243bdd24810aac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a><span data-ttu-id="9f0e2-102">Gewusst wie: Sortieren und Gruppieren von Daten mit einer Ansicht in XAML</span><span class="sxs-lookup"><span data-stu-id="9f0e2-102">How to: Sort and Group Data Using a View in XAML</span></span>
<span data-ttu-id="9f0e2-103">In diesem Beispiel wird gezeigt, wie zum Erstellen einer Ansicht der Datensammlung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f0e2-103">This example shows how to create a view of a data collection in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="9f0e2-104">Sichten ermöglichen die Funktionen von gruppieren, sortieren, Filtern und das Konzept eines aktuellen Elements.</span><span class="sxs-lookup"><span data-stu-id="9f0e2-104">Views allow for the functionalities of grouping, sorting, filtering, and the notion of a current item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f0e2-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9f0e2-105">Example</span></span>  
 <span data-ttu-id="9f0e2-106">Im folgenden Beispiel die statische Ressource mit dem Namen *platziert* ist definiert als eine Auflistung von *Stelle* -Objekte, in denen die einzelnen *Stelle* Objekt einen Ortsnamen umfasste ist und die Status.</span><span class="sxs-lookup"><span data-stu-id="9f0e2-106">In the following example, the static resource named *places* is defined as a collection of *Place* objects, in which each *Place* object is consisted of a city name and the state.</span></span> <span data-ttu-id="9f0e2-107">Das Präfix *Src* zugeordnet ist, auf den Namespace, in dem die Datenquelle *stellen* definiert ist.</span><span class="sxs-lookup"><span data-stu-id="9f0e2-107">The prefix *src* is mapped to the namespace where the data source *Places* is defined.</span></span> <span data-ttu-id="9f0e2-108">Das Präfix *Scm* ordnet `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` und *Dat* ordnet `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span><span class="sxs-lookup"><span data-stu-id="9f0e2-108">The prefix *scm* maps to `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` and *dat* maps to `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span></span>  
  
 <span data-ttu-id="9f0e2-109">Das folgende Beispiel erstellt einen Überblick über die Datensammlung, die nach dem Namen der Stadt sortiert und gruppiert nach dem der Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="9f0e2-109">The following example creates a view of the data collection that is sorted by the city name and grouped by the state.</span></span>  
  
 [!code-xaml[CollectionViewSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 <span data-ttu-id="9f0e2-110">Die Sicht kann dann Bindungsquelle, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9f0e2-110">The view can then be a binding source, as in the following example:</span></span>  
  
 [!code-xaml[CollectionViewSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <span data-ttu-id="9f0e2-111">Für Bindungen an XML-Daten, die in definierten ein <xref:System.Windows.Data.XmlDataProvider> Ressource setzen vor den XML-Namen ein @-Symbols.</span><span class="sxs-lookup"><span data-stu-id="9f0e2-111">For bindings to XML data defined in an <xref:System.Windows.Data.XmlDataProvider> resource, precede the XML name with an @ symbol.</span></span>  
  
 [!code-xaml[CollectionViewSource#XDPChunk](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a><span data-ttu-id="9f0e2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f0e2-112">See Also</span></span>  
 <xref:System.Windows.Data.CollectionViewSource>  
 [<span data-ttu-id="9f0e2-113">Abrufen der Standardansicht einer Datenauflistung</span><span class="sxs-lookup"><span data-stu-id="9f0e2-113">Get the Default View of a Data Collection</span></span>](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)  
 [<span data-ttu-id="9f0e2-114">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="9f0e2-114">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="9f0e2-115">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="9f0e2-115">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

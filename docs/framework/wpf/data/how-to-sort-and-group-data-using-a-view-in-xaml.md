---
title: 'Gewusst wie: Sortieren und Gruppieren von Daten mit einer Ansicht in XAML'
ms.date: 03/30/2017
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
ms.openlocfilehash: 9e42dd330535f71438ab7af3dca9d078e9dfd8d3
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460125"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a><span data-ttu-id="4f783-102">Gewusst wie: Sortieren und Gruppieren von Daten mit einer Ansicht in XAML</span><span class="sxs-lookup"><span data-stu-id="4f783-102">How to: Sort and Group Data Using a View in XAML</span></span>
<span data-ttu-id="4f783-103">Dieses Beispiel zeigt, wie eine Ansicht einer Datensammlung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4f783-103">This example shows how to create a view of a data collection in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="4f783-104">Sichten ermöglichen das Gruppieren, sortieren, Filtern und das Konzept eines aktuellen Elements.</span><span class="sxs-lookup"><span data-stu-id="4f783-104">Views allow for the functionalities of grouping, sorting, filtering, and the notion of a current item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f783-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4f783-105">Example</span></span>  
 <span data-ttu-id="4f783-106">Im folgenden Beispiel wird die statische Ressource mit dem Namen *Places* als eine Auflistung von *Place* -Objekten definiert, wobei jedes *Place* -Objekt aus einem Ortsnamen und dem-Zustand besteht.</span><span class="sxs-lookup"><span data-stu-id="4f783-106">In the following example, the static resource named *places* is defined as a collection of *Place* objects, in which each *Place* object is consisted of a city name and the state.</span></span> <span data-ttu-id="4f783-107">Das Präfix *src* wird dem Namespace zugeordnet, in dem die Datenquellen Speicher *Orte* definiert sind.</span><span class="sxs-lookup"><span data-stu-id="4f783-107">The prefix *src* is mapped to the namespace where the data source *Places* is defined.</span></span> <span data-ttu-id="4f783-108">Das Präfix *SCM* wird `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` zugeordnet, und *DAT* wird `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="4f783-108">The prefix *scm* maps to `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` and *dat* maps to `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span></span>  
  
 <span data-ttu-id="4f783-109">Im folgenden Beispiel wird eine Ansicht der Datensammlung erstellt, die nach dem Namen der Stadt sortiert und nach dem-Status gruppiert ist.</span><span class="sxs-lookup"><span data-stu-id="4f783-109">The following example creates a view of the data collection that is sorted by the city name and grouped by the state.</span></span>  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 <span data-ttu-id="4f783-110">Die Sicht kann dann eine Bindungs Quelle sein, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="4f783-110">The view can then be a binding source, as in the following example:</span></span>  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <span data-ttu-id="4f783-111">Für Bindungen an XML-Daten, die in einer <xref:System.Windows.Data.XmlDataProvider> Ressource definiert sind, muss dem XML-Namen ein @-Symbol vorangestellt sein.</span><span class="sxs-lookup"><span data-stu-id="4f783-111">For bindings to XML data defined in an <xref:System.Windows.Data.XmlDataProvider> resource, precede the XML name with an @ symbol.</span></span>  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a><span data-ttu-id="4f783-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f783-112">See also</span></span>

- <xref:System.Windows.Data.CollectionViewSource>
- [<span data-ttu-id="4f783-113">Abrufen der Standardansicht einer Datenauflistung</span><span class="sxs-lookup"><span data-stu-id="4f783-113">Get the Default View of a Data Collection</span></span>](how-to-get-the-default-view-of-a-data-collection.md)
- [<span data-ttu-id="4f783-114">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="4f783-114">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="4f783-115">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="4f783-115">How-to Topics</span></span>](data-binding-how-to-topics.md)

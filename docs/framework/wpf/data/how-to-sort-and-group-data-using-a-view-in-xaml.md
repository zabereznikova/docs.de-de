---
title: 'Vorgehensweise: Sortieren und Gruppieren von Daten mit einer Ansicht in XAML'
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
ms.openlocfilehash: 01cbd113502c3f953bd701930df6db090844fefa
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351423"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a><span data-ttu-id="af537-102">Vorgehensweise: Sortieren und Gruppieren von Daten mit einer Ansicht in XAML</span><span class="sxs-lookup"><span data-stu-id="af537-102">How to: Sort and Group Data Using a View in XAML</span></span>
<span data-ttu-id="af537-103">In diesem Beispiel wird gezeigt, wie zum Erstellen einer Ansicht einer Datensammlung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af537-103">This example shows how to create a view of a data collection in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="af537-104">Sichten können für die Funktionen von gruppieren, sortieren, Filtern und das Konzept eines aktuellen Elements.</span><span class="sxs-lookup"><span data-stu-id="af537-104">Views allow for the functionalities of grouping, sorting, filtering, and the notion of a current item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af537-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af537-105">Example</span></span>  
 <span data-ttu-id="af537-106">Im folgenden Beispiel die statische Ressource namens *platziert* ist definiert als eine Auflistung von *Ort* -Objekte, in denen die einzelnen *Ort* Objekt ist Bestand, der Namen einer Stadt und die Status.</span><span class="sxs-lookup"><span data-stu-id="af537-106">In the following example, the static resource named *places* is defined as a collection of *Place* objects, in which each *Place* object is consisted of a city name and the state.</span></span> <span data-ttu-id="af537-107">Das Präfix *Src* zugeordnet ist, auf den Namespace, in dem die Datenquelle *stellen* definiert ist.</span><span class="sxs-lookup"><span data-stu-id="af537-107">The prefix *src* is mapped to the namespace where the data source *Places* is defined.</span></span> <span data-ttu-id="af537-108">Das Präfix *Scm* ordnet `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` und *Dat* ordnet `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span><span class="sxs-lookup"><span data-stu-id="af537-108">The prefix *scm* maps to `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` and *dat* maps to `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.</span></span>  
  
 <span data-ttu-id="af537-109">Das folgende Beispiel erstellt einen Überblick über die Datensammlung, die durch den Namen der Stadt sortiert und gruppiert nach den Status an.</span><span class="sxs-lookup"><span data-stu-id="af537-109">The following example creates a view of the data collection that is sorted by the city name and grouped by the state.</span></span>  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 <span data-ttu-id="af537-110">Die Ansicht kann dann eine Bindungsquelle, wie im folgenden Beispiel sein:</span><span class="sxs-lookup"><span data-stu-id="af537-110">The view can then be a binding source, as in the following example:</span></span>  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 <span data-ttu-id="af537-111">Für Bindungen an XML-Daten, die definiert, die einer <xref:System.Windows.Data.XmlDataProvider> Ressource stellen vor den Namen der XML-ein @-Symbols.</span><span class="sxs-lookup"><span data-stu-id="af537-111">For bindings to XML data defined in an <xref:System.Windows.Data.XmlDataProvider> resource, precede the XML name with an @ symbol.</span></span>  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a><span data-ttu-id="af537-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af537-112">See also</span></span>
- <xref:System.Windows.Data.CollectionViewSource>
- [<span data-ttu-id="af537-113">Abrufen der Standardansicht einer Datenauflistung</span><span class="sxs-lookup"><span data-stu-id="af537-113">Get the Default View of a Data Collection</span></span>](how-to-get-the-default-view-of-a-data-collection.md)
- [<span data-ttu-id="af537-114">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="af537-114">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="af537-115">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="af537-115">How-to Topics</span></span>](data-binding-how-to-topics.md)

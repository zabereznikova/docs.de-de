---
title: 'Gewusst wie: Formatieren einer Zeile in einem ListView, in dem ein GridView implementiert ist'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1e37d70fe1cb6aefb1404424c1a8f5339e0badf7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="6d738-102">Gewusst wie: Formatieren einer Zeile in einem ListView, in dem ein GridView implementiert ist</span><span class="sxs-lookup"><span data-stu-id="6d738-102">How to: Style a Row in a ListView That Implements a GridView</span></span>
<span data-ttu-id="6d738-103">In diesem Beispiel wird gezeigt, wie so formatieren Sie eine Zeile in einer <xref:System.Windows.Controls.ListView> -Steuerelement, implementiert eine <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> Modus.</span><span class="sxs-lookup"><span data-stu-id="6d738-103">This example shows how to style a row in a <xref:System.Windows.Controls.ListView> control that implements a <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d738-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6d738-104">Example</span></span>  
 <span data-ttu-id="6d738-105">Können Sie eine Zeile in Formatieren einer <xref:System.Windows.Controls.ListView> Steuerelement durch Festlegen einer <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> auf die <xref:System.Windows.Controls.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="6d738-105">You can style a row in a <xref:System.Windows.Controls.ListView> control by setting an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> on the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="6d738-106">Festlegen des Formats für die Elemente, die als Werte dargestellt werden <xref:System.Windows.Controls.ListViewItem> Objekte.</span><span class="sxs-lookup"><span data-stu-id="6d738-106">Set the style for its items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="6d738-107">Die <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Verweise der <xref:System.Windows.Controls.ControlTemplate> Objekte, die verwendet werden, um den Zeileninhalt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6d738-107">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references the <xref:System.Windows.Controls.ControlTemplate> objects that are used to display the row content.</span></span>  
  
 <span data-ttu-id="6d738-108">Das vollständige Beispiel, aus dem die folgenden Beispiele stammen, zeigt eine Auflistung von Informationen zu Musiktiteln, die in einer [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Datenbank gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="6d738-108">The complete sample, which the following examples are extracted from, displays a collection of song information that is stored in an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] database.</span></span> <span data-ttu-id="6d738-109">Jeder Titel in der Datenbank verfügt über ein Bewertungsfeld, und der Wert dieses Felds gibt an, wie eine Zeile mit den zugehörigen Informationen angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6d738-109">Each song in the database has a rating field and the value of this field specifies how to display a row of song information.</span></span>  
  
 <span data-ttu-id="6d738-110">Das folgende Beispiel zeigt, wie definiert <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> für die <xref:System.Windows.Controls.ListViewItem> Objekte, die die Titel in der Auflistung Musiktitel darstellen.</span><span class="sxs-lookup"><span data-stu-id="6d738-110">The following example shows how to define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for the <xref:System.Windows.Controls.ListViewItem> objects that represent the songs in the song collection.</span></span> <span data-ttu-id="6d738-111">Die <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Verweise <xref:System.Windows.Controls.ControlTemplate> Objekte, die angeben, wie eine Zeile mit Titelinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d738-111">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references <xref:System.Windows.Controls.ControlTemplate> objects that specify how to display a row of song information.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 <span data-ttu-id="6d738-112">Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.ControlTemplate> , addiert der Textzeichenfolge `"Strongly Recommended"` auf die Zeile.</span><span class="sxs-lookup"><span data-stu-id="6d738-112">The following example shows a <xref:System.Windows.Controls.ControlTemplate> that adds the text string `"Strongly Recommended"` to the row.</span></span> <span data-ttu-id="6d738-113">Diese Vorlage verwiesen wird, der <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> und zeigt an, wenn der Titel Bewertung den Wert 5 (5) aufweist.</span><span class="sxs-lookup"><span data-stu-id="6d738-113">This template is referenced in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> and displays when the song's rating has a value of 5 (five).</span></span> <span data-ttu-id="6d738-114">Die <xref:System.Windows.Controls.ControlTemplate> enthält eine <xref:System.Windows.Controls.GridViewRowPresenter> -Objekt, das den Inhalt der Zeile in den Spalten angeordnet, gemäß der Definition von der <xref:System.Windows.Controls.GridView> sichtmodus befinden.</span><span class="sxs-lookup"><span data-stu-id="6d738-114">The <xref:System.Windows.Controls.ControlTemplate> includes a <xref:System.Windows.Controls.GridViewRowPresenter> object that lays out the contents of the row in columns as defined by the <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 <span data-ttu-id="6d738-115">Das folgende Beispiel definiert <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="6d738-115">The following example defines <xref:System.Windows.Controls.GridView>.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a><span data-ttu-id="6d738-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d738-116">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="6d738-117">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="6d738-117">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="6d738-118">Übersicht über ListView</span><span class="sxs-lookup"><span data-stu-id="6d738-118">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="6d738-119">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="6d738-119">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)

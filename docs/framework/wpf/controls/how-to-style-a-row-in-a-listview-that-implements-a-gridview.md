---
title: 'Vorgehensweise: Formatieren einer Zeile in einem ListView-Objekt, in dem ein GridView-Objekt implementiert ist'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 9af8d10c7db2d3bbe8b9443402cbb1cfeaa7edb3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091459"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="f11a6-102">Vorgehensweise: Formatieren einer Zeile in einem ListView-Objekt, in dem ein GridView-Objekt implementiert ist</span><span class="sxs-lookup"><span data-stu-id="f11a6-102">How to: Style a Row in a ListView That Implements a GridView</span></span>
<span data-ttu-id="f11a6-103">In diesem Beispiel wird gezeigt, wie zum Formatieren einer Zeile in einer <xref:System.Windows.Controls.ListView> -Steuerelement, implementiert eine <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> Modus.</span><span class="sxs-lookup"><span data-stu-id="f11a6-103">This example shows how to style a row in a <xref:System.Windows.Controls.ListView> control that implements a <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f11a6-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f11a6-104">Example</span></span>  
 <span data-ttu-id="f11a6-105">Können Sie eine Zeile in Formatieren einer <xref:System.Windows.Controls.ListView> Steuerelement durch Festlegen einer <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> auf die <xref:System.Windows.Controls.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f11a6-105">You can style a row in a <xref:System.Windows.Controls.ListView> control by setting an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> on the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="f11a6-106">Legen Sie den Stil für die enthaltenen Elemente, die als dargestellt werden <xref:System.Windows.Controls.ListViewItem> Objekte.</span><span class="sxs-lookup"><span data-stu-id="f11a6-106">Set the style for its items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="f11a6-107">Die <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Verweise der <xref:System.Windows.Controls.ControlTemplate> Objekte, die zum Anzeigen des Zeileninhalts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f11a6-107">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references the <xref:System.Windows.Controls.ControlTemplate> objects that are used to display the row content.</span></span>  
  
 <span data-ttu-id="f11a6-108">Das vollständige Beispiel, aus dem die folgenden Beispiele stammen, zeigt eine Auflistung von Informationen zu Musiktiteln, die in einer [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Datenbank gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="f11a6-108">The complete sample, which the following examples are extracted from, displays a collection of song information that is stored in an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] database.</span></span> <span data-ttu-id="f11a6-109">Jeder Titel in der Datenbank verfügt über ein Bewertungsfeld, und der Wert dieses Felds gibt an, wie eine Zeile mit den zugehörigen Informationen angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f11a6-109">Each song in the database has a rating field and the value of this field specifies how to display a row of song information.</span></span>  
  
 <span data-ttu-id="f11a6-110">Das folgende Beispiel zeigt, wie Sie definieren <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> für die <xref:System.Windows.Controls.ListViewItem> Objekte, die die Titel in der Auflistung darstellen.</span><span class="sxs-lookup"><span data-stu-id="f11a6-110">The following example shows how to define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for the <xref:System.Windows.Controls.ListViewItem> objects that represent the songs in the song collection.</span></span> <span data-ttu-id="f11a6-111">Die <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Verweise <xref:System.Windows.Controls.ControlTemplate> Objekte, die angeben, wie eine Zeile mit Titelinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f11a6-111">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references <xref:System.Windows.Controls.ControlTemplate> objects that specify how to display a row of song information.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 <span data-ttu-id="f11a6-112">Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.ControlTemplate> , addiert die Textzeichenfolge `"Strongly Recommended"` auf die Zeile.</span><span class="sxs-lookup"><span data-stu-id="f11a6-112">The following example shows a <xref:System.Windows.Controls.ControlTemplate> that adds the text string `"Strongly Recommended"` to the row.</span></span> <span data-ttu-id="f11a6-113">Diese Vorlage verwiesen wird, der <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> und zeigt an, wenn der Titel mit dem Wert 5 (fünf) hat.</span><span class="sxs-lookup"><span data-stu-id="f11a6-113">This template is referenced in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> and displays when the song's rating has a value of 5 (five).</span></span> <span data-ttu-id="f11a6-114">Die <xref:System.Windows.Controls.ControlTemplate> enthält eine <xref:System.Windows.Controls.GridViewRowPresenter> -Objekt, das den Inhalt der Zeile Spalten angelegt, gemäß der <xref:System.Windows.Controls.GridView> sichtmodus befinden.</span><span class="sxs-lookup"><span data-stu-id="f11a6-114">The <xref:System.Windows.Controls.ControlTemplate> includes a <xref:System.Windows.Controls.GridViewRowPresenter> object that lays out the contents of the row in columns as defined by the <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 <span data-ttu-id="f11a6-115">Das folgende Beispiel definiert <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="f11a6-115">The following example defines <xref:System.Windows.Controls.GridView>.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a><span data-ttu-id="f11a6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f11a6-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="f11a6-117">Gewusst wie-Themen</span><span class="sxs-lookup"><span data-stu-id="f11a6-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="f11a6-118">Übersicht über ListView</span><span class="sxs-lookup"><span data-stu-id="f11a6-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="f11a6-119">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="f11a6-119">Styling and Templating</span></span>](styling-and-templating.md)

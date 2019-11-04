---
title: 'Gewusst wie: Formatieren einer Zeile in einem ListView, in dem ein GridView implementiert ist'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 150988aab368e3ffef0107d29bea5ebc53163946
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459323"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="8269e-102">Gewusst wie: Formatieren einer Zeile in einem ListView, in dem ein GridView implementiert ist</span><span class="sxs-lookup"><span data-stu-id="8269e-102">How to: Style a Row in a ListView That Implements a GridView</span></span>
<span data-ttu-id="8269e-103">In diesem Beispiel wird gezeigt, wie eine Zeile in einem <xref:System.Windows.Controls.ListView>-Steuerelement formatieren wird, das einen <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> Modus implementiert.</span><span class="sxs-lookup"><span data-stu-id="8269e-103">This example shows how to style a row in a <xref:System.Windows.Controls.ListView> control that implements a <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8269e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8269e-104">Example</span></span>  
 <span data-ttu-id="8269e-105">Sie können eine Zeile in einem <xref:System.Windows.Controls.ListView>-Steuerelement formatieren, indem Sie eine <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> auf dem <xref:System.Windows.Controls.ListView>-Steuerelement festlegen.</span><span class="sxs-lookup"><span data-stu-id="8269e-105">You can style a row in a <xref:System.Windows.Controls.ListView> control by setting an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> on the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="8269e-106">Legen Sie den Stil für die Elemente fest, die als <xref:System.Windows.Controls.ListViewItem>-Objekte dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8269e-106">Set the style for its items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="8269e-107">Der <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> verweist auf die <xref:System.Windows.Controls.ControlTemplate> Objekte, die verwendet werden, um den Zeilen Inhalt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8269e-107">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references the <xref:System.Windows.Controls.ControlTemplate> objects that are used to display the row content.</span></span>  
  
 <span data-ttu-id="8269e-108">Das vollständige Beispiel, aus dem die folgenden Beispiele stammen, zeigt eine Auflistung von Informationen zu Musiktiteln, die in einer [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Datenbank gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="8269e-108">The complete sample, which the following examples are extracted from, displays a collection of song information that is stored in an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] database.</span></span> <span data-ttu-id="8269e-109">Jeder Titel in der Datenbank verfügt über ein Bewertungsfeld, und der Wert dieses Felds gibt an, wie eine Zeile mit den zugehörigen Informationen angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8269e-109">Each song in the database has a rating field and the value of this field specifies how to display a row of song information.</span></span>  
  
 <span data-ttu-id="8269e-110">Im folgenden Beispiel wird gezeigt, wie <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> für die <xref:System.Windows.Controls.ListViewItem>-Objekte definiert werden, die die-Lieder in der Song-Auflistung darstellen.</span><span class="sxs-lookup"><span data-stu-id="8269e-110">The following example shows how to define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for the <xref:System.Windows.Controls.ListViewItem> objects that represent the songs in the song collection.</span></span> <span data-ttu-id="8269e-111">Der <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> verweist auf <xref:System.Windows.Controls.ControlTemplate> Objekte, die angeben, wie eine Zeile mit den Songinformationen angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8269e-111">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references <xref:System.Windows.Controls.ControlTemplate> objects that specify how to display a row of song information.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 <span data-ttu-id="8269e-112">Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.ControlTemplate>, die der Zeile die Text Zeichenfolge `"Strongly Recommended"` hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="8269e-112">The following example shows a <xref:System.Windows.Controls.ControlTemplate> that adds the text string `"Strongly Recommended"` to the row.</span></span> <span data-ttu-id="8269e-113">Auf diese Vorlage wird im <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> verwiesen und angezeigt, wenn die Titel Bewertung den Wert 5 (fünf) aufweist.</span><span class="sxs-lookup"><span data-stu-id="8269e-113">This template is referenced in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> and displays when the song's rating has a value of 5 (five).</span></span> <span data-ttu-id="8269e-114">Die <xref:System.Windows.Controls.ControlTemplate> enthält ein <xref:System.Windows.Controls.GridViewRowPresenter> Objekt, das den Inhalt der Zeile in Spalten festlegt, wie im <xref:System.Windows.Controls.GridView> Ansichtsmodus definiert.</span><span class="sxs-lookup"><span data-stu-id="8269e-114">The <xref:System.Windows.Controls.ControlTemplate> includes a <xref:System.Windows.Controls.GridViewRowPresenter> object that lays out the contents of the row in columns as defined by the <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 <span data-ttu-id="8269e-115">Im folgenden Beispiel wird <xref:System.Windows.Controls.GridView>definiert.</span><span class="sxs-lookup"><span data-stu-id="8269e-115">The following example defines <xref:System.Windows.Controls.GridView>.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a><span data-ttu-id="8269e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8269e-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="8269e-117">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="8269e-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="8269e-118">Übersicht über ListView</span><span class="sxs-lookup"><span data-stu-id="8269e-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="8269e-119">Erstellen von Formaten und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="8269e-119">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)

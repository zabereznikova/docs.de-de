---
title: 'Gewusst wie: Erstellen eines benutzerdefinierten Ansichtsmodus für eine ListView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 239fb2e9a364bd0265ff7cf644ee296878280cf3
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43561694"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a><span data-ttu-id="bae81-102">Gewusst wie: Erstellen eines benutzerdefinierten Ansichtsmodus für eine ListView</span><span class="sxs-lookup"><span data-stu-id="bae81-102">How to: Create a Custom View Mode for a ListView</span></span>
<span data-ttu-id="bae81-103">In diesem Beispiel wird gezeigt, wie eine benutzerdefinierte <xref:System.Windows.Controls.ListView.View%2A> Modus für eine <xref:System.Windows.Controls.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="bae81-103">This example shows how to create a custom <xref:System.Windows.Controls.ListView.View%2A> mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bae81-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bae81-104">Example</span></span>  
 <span data-ttu-id="bae81-105">Verwenden Sie die <xref:System.Windows.Controls.ViewBase> Klasse bei der Erstellung einer benutzerdefinierten Ansicht für die <xref:System.Windows.Controls.ListView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="bae81-105">You must use the <xref:System.Windows.Controls.ViewBase> class when you create a custom view for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="bae81-106">Das folgende Beispiel zeigt einen Anzeigemodus aus, die aufgerufen wird `PlainView`, ergibt sich aus der <xref:System.Windows.Controls.ViewBase> Klasse.</span><span class="sxs-lookup"><span data-stu-id="bae81-106">The following example shows a view mode that is called `PlainView`, which is derived from the <xref:System.Windows.Controls.ViewBase> class.</span></span>  
  
 [!code-csharp[ListViewCustomView#PlainView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 <span data-ttu-id="bae81-107">Verwenden Sie zum Anwenden eines Stils für die benutzerdefinierte Ansicht der <xref:System.Windows.Style> Klasse.</span><span class="sxs-lookup"><span data-stu-id="bae81-107">To apply a style to the custom view, use the <xref:System.Windows.Style> class.</span></span> <span data-ttu-id="bae81-108">Das folgende Beispiel definiert eine <xref:System.Windows.Style> für die `PlainView` sichtmodus befinden.</span><span class="sxs-lookup"><span data-stu-id="bae81-108">The following example defines a <xref:System.Windows.Style> for the `PlainView` view mode.</span></span> <span data-ttu-id="bae81-109">Im vorherigen Beispiel dieses Format festgelegt ist, als Wert für die <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> für definierte Eigenschaft `PlainView`.</span><span class="sxs-lookup"><span data-stu-id="bae81-109">In the previous example, this style is set as the value of the <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> property that is defined for `PlainView`.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 <span data-ttu-id="bae81-110">Um das Layout der Daten in einen benutzerdefinierten Ansichtsmodus zu definieren, definieren eine <xref:System.Windows.DataTemplate> Objekt.</span><span class="sxs-lookup"><span data-stu-id="bae81-110">To define the layout of data in a custom view mode, define a <xref:System.Windows.DataTemplate> object.</span></span> <span data-ttu-id="bae81-111">Das folgende Beispiel definiert eine <xref:System.Windows.DataTemplate> , die verwendet werden kann, zum Anzeigen von Daten in die `PlainView` sichtmodus befinden.</span><span class="sxs-lookup"><span data-stu-id="bae81-111">The following example defines a <xref:System.Windows.DataTemplate> that can be used to display data in the `PlainView` view mode.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 <span data-ttu-id="bae81-112">Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.ResourceKey> für die `PlainView` Anzeigemodus, verwendet der <xref:System.Windows.DataTemplate> , die im vorherigen Beispiel definiert ist.</span><span class="sxs-lookup"><span data-stu-id="bae81-112">The following example shows how to define a <xref:System.Windows.ResourceKey> for the `PlainView` view mode that uses the <xref:System.Windows.DataTemplate> that is defined in the previous example.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <span data-ttu-id="bae81-113">Ein <xref:System.Windows.Controls.ListView> -Steuerelement kann eine benutzerdefinierte Ansicht verwenden, setzen Sie die <xref:System.Windows.Controls.ListView.View%2A> Eigenschaft, um den Ressourcenschlüssel.</span><span class="sxs-lookup"><span data-stu-id="bae81-113">A <xref:System.Windows.Controls.ListView> control can use a custom view if you set the <xref:System.Windows.Controls.ListView.View%2A> property to the resource key.</span></span> <span data-ttu-id="bae81-114">Das folgende Beispiel zeigt, wie angegeben `PlainView` als den Anzeigemodus für eine <xref:System.Windows.Controls.ListView>.</span><span class="sxs-lookup"><span data-stu-id="bae81-114">The following example shows how to specify `PlainView` as the view mode for a <xref:System.Windows.Controls.ListView>.</span></span>  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 <span data-ttu-id="bae81-115">Das vollständige Beispiel finden Sie unter [ListView mit mehreren Ansichten Beispiel](https://go.microsoft.com/fwlink/?LinkID=160013).</span><span class="sxs-lookup"><span data-stu-id="bae81-115">For the complete sample, see [ListView with Multiple Views Sample](https://go.microsoft.com/fwlink/?LinkID=160013).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bae81-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bae81-116">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="bae81-117">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="bae81-117">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="bae81-118">Übersicht über ListView</span><span class="sxs-lookup"><span data-stu-id="bae81-118">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="bae81-119">Übersicht über GridView</span><span class="sxs-lookup"><span data-stu-id="bae81-119">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)

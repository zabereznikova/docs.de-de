---
title: 'Vorgehensweise: Erstellen von einfachen oder komplexen TreeViews'
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], creating
- Control class [WPF], TreeView [WPF], creating
ms.assetid: 1defbb78-b8e7-4c0e-b650-576453ac828d
ms.openlocfilehash: 9b19443c80818809122b0bbfc7c7dae7b4b40da5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368915"
---
# <a name="how-to-create-simple-or-complex-treeviews"></a><span data-ttu-id="96870-102">Vorgehensweise: Erstellen von einfachen oder komplexen TreeViews</span><span class="sxs-lookup"><span data-stu-id="96870-102">How to: Create Simple or Complex TreeViews</span></span>
<span data-ttu-id="96870-103">In diesem Beispiel wird gezeigt, wie zum Erstellen von einfachen oder komplexen <xref:System.Windows.Controls.TreeView> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="96870-103">This example shows how to create simple or complex <xref:System.Windows.Controls.TreeView> controls.</span></span>  
  
 <span data-ttu-id="96870-104">Ein <xref:System.Windows.Controls.TreeView> besteht aus einer Hierarchie von <xref:System.Windows.Controls.TreeViewItem> -Steuerelemente, die einfache Textzeichenfolgen und auch eine komplexere Inhalte, z. B. darf <xref:System.Windows.Controls.Button> Steuerelemente oder ein <xref:System.Windows.Controls.StackPanel> mit eingebetteter Inhalt.</span><span class="sxs-lookup"><span data-stu-id="96870-104">A <xref:System.Windows.Controls.TreeView> consists of a hierarchy of <xref:System.Windows.Controls.TreeViewItem> controls, which can contain simple text strings and also more complex content, such as <xref:System.Windows.Controls.Button> controls or a <xref:System.Windows.Controls.StackPanel> with embedded content.</span></span> <span data-ttu-id="96870-105">Sie können explizit definieren, die <xref:System.Windows.Controls.TreeView> Inhalt oder eine Datenquelle kann der Inhalt bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="96870-105">You can explicitly define the <xref:System.Windows.Controls.TreeView> content or a data source can provide the content.</span></span> <span data-ttu-id="96870-106">Dieses Thema enthält Beispiele für diese Konzepte.</span><span class="sxs-lookup"><span data-stu-id="96870-106">This topic provides examples of these concepts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96870-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="96870-107">Example</span></span>  
 <span data-ttu-id="96870-108">Die <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Eigenschaft der <xref:System.Windows.Controls.TreeViewItem> enthält den Inhalt, der die <xref:System.Windows.Controls.TreeView> für dieses Element angezeigt.</span><span class="sxs-lookup"><span data-stu-id="96870-108">The <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property of the <xref:System.Windows.Controls.TreeViewItem> contains the content that the <xref:System.Windows.Controls.TreeView> displays for that item.</span></span> <span data-ttu-id="96870-109">Ein <xref:System.Windows.Controls.TreeViewItem> haben auch <xref:System.Windows.Controls.TreeViewItem> Steuerelemente als seine untergeordneten Elemente und Sie können diese untergeordneten Elemente definieren, indem Sie mit der <xref:System.Windows.Controls.ItemsControl.Items%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="96870-109">A <xref:System.Windows.Controls.TreeViewItem> can also have <xref:System.Windows.Controls.TreeViewItem> controls as its child elements and you can define these child elements by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="96870-110">Das folgende Beispiel zeigt, wie Sie explizit definieren <xref:System.Windows.Controls.TreeViewItem> Inhalt durch Festlegen der <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> Eigenschaft, um eine Textzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="96870-110">The following example shows how to explicitly define <xref:System.Windows.Controls.TreeViewItem> content by setting the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property to a text string.</span></span>  
  
 [!code-xaml[TreeViewSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="96870-111">Das folgende Beispiel zeigt die untergeordneten Elemente definieren eine <xref:System.Windows.Controls.TreeViewItem> definieren <xref:System.Windows.Controls.ItemsControl.Items%2A> sind <xref:System.Windows.Controls.Button> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="96870-111">The following example show how to define child elements of a <xref:System.Windows.Controls.TreeViewItem> by defining <xref:System.Windows.Controls.ItemsControl.Items%2A> that are <xref:System.Windows.Controls.Button> controls.</span></span>  
  
 [!code-xaml[TreeViewSimple#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#3)]  
  
 <span data-ttu-id="96870-112">Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.TreeView> , in denen ein <xref:System.Windows.Data.XmlDataProvider> bietet <xref:System.Windows.Controls.TreeViewItem> Inhalt und einem <xref:System.Windows.HierarchicalDataTemplate> definiert die Darstellung des Inhalts.</span><span class="sxs-lookup"><span data-stu-id="96870-112">The following example shows how to create a <xref:System.Windows.Controls.TreeView> where an <xref:System.Windows.Data.XmlDataProvider> provides <xref:System.Windows.Controls.TreeViewItem> content and a <xref:System.Windows.HierarchicalDataTemplate> defines the appearance of the content.</span></span>  
  
 [!code-xaml[TreeViewSimple#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#6)]  
  
 [!code-xaml[TreeViewSimple#7](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#7)]  
  
 [!code-xaml[TreeViewSimple#5](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#5)]  
  
 <span data-ttu-id="96870-113">Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.TreeView> , in denen die <xref:System.Windows.Controls.TreeViewItem> Inhalt enthält <xref:System.Windows.Controls.DockPanel> Steuerelemente, die eingebettete Inhalte zu haben.</span><span class="sxs-lookup"><span data-stu-id="96870-113">The following example shows how to create a <xref:System.Windows.Controls.TreeView> where the <xref:System.Windows.Controls.TreeViewItem> content contains <xref:System.Windows.Controls.DockPanel> controls that have embedded content.</span></span>  
  
 [!code-xaml[TreeViewSimple#9](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#9)]  
  
## <a name="see-also"></a><span data-ttu-id="96870-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96870-114">See also</span></span>
- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [<span data-ttu-id="96870-115">Übersicht über TreeView</span><span class="sxs-lookup"><span data-stu-id="96870-115">TreeView Overview</span></span>](treeview-overview.md)
- [<span data-ttu-id="96870-116">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="96870-116">How-to Topics</span></span>](treeview-how-to-topics.md)

---
title: 'Vorgehensweise: Aktivieren der Tile-Ansicht in einem ListView-Steuerelement von Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tile view feature
- tiling
- Windows Forms, controls
- ListView control [Windows Forms], tile view
ms.assetid: c20e67a3-2d94-413d-9fcf-ecbd0fe251da
ms.openlocfilehash: 44d34ddb00005a0fb86b2d06c4c14e2a5b949819
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966679"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control"></a><span data-ttu-id="70ee3-102">Vorgehensweise: Aktivieren der Tile-Ansicht in einem ListView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="70ee3-102">How to: Enable Tile View in a Windows Forms ListView Control</span></span>
<span data-ttu-id="70ee3-103">Mit dem Feature für "Ansicht 'Nebeneinander'" des <xref:System.Windows.Forms.ListView>-Steuerelements können Sie eine visuelle Balance zwischen grafischen und textbasierten Daten herstellen.</span><span class="sxs-lookup"><span data-stu-id="70ee3-103">With the tile view feature of the <xref:System.Windows.Forms.ListView> control, you can provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="70ee3-104">Die textbasierten Daten, die für ein Element in der Ansicht "Nebeneinander" angezeigt werden, sind die gleichen wie die Spalteninformationen, die für die Detailansicht definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="70ee3-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="70ee3-105">Die Ansicht "Nebeneinander" funktioniert in Kombination mit den Features "Gruppieren" oder "Einfügemarke" des <xref:System.Windows.Forms.ListView>-Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="70ee3-105">Tile view works in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 <span data-ttu-id="70ee3-106">Für die Ansicht "Nebeneinander" wird ein 32 x 32 Pixel großes Symbol mit mehreren Textzeilen verwendet, wie in den folgenden Abbildungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="70ee3-106">The tile view uses a 32 x 32 pixel icon and several lines of text, as shown in the following images.</span></span>  
  
 <span data-ttu-id="70ee3-107">![Kachel Ansicht in einem ListView-Steuer] Element (./media/how-to-enable-tile-view-in-a-windows-forms-listview-control/tile-view-in-listview-control.gif "Symbole und Text der Kachel Ansicht")</span><span class="sxs-lookup"><span data-stu-id="70ee3-107">![Tile View in a ListView Control](./media/how-to-enable-tile-view-in-a-windows-forms-listview-control/tile-view-in-listview-control.gif "Tile view icons and text")</span></span>  
 
 <span data-ttu-id="70ee3-108">Um die Ansicht "Nebeneinander" zu aktivieren, legen Sie die <xref:System.Windows.Forms.ListView.View%2A>-Eigenschaft auf <xref:System.Windows.Forms.View.Tile> fest.</span><span class="sxs-lookup"><span data-stu-id="70ee3-108">To enable tile view, set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Tile>.</span></span> <span data-ttu-id="70ee3-109">Sie können die Größe der Kacheln anpassen, indem Sie die <xref:System.Windows.Forms.ListView.TileSize%2A>-Eigenschaft festlegen, und Sie können die Anzahl der angezeigten Textzeilen festlegen, indem Sie die <xref:System.Windows.Forms.ListView.Columns%2A>-Auflistung anpassen.</span><span class="sxs-lookup"><span data-stu-id="70ee3-109">You can adjust the size of the tiles by setting the <xref:System.Windows.Forms.ListView.TileSize%2A> property, and the number of text lines displayed in the tile by adjusting the <xref:System.Windows.Forms.ListView.Columns%2A> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70ee3-110">Die Ansicht "Nebeneinander" steht unter [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] nur zur Verfügung, wenn die Anwendung die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>-Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="70ee3-110">The tile view is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="70ee3-111">Unter älteren Betriebssystemen hat Code in Bezug auf die Ansicht "Nebeneinander" keine Auswirkungen, und das <xref:System.Windows.Forms.ListView>-Steuerelement wird in der Ansicht "Große Symbole" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="70ee3-111">On earlier operating systems, any code related to the tile view has no effect, and the <xref:System.Windows.Forms.ListView> control displays in the large icon view.</span></span> <span data-ttu-id="70ee3-112">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="70ee3-112">For more information, see <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-set-tile-view-programmatically"></a><span data-ttu-id="70ee3-113">So legen Sie die Ansicht "Nebeneinander" programmgesteuert fest</span><span class="sxs-lookup"><span data-stu-id="70ee3-113">To set tile view programmatically</span></span>  
  
1. <span data-ttu-id="70ee3-114">Verwenden Sie die <xref:System.Windows.Forms.View>-Enumeration des <xref:System.Windows.Forms.ListView>-Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="70ee3-114">Use the <xref:System.Windows.Forms.View> enumeration of the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
    ```vb  
    ListView1.View = View.Tile  
    ```  
  
    ```csharp  
    listView1.View = View.Tile;  
    ```  
  
## <a name="example"></a><span data-ttu-id="70ee3-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70ee3-115">Example</span></span>  
 <span data-ttu-id="70ee3-116">Die folgenden vollständigen Codebeispiele zeigen die Ansicht "Nebeneinander" mit Kacheln, die so geändert wurden, dass drei Textzeilen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="70ee3-116">The following complete code example demonstrates Tile view with tiles modified to show three lines of text.</span></span> <span data-ttu-id="70ee3-117">Die Kachelgröße wurde angepasst, um Zeilenumbrüche zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="70ee3-117">The tile size has been adjusted to prevent line-wrapping.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CPP/listviewtilingexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CS/listviewtilingexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/VB/listviewtilingexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="70ee3-118">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="70ee3-118">Compiling the Code</span></span>  
 <span data-ttu-id="70ee3-119">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="70ee3-119">This example requires:</span></span>  
  
- <span data-ttu-id="70ee3-120">Verweise auf die Assemblys "System" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="70ee3-120">References to the System and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="70ee3-121">Eine Symboldatei mit Namen "book.ico", die sich im selben Verzeichnis befinden wie die ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="70ee3-121">An icon file named book.ico in the same directory as the executable file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70ee3-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70ee3-122">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [<span data-ttu-id="70ee3-123">ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="70ee3-123">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="70ee3-124">Übersicht über das ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="70ee3-124">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)

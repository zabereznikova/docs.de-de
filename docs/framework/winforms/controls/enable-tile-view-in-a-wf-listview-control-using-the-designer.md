---
title: 'Vorgehensweise: Aktivieren der Tile-Ansicht in einem ListView-Steuerelement in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: 8a45a8a484bd373f53585b1b113a51e59b30fca2
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040361"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="f8ceb-102">Vorgehensweise: Aktivieren der Tile-Ansicht in einem ListView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="f8ceb-102">How to: Enable Tile View in a Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="f8ceb-103">Mit der Kachel Ansicht des <xref:System.Windows.Forms.ListView> -Steuer Elements können Sie eine visuelle Balance zwischen grafischen und Textinformationen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f8ceb-103">The tile view feature of the <xref:System.Windows.Forms.ListView> control enables you to provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="f8ceb-104">Die textbasierten Daten, die für ein Element in der Ansicht "Nebeneinander" angezeigt werden, sind die gleichen wie die Spalteninformationen, die für die Detailansicht definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="f8ceb-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="f8ceb-105">Die Kachel Ansicht funktioniert in Kombination mit den Funktionen "Gruppieren" oder " <xref:System.Windows.Forms.ListView> Einfügemarke" im Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f8ceb-105">Tile view functions in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>

 <span data-ttu-id="f8ceb-106">In der Kachel Ansicht werden ein 32 x 32-Symbol und mehrere Textzeilen verwendet, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f8ceb-106">The tile view uses a 32 x 32 icon and several lines of text, as shown in the following image.</span></span>

 <span data-ttu-id="f8ceb-107">![Kachel Ansicht in einem ListView-Steuer] Element (./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Symbole und Text der Kachel Ansicht")</span><span class="sxs-lookup"><span data-stu-id="f8ceb-107">![Tile View in a ListView Control](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Tile view icons and text")</span></span>

 <span data-ttu-id="f8ceb-108">Mit den Eigenschaften und Methoden der Kachel Ansicht können Sie angeben, welche Spalten Felder für die einzelnen Elemente angezeigt werden sollen. Darüber hinaus können Sie die Größe und Darstellung aller Elemente innerhalb eines Kachel Ansichts Fensters gemeinsam steuern.</span><span class="sxs-lookup"><span data-stu-id="f8ceb-108">Tile view properties and methods enable you to specify which column fields to display for each item, and to collectively control the size and appearance of all items within a tile view window.</span></span> <span data-ttu-id="f8ceb-109">Aus Gründen der Übersichtlichkeit ist die erste Textzeile in einer Kachel immer der Name des Elements. Sie kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f8ceb-109">For clarity, the first line of text in a tile is always the item's name; it cannot be changed.</span></span>

 <span data-ttu-id="f8ceb-110">Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, <xref:System.Windows.Forms.ListView> das ein-Steuerelement enthält.</span><span class="sxs-lookup"><span data-stu-id="f8ceb-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="f8ceb-111">Weitere Informationen zum Einrichten eines solchen Projekts finden [Sie unter Gewusst wie: Erstellen Sie ein Windows Forms-](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Anwendungs [Projekt, und Gewusst wie: Fügen Sie Windows Forms](how-to-add-controls-to-windows-forms.md)Steuerelemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="f8ceb-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f8ceb-112">Die Ansicht "Nebeneinander" steht unter [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] nur zur Verfügung, wenn die Anwendung die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>-Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="f8ceb-112">The tile view is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f8ceb-113">Unter älteren Betriebssystemen hat Code in Bezug auf die Ansicht "Nebeneinander" keine Auswirkungen, und das <xref:System.Windows.Forms.ListView>-Steuerelement wird in der Ansicht "Große Symbole" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f8ceb-113">On earlier operating systems, any code related to the tile view has no effect, and the <xref:System.Windows.Forms.ListView> control displays in the large icon view.</span></span> <span data-ttu-id="f8ceb-114">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f8ceb-114">For more information, see <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span></span>

## <a name="to-set-tile-view-in-the-designer"></a><span data-ttu-id="f8ceb-115">So legen Sie die Kachel Ansicht im Designer fest</span><span class="sxs-lookup"><span data-stu-id="f8ceb-115">To set tile view in the designer</span></span>

1. <span data-ttu-id="f8ceb-116">Wählen Sie in Visual Studio das <xref:System.Windows.Forms.ListView> Steuerelement auf dem Formular aus.</span><span class="sxs-lookup"><span data-stu-id="f8ceb-116">In Visual Studio, select the <xref:System.Windows.Forms.ListView> control on your form.</span></span>

2. <span data-ttu-id="f8ceb-117">Wählen Sie im Fenster **Eigenschaften** die Eigenschaft <xref:System.Windows.Forms.ListView.View%2A> aus, und wählen Sie dann die **Kachel**aus.</span><span class="sxs-lookup"><span data-stu-id="f8ceb-117">In the **Properties** window, select the <xref:System.Windows.Forms.ListView.View%2A> property and choose **Tile**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8ceb-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8ceb-118">See also</span></span>

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [<span data-ttu-id="f8ceb-119">Übersicht über das ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f8ceb-119">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)

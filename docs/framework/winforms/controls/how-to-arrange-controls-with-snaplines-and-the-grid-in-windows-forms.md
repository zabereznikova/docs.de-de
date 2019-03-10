---
title: 'Vorgehensweise: Anordnen von Steuerelementen mithilfe der Ausrichtungslinien und des Rasters in Windows Forms'
ms.date: 03/30/2017
f1_keywords:
- GridSize
helpviewer_keywords:
- snap to grid [Windows Forms], Windows Forms Designer
- Windows Forms, grid options in designer
- controls [Windows Forms], aligning
ms.assetid: bb54bce5-880f-4a36-af68-8cf92058dc1c
ms.openlocfilehash: 23a1c850133982c5f0136e4c21e6b73fcb94e887
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716360"
---
# <a name="how-to-arrange-controls-with-snaplines-and-the-grid-in-windows-forms"></a><span data-ttu-id="3e53a-102">Vorgehensweise: Anordnen von Steuerelementen mithilfe der Ausrichtungslinien und des Rasters in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3e53a-102">How to: Arrange Controls with Snaplines and the Grid in Windows Forms</span></span>
<span data-ttu-id="3e53a-103">Verwenden die Layoutfeatures von Visual Studio, können Sie genau steuern, wo die Steuerelemente in einem Formular platziert werden.</span><span class="sxs-lookup"><span data-stu-id="3e53a-103">Using the layout features of Visual Studio, you can precisely direct where controls are placed on a form.</span></span> <span data-ttu-id="3e53a-104">Steuerelemente zu einem Formular hinzugefügt oder verschoben werden, in einem Formular automatisch auf die Zeilen und Spalten von der Windows Forms-Designer-Raster ausgerichtet werden können, oder Ausrichten von Steuerelementen mithilfe der Ausrichtungslinien-Funktion.</span><span class="sxs-lookup"><span data-stu-id="3e53a-104">Controls added to a form or moved on a form can be automatically aligned to the rows and columns of the Windows Forms Designer's grid, or you can align controls by using the snaplines feature.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e53a-105">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="3e53a-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3e53a-106">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3e53a-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3e53a-107">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="3e53a-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-snap-all-controls-to-the-grid"></a><span data-ttu-id="3e53a-108">Um alle Steuerelemente am Raster ausrichten</span><span class="sxs-lookup"><span data-stu-id="3e53a-108">To snap all controls to the grid</span></span>  
  
-   <span data-ttu-id="3e53a-109">Wählen Sie die **SnapToGrid** Layoutmodus im Windows Forms-Designer **Optionen** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="3e53a-109">Select the **SnapToGrid** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="3e53a-110">Weitere Informationen finden Sie unter [Allgemein, Windows Forms-Designer, Optionen (Dialogfeld)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="3e53a-110">For more information, see [General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100)).</span></span> <span data-ttu-id="3e53a-111">Alle Steuerelemente ausrichten jetzt selbst auf die Punkte im Raster.</span><span class="sxs-lookup"><span data-stu-id="3e53a-111">All controls now align themselves along the points on the grid.</span></span>  
  
     <span data-ttu-id="3e53a-112">Sie können einzelne Steuerelemente am Raster ausrichten, indem Sie ihrer Position sperren.</span><span class="sxs-lookup"><span data-stu-id="3e53a-112">You can snap individual controls to the grid by locking them in place.</span></span> <span data-ttu-id="3e53a-113">Allerdings gesperrte, werden nicht verschoben oder geändert.</span><span class="sxs-lookup"><span data-stu-id="3e53a-113">However, while they are locked, they cannot be moved or resized.</span></span> <span data-ttu-id="3e53a-114">Weitere Informationen zum Sperren von Steuerelementen finden Sie unter [Vorgehensweise: Sperren von Steuerelementen für Windows Forms](how-to-lock-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="3e53a-114">For more information about locking controls, see [How to: Lock Controls to Windows Forms](how-to-lock-controls-to-windows-forms.md).</span></span>  
  
### <a name="to-align-controls-using-snaplines"></a><span data-ttu-id="3e53a-115">Zum Ausrichten von Steuerelementen, die mithilfe von Ausrichtungslinien</span><span class="sxs-lookup"><span data-stu-id="3e53a-115">To align controls using snaplines</span></span>  
  
-   <span data-ttu-id="3e53a-116">Wählen Sie die **Ausrichtungslinien** Layoutmodus im Windows Forms-Designer **Optionen** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="3e53a-116">Select the **SnapLines** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="3e53a-117">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="3e53a-117">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span> <span data-ttu-id="3e53a-118">Sie können jetzt mithilfe von Ausrichtungslinien ausrichten und Steuerelemente im Formular anordnen.</span><span class="sxs-lookup"><span data-stu-id="3e53a-118">You can now use snaplines to align and arrange controls on your form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e53a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e53a-119">See also</span></span>
- <span data-ttu-id="3e53a-120">[Allgemein, Windows Forms-Designer, Optionen (Dialogfeld)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3e53a-120">[General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span></span>
- [<span data-ttu-id="3e53a-121">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien</span><span class="sxs-lookup"><span data-stu-id="3e53a-121">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="3e53a-122">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="3e53a-122">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="3e53a-123">Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3e53a-123">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="3e53a-124">Anordnen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3e53a-124">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="3e53a-125">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="3e53a-125">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="3e53a-126">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="3e53a-126">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="3e53a-127">Windows Forms-Steuerelemente nach Funktion</span><span class="sxs-lookup"><span data-stu-id="3e53a-127">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)

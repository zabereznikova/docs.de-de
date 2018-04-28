---
title: 'Gewusst wie: Anordnen von Steuerelementen mithilfe der Ausrichtungslinien und des Rasters in Windows Forms'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- GridSize
helpviewer_keywords:
- snap to grid [Windows Forms], Windows Forms Designer
- Windows Forms, grid options in designer
- controls [Windows Forms], aligning
ms.assetid: bb54bce5-880f-4a36-af68-8cf92058dc1c
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3f7467abe6669b88e1a55851fd745c2dcb56c150
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-arrange-controls-with-snaplines-and-the-grid-in-windows-forms"></a><span data-ttu-id="11ff7-102">Gewusst wie: Anordnen von Steuerelementen mithilfe der Ausrichtungslinien und des Rasters in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="11ff7-102">How to: Arrange Controls with Snaplines and the Grid in Windows Forms</span></span>
<span data-ttu-id="11ff7-103">Verwenden das Layoutfunktionen von Visual Studio, können Sie genau steuern, in die Steuerelemente auf einem Formular platziert werden.</span><span class="sxs-lookup"><span data-stu-id="11ff7-103">Using the layout features of Visual Studio, you can precisely direct where controls are placed on a form.</span></span> <span data-ttu-id="11ff7-104">Steuerelemente zu einem Formular hinzugefügt oder in einem Formular verschoben können automatisch in die Zeilen und Spalten des Rasters für die Windows Forms-Designer ausgerichtet werden oder können Sie Steuerelemente mithilfe von Ausrichtungslinien ausrichten.</span><span class="sxs-lookup"><span data-stu-id="11ff7-104">Controls added to a form or moved on a form can be automatically aligned to the rows and columns of the Windows Forms Designer's grid, or you can align controls by using the snaplines feature.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11ff7-105">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="11ff7-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="11ff7-106">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="11ff7-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="11ff7-107">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="11ff7-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-snap-all-controls-to-the-grid"></a><span data-ttu-id="11ff7-108">Alle Steuerelemente am Raster ausgerichtet werden soll</span><span class="sxs-lookup"><span data-stu-id="11ff7-108">To snap all controls to the grid</span></span>  
  
-   <span data-ttu-id="11ff7-109">Wählen Sie die **SnapToGrid** Layoutmodus in Windows Forms-Designer **Optionen** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="11ff7-109">Select the **SnapToGrid** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="11ff7-110">Weitere Informationen finden Sie unter [Allgemein, Windows Forms-Designer, Optionen (Dialogfeld)](http://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834).</span><span class="sxs-lookup"><span data-stu-id="11ff7-110">For more information, see [General, Windows Forms Designer, Options Dialog Box](http://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834).</span></span> <span data-ttu-id="11ff7-111">Alle Steuerelemente auszurichten selbst jetzt entlang der Punkte im Raster.</span><span class="sxs-lookup"><span data-stu-id="11ff7-111">All controls now align themselves along the points on the grid.</span></span>  
  
     <span data-ttu-id="11ff7-112">Sie können einzelne Steuerelemente am Raster ausrichten, von ihrer Position sperren.</span><span class="sxs-lookup"><span data-stu-id="11ff7-112">You can snap individual controls to the grid by locking them in place.</span></span> <span data-ttu-id="11ff7-113">Jedoch, während sie gesperrt sind, sie können nicht verschoben oder dessen Größe geändert werden.</span><span class="sxs-lookup"><span data-stu-id="11ff7-113">However, while they are locked, they cannot be moved or resized.</span></span> <span data-ttu-id="11ff7-114">Weitere Informationen zum Sperren von Steuerelementen finden Sie unter [Vorgehensweise: Sperren von Steuerelementen für Windows Forms](../../../../docs/framework/winforms/controls/how-to-lock-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="11ff7-114">For more information about locking controls, see [How to: Lock Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-lock-controls-to-windows-forms.md).</span></span>  
  
### <a name="to-align-controls-using-snaplines"></a><span data-ttu-id="11ff7-115">Zum Ausrichten von Steuerelementen mithilfe von Ausrichtungslinien</span><span class="sxs-lookup"><span data-stu-id="11ff7-115">To align controls using snaplines</span></span>  
  
-   <span data-ttu-id="11ff7-116">Wählen Sie die **Ausrichtungslinien** Layoutmodus in Windows Forms-Designer **Optionen** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="11ff7-116">Select the **SnapLines** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>  
  
     <span data-ttu-id="11ff7-117">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="11ff7-117">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span> <span data-ttu-id="11ff7-118">Sie können jetzt mithilfe von Ausrichtungslinien ausrichten und Anordnen von Steuerelementen auf dem Formular.</span><span class="sxs-lookup"><span data-stu-id="11ff7-118">You can now use snaplines to align and arrange controls on your form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11ff7-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11ff7-119">See Also</span></span>  
 [<span data-ttu-id="11ff7-120">Allgemein, Windows Forms-Designer, Optionen (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="11ff7-120">General, Windows Forms Designer, Options Dialog Box</span></span>](http://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834)  
 [<span data-ttu-id="11ff7-121">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien</span><span class="sxs-lookup"><span data-stu-id="11ff7-121">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="11ff7-122">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="11ff7-122">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="11ff7-123">Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="11ff7-123">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [<span data-ttu-id="11ff7-124">Anordnen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="11ff7-124">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="11ff7-125">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="11ff7-125">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="11ff7-126">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="11ff7-126">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="11ff7-127">Windows Forms-Steuerelemente nach Funktion</span><span class="sxs-lookup"><span data-stu-id="11ff7-127">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)

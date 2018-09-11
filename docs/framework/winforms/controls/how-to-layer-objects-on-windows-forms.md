---
title: 'Gewusst wie: Überlagern von Objekten in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
ms.openlocfilehash: d67d9b204c316dce5f3818496d791ed4c1b352f2
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44269162"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="b9f57-102">Gewusst wie: Überlagern von Objekten in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b9f57-102">How to: Layer Objects on Windows Forms</span></span>
<span data-ttu-id="b9f57-103">Beim Erstellen einer komplexen Benutzeroberfläche, oder mit einem Formular der multiple Document Interface (MDI) arbeiten, sollten Sie häufig layer-Steuerelemente und untergeordnete Formulare komplexere Benutzeroberflächen (UI) erstellen.</span><span class="sxs-lookup"><span data-stu-id="b9f57-103">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="b9f57-104">Zum Verschieben und das Verfolgen von Steuerelemente und Fenster innerhalb des Kontexts einer Gruppe, bearbeiten Sie die Z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="b9f57-104">To move and keep track of controls and windows within the context of a group, you manipulate their z-order.</span></span> <span data-ttu-id="b9f57-105">*Z-Reihenfolge* ist die Schichtung der Steuerelemente in einem Formular entlang des Formulars z-Achse (Tiefe).</span><span class="sxs-lookup"><span data-stu-id="b9f57-105">*Z-order* is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="b9f57-106">Das Fenster am Anfang der Z-Reihenfolge überschneidet sich mit allen anderen Fenstern.</span><span class="sxs-lookup"><span data-stu-id="b9f57-106">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="b9f57-107">Alle anderen Fenster überlappen, das Fenster am unteren Rand der Z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="b9f57-107">All other windows overlap the window at the bottom of the z-order.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b9f57-108">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="b9f57-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b9f57-109">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b9f57-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b9f57-110">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="b9f57-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="b9f57-111">Auf der Ebene von Steuerelementen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="b9f57-111">To layer controls at design time</span></span>  
  
1.  <span data-ttu-id="b9f57-112">Wählen Sie ein Steuerelement, das Sie überlagern möchten.</span><span class="sxs-lookup"><span data-stu-id="b9f57-112">Select a control that you want to layer.</span></span>  
  
2.  <span data-ttu-id="b9f57-113">Auf der **Format** Startmenü **Reihenfolge**, und klicken Sie dann auf **in den Vordergrund** oder **in den Hintergrund**.</span><span class="sxs-lookup"><span data-stu-id="b9f57-113">On the **Format** menu, point to **Order**, and then click **Bring To Front** or **Send To Back**.</span></span>  
  
### <a name="to-layer-controls-programmatically"></a><span data-ttu-id="b9f57-114">Layer-Steuerelemente programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="b9f57-114">To layer controls programmatically</span></span>  
  
-   <span data-ttu-id="b9f57-115">Verwenden der <xref:System.Windows.Forms.Control.BringToFront%2A> und <xref:System.Windows.Forms.Control.SendToBack%2A> Methoden, um die Z-Anordnung der Steuerelemente ändern.</span><span class="sxs-lookup"><span data-stu-id="b9f57-115">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>  
  
     <span data-ttu-id="b9f57-116">Z. B. wenn ein <xref:System.Windows.Forms.TextBox> Steuerelement `txtFirstName`, wird darunter ein anderes Steuerelement und Sie möchten im Vordergrund soll, verwenden Sie den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="b9f57-116">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>  
  
    ```vb  
    txtFirstName.BringToFront()  
    ```  
  
    ```csharp  
    txtFirstName.BringToFront();  
    ```  
  
    ```cpp  
    txtFirstName->BringToFront();  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="b9f57-117">Windows Forms unterstützt *steuerelementkapselung*.</span><span class="sxs-lookup"><span data-stu-id="b9f57-117">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="b9f57-118">Steuerelementkapselung umfasst eine Reihe von Steuerelementen in einem enthaltenden Steuerelement, z. B. eine Anzahl von platzieren <xref:System.Windows.Forms.RadioButton> -Steuerelementen innerhalb einer <xref:System.Windows.Forms.GroupBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b9f57-118">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="b9f57-119">Sie können dann die Steuerelemente innerhalb des enthaltenden Steuerelements zusätzliche.</span><span class="sxs-lookup"><span data-stu-id="b9f57-119">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="b9f57-120">Die Steuerelemente, verschieben das Gruppenfeld verschoben werden, da sie darin enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b9f57-120">Moving the group box moves the controls as well, because they are contained inside it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9f57-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9f57-121">See Also</span></span>  
 [<span data-ttu-id="b9f57-122">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="b9f57-122">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="b9f57-123">Anordnen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b9f57-123">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="b9f57-124">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="b9f57-124">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="b9f57-125">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="b9f57-125">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="b9f57-126">Windows Forms-Steuerelemente nach Funktion</span><span class="sxs-lookup"><span data-stu-id="b9f57-126">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)

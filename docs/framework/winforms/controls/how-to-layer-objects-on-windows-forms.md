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
ms.openlocfilehash: 1a2a25f2e7eaa6618c0bf535a34f7dc6a28d51fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533685"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="b563d-102">Gewusst wie: Überlagern von Objekten in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b563d-102">How to: Layer Objects on Windows Forms</span></span>
<span data-ttu-id="b563d-103">Wenn Sie eine komplexe Benutzeroberfläche erstellen oder mit einem Formular der multiple Document Interface (MDI arbeiten), sollten Sie häufig überlagern Sie die Steuerelemente und untergeordnete Formulare komplexere Benutzeroberflächen (UI) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b563d-103">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="b563d-104">Zum Verschieben und das Verfolgen von Steuerelemente und Fenster innerhalb des Kontexts einer Gruppe, bearbeiten Sie ihre Z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="b563d-104">To move and keep track of controls and windows within the context of a group, you manipulate their z-order.</span></span> <span data-ttu-id="b563d-105">*Z-Reihenfolge* ist die Schichtung der Steuerelemente in einem Formular auf das Formular z-Achse (Tiefe).</span><span class="sxs-lookup"><span data-stu-id="b563d-105">*Z-order* is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="b563d-106">Das Fenster am Anfang der Z-Reihenfolge überschneidet sich mit allen anderen Fenstern.</span><span class="sxs-lookup"><span data-stu-id="b563d-106">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="b563d-107">Alle überlappen anderen Fenster am unteren Rand der Z-Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="b563d-107">All other windows overlap the window at the bottom of the z-order.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b563d-108">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="b563d-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b563d-109">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b563d-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b563d-110">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="b563d-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="b563d-111">Auf Ebene-Steuerelementen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="b563d-111">To layer controls at design time</span></span>  
  
1.  <span data-ttu-id="b563d-112">Wählen Sie ein Steuerelement an die gewünschte Ebene.</span><span class="sxs-lookup"><span data-stu-id="b563d-112">Select a control that you want to layer.</span></span>  
  
2.  <span data-ttu-id="b563d-113">Auf der **Format** Sie im Menü **Reihenfolge**, und klicken Sie dann auf **in den Vordergrund** oder **in den Hintergrund**.</span><span class="sxs-lookup"><span data-stu-id="b563d-113">On the **Format** menu, point to **Order**, and then click **Bring To Front** or **Send To Back**.</span></span>  
  
### <a name="to-layer-controls-programmatically"></a><span data-ttu-id="b563d-114">Layer-Steuerelemente programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="b563d-114">To layer controls programmatically</span></span>  
  
-   <span data-ttu-id="b563d-115">Verwenden der <xref:System.Windows.Forms.Control.BringToFront%2A> und <xref:System.Windows.Forms.Control.SendToBack%2A> Methoden, um die Z-Reihenfolge der Steuerelemente zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="b563d-115">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>  
  
     <span data-ttu-id="b563d-116">Z. B. wenn ein <xref:System.Windows.Forms.TextBox> Steuerelement `txtFirstName`, wird unter einem anderen Steuerelement und möchten es im Vordergrund, verwenden Sie den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="b563d-116">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>  
  
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
>  <span data-ttu-id="b563d-117">Windows Forms unterstützt *steuern Containment*.</span><span class="sxs-lookup"><span data-stu-id="b563d-117">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="b563d-118">Steuerelementcontainern umfasst eine Reihe von Steuerelementen in einem enthaltenden Steuerelement, z. B. eine Anzahl von platzieren <xref:System.Windows.Forms.RadioButton> steuert innerhalb einer <xref:System.Windows.Forms.GroupBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b563d-118">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="b563d-119">Sie können dann die Steuerelemente innerhalb des enthaltenden Steuerelements Ebene.</span><span class="sxs-lookup"><span data-stu-id="b563d-119">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="b563d-120">Das Gruppenfeld verschieben, die Steuerelemente auch, da sie darin enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b563d-120">Moving the group box moves the controls as well, because they are contained inside it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b563d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b563d-121">See Also</span></span>  
 [<span data-ttu-id="b563d-122">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="b563d-122">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="b563d-123">Anordnen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b563d-123">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="b563d-124">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="b563d-124">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="b563d-125">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="b563d-125">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="b563d-126">Windows Forms-Steuerelemente nach Funktion</span><span class="sxs-lookup"><span data-stu-id="b563d-126">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)

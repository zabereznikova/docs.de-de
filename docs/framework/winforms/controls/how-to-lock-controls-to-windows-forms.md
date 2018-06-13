---
title: 'Gewusst wie: Sperren von Steuerelementen für Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
ms.openlocfilehash: f05da53f134f13bf5edbbe7ab8c5973f79bbca4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534744"
---
# <a name="how-to-lock-controls-to-windows-forms"></a><span data-ttu-id="887d2-102">Gewusst wie: Sperren von Steuerelementen für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="887d2-102">How to: Lock Controls to Windows Forms</span></span>
<span data-ttu-id="887d2-103">Wenn Sie die Benutzeroberfläche (UI) von der Windows-Anwendung entwerfen, können Sie die Steuerelemente sperren, sobald sie ordnungsgemäß positioniert sind, sodass Sie nicht versehentlich verschieben oder deren Größe ändern, wenn Sie andere Eigenschaften festlegen.</span><span class="sxs-lookup"><span data-stu-id="887d2-103">When you design the user interface (UI) of your Windows application, you can lock the controls once they are positioned correctly, so that you do not inadvertently move or resize them when setting other properties.</span></span>  
  
 <span data-ttu-id="887d2-104">Darüber hinaus können Sie sperren und entsperren Sie alle Steuerelemente im Formular gleichzeitig, was für Formulare mit vielen Steuerelementen hilfreich ist, oder Sie einzelne Steuerelemente entsperren.</span><span class="sxs-lookup"><span data-stu-id="887d2-104">Additionally, you can lock and unlock all the controls on the form at once, which is helpful for forms with many controls, or you can unlock individual controls.</span></span> <span data-ttu-id="887d2-105">Nachdem Sie alle Steuerelemente platziert haben, möchten Sie sie auf dem Formular, Sperren Sie diese um fehlerhafte Bewegung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="887d2-105">Once you have placed all the controls where you want them on the form, lock them all in place to prevent erroneous movement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="887d2-106">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="887d2-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="887d2-107">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="887d2-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="887d2-108">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="887d2-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-lock-a-control"></a><span data-ttu-id="887d2-109">So sperren Sie ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="887d2-109">To lock a control</span></span>  
  
1.  <span data-ttu-id="887d2-110">In der **Eigenschaften** Fenster, klicken Sie auf die **gesperrt** Eigenschaft, und wählen `true`.</span><span class="sxs-lookup"><span data-stu-id="887d2-110">In the **Properties** window, click the **Locked** property and select `true`.</span></span> <span data-ttu-id="887d2-111">(Doppelklicken auf den Namen wird die Einstellung der Eigenschaft.)</span><span class="sxs-lookup"><span data-stu-id="887d2-111">(Double-clicking the name toggles the property setting.)</span></span>  
  
     <span data-ttu-id="887d2-112">Alternativ können Sie mit der rechten Maustaste in des Steuerelements, und wählen Sie **Steuerelemente sperren**.</span><span class="sxs-lookup"><span data-stu-id="887d2-112">Alternatively, right-click the control and choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="887d2-113">Sperren von Steuerelementen, die sie zu einer neuen Größe oder Position auf der Entwurfsoberfläche gezogenen verhindert.</span><span class="sxs-lookup"><span data-stu-id="887d2-113">Locking controls prevents them from being dragged to a new size or location on the design surface.</span></span> <span data-ttu-id="887d2-114">Sie können jedoch immer noch ändern die Größe oder Position von Steuerelementen mithilfe von der **Eigenschaften** Fenster oder im Code.</span><span class="sxs-lookup"><span data-stu-id="887d2-114">However, you can still change the size or location of controls by means of the **Properties** window or in code.</span></span>  
  
### <a name="to-lock-all-the-controls-on-a-form"></a><span data-ttu-id="887d2-115">So sperren Sie alle Steuerelemente in einem Formular</span><span class="sxs-lookup"><span data-stu-id="887d2-115">To lock all the controls on a form</span></span>  
  
1.  <span data-ttu-id="887d2-116">Aus der **Format** Menü wählen **Steuerelemente sperren**.</span><span class="sxs-lookup"><span data-stu-id="887d2-116">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="887d2-117">Mit diesem Befehl wird auch die Größe des Formulars gesperrt, da ein Formular ein Steuerelement handelt.</span><span class="sxs-lookup"><span data-stu-id="887d2-117">This command locks the form's size as well, because a form is a control.</span></span>  
  
### <a name="to-unlock-all-locked-controls-on-a-form"></a><span data-ttu-id="887d2-118">Gesperrt, um alle Steuerelemente in einem Formular</span><span class="sxs-lookup"><span data-stu-id="887d2-118">To unlock all locked controls on a form</span></span>  
  
1.  <span data-ttu-id="887d2-119">Aus der **Format** Menü wählen **Steuerelemente sperren**.</span><span class="sxs-lookup"><span data-stu-id="887d2-119">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
     <span data-ttu-id="887d2-120">Alle zuvor gesperrten Steuerelemente im Formular sind jetzt entsperrt.</span><span class="sxs-lookup"><span data-stu-id="887d2-120">All previously locked controls on the form are now unlocked.</span></span>  
  
### <a name="to-unlock-locked-controls-individually"></a><span data-ttu-id="887d2-121">Zum Entsperren Steuerelemente einzeln gesperrt werden</span><span class="sxs-lookup"><span data-stu-id="887d2-121">To unlock locked controls individually</span></span>  
  
1.  <span data-ttu-id="887d2-122">In der **Eigenschaften** Fenster, klicken Sie auf die **gesperrt** Eigenschaft, und wählen `false`.</span><span class="sxs-lookup"><span data-stu-id="887d2-122">In the **Properties** window, click the **Locked** property and select `false`.</span></span> <span data-ttu-id="887d2-123">(Doppelklicken auf den Namen wird die Einstellung der Eigenschaft.)</span><span class="sxs-lookup"><span data-stu-id="887d2-123">(Double-clicking the name toggles the property setting.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="887d2-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="887d2-124">See Also</span></span>  
 [<span data-ttu-id="887d2-125">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="887d2-125">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="887d2-126">Anordnen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="887d2-126">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="887d2-127">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="887d2-127">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="887d2-128">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="887d2-128">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="887d2-129">Windows Forms-Steuerelemente nach Funktion</span><span class="sxs-lookup"><span data-stu-id="887d2-129">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)

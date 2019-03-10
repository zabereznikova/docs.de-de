---
title: 'Vorgehensweise: Steuerelemente Sperren zu Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
ms.openlocfilehash: cff3b0a3ba547c15e7b1c896bde49931a6a3c742
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702645"
---
# <a name="how-to-lock-controls-to-windows-forms"></a><span data-ttu-id="5935e-102">Vorgehensweise: Steuerelemente Sperren zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5935e-102">How to: Lock Controls to Windows Forms</span></span>
<span data-ttu-id="5935e-103">Wenn Sie die Benutzeroberfläche (UI) Ihrer Windows-Anwendung entwerfen, können Sie die Steuerelemente sperren, sobald sie die richtige Position sind, damit Sie nicht versehentlich zu verschieben oder deren Größe ändern, wenn Sie andere Eigenschaften festlegen.</span><span class="sxs-lookup"><span data-stu-id="5935e-103">When you design the user interface (UI) of your Windows application, you can lock the controls once they are positioned correctly, so that you do not inadvertently move or resize them when setting other properties.</span></span>  
  
 <span data-ttu-id="5935e-104">Darüber hinaus sperren und entsperren Sie alle Steuerelemente im Formular gleichzeitig angezeigt werden, die bei Formularen mit zahlreichen Steuerelementen hilfreich sind, oder Sie können einzelne Steuerelemente entsperren.</span><span class="sxs-lookup"><span data-stu-id="5935e-104">Additionally, you can lock and unlock all the controls on the form at once, which is helpful for forms with many controls, or you can unlock individual controls.</span></span> <span data-ttu-id="5935e-105">Nachdem Sie alle Steuerelemente platziert haben, Sie möchten diese auf dem Formular, Sperren Sie diese um fehlerhafte Bewegung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="5935e-105">Once you have placed all the controls where you want them on the form, lock them all in place to prevent erroneous movement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5935e-106">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="5935e-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5935e-107">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5935e-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5935e-108">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="5935e-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-lock-a-control"></a><span data-ttu-id="5935e-109">Um ein Steuerelement zu sperren.</span><span class="sxs-lookup"><span data-stu-id="5935e-109">To lock a control</span></span>  
  
1.  <span data-ttu-id="5935e-110">In der **Eigenschaften** Fenster, klicken Sie auf die **gesperrt** Eigenschaft, und wählen `true`.</span><span class="sxs-lookup"><span data-stu-id="5935e-110">In the **Properties** window, click the **Locked** property and select `true`.</span></span> <span data-ttu-id="5935e-111">(Mit durch Doppelklicken auf den Namen wird die Einstellung der Eigenschaft.)</span><span class="sxs-lookup"><span data-stu-id="5935e-111">(Double-clicking the name toggles the property setting.)</span></span>  
  
     <span data-ttu-id="5935e-112">Alternativ klicken Sie auf das Steuerelement, und wählen Sie **Steuerelemente sperren**.</span><span class="sxs-lookup"><span data-stu-id="5935e-112">Alternatively, right-click the control and choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5935e-113">Steuerelemente Sperren verhindert werden, die auf eine neue Größe oder Position auf der Entwurfsoberfläche gezogen wird.</span><span class="sxs-lookup"><span data-stu-id="5935e-113">Locking controls prevents them from being dragged to a new size or location on the design surface.</span></span> <span data-ttu-id="5935e-114">Sie können jedoch weiterhin ändern die Größe oder Position der Steuerelemente von der **Eigenschaften** Fenster oder im Code.</span><span class="sxs-lookup"><span data-stu-id="5935e-114">However, you can still change the size or location of controls by means of the **Properties** window or in code.</span></span>  
  
### <a name="to-lock-all-the-controls-on-a-form"></a><span data-ttu-id="5935e-115">Um alle Steuerelemente in einem Formular zu sperren.</span><span class="sxs-lookup"><span data-stu-id="5935e-115">To lock all the controls on a form</span></span>  
  
1.  <span data-ttu-id="5935e-116">Von der **Format** Menü wählen **Steuerelemente sperren**.</span><span class="sxs-lookup"><span data-stu-id="5935e-116">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5935e-117">Mit diesem Befehl sperrt auch die Größe des Formulars auf, da ein Formular ein Steuerelement handelt.</span><span class="sxs-lookup"><span data-stu-id="5935e-117">This command locks the form's size as well, because a form is a control.</span></span>  
  
### <a name="to-unlock-all-locked-controls-on-a-form"></a><span data-ttu-id="5935e-118">Um alle gesperrten Steuerelemente in einem Formular zu entsperren.</span><span class="sxs-lookup"><span data-stu-id="5935e-118">To unlock all locked controls on a form</span></span>  
  
1.  <span data-ttu-id="5935e-119">Von der **Format** Menü wählen **Steuerelemente sperren**.</span><span class="sxs-lookup"><span data-stu-id="5935e-119">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
     <span data-ttu-id="5935e-120">Alle zuvor gesperrten Steuerelemente im Formular sind jetzt entsperrt.</span><span class="sxs-lookup"><span data-stu-id="5935e-120">All previously locked controls on the form are now unlocked.</span></span>  
  
### <a name="to-unlock-locked-controls-individually"></a><span data-ttu-id="5935e-121">Um gesperrte Steuerelemente einzeln zu entsperren.</span><span class="sxs-lookup"><span data-stu-id="5935e-121">To unlock locked controls individually</span></span>  
  
1.  <span data-ttu-id="5935e-122">In der **Eigenschaften** Fenster, klicken Sie auf die **gesperrt** Eigenschaft, und wählen `false`.</span><span class="sxs-lookup"><span data-stu-id="5935e-122">In the **Properties** window, click the **Locked** property and select `false`.</span></span> <span data-ttu-id="5935e-123">(Mit durch Doppelklicken auf den Namen wird die Einstellung der Eigenschaft.)</span><span class="sxs-lookup"><span data-stu-id="5935e-123">(Double-clicking the name toggles the property setting.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5935e-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5935e-124">See also</span></span>
- [<span data-ttu-id="5935e-125">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="5935e-125">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="5935e-126">Anordnen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5935e-126">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="5935e-127">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="5935e-127">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="5935e-128">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="5935e-128">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="5935e-129">Windows Forms-Steuerelemente nach Funktion</span><span class="sxs-lookup"><span data-stu-id="5935e-129">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)

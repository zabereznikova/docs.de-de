---
title: 'Vorgehensweise: Definieren einer Windows Forms-Schaltfläche als „Abbrechen“-Schaltfläche mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: be0847d1837ec85ed9d82dc7cc879d0cffa19cd6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156220"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a><span data-ttu-id="21dae-102">Vorgehensweise: Definieren einer Windows Forms-Schaltfläche als „Abbrechen“-Schaltfläche mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="21dae-102">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>
<span data-ttu-id="21dae-103">Auf jedem Windows-Formular, Sie können festlegen, eine <xref:System.Windows.Forms.Button> Steuerelement die Schaltfläche "Abbrechen".</span><span class="sxs-lookup"><span data-stu-id="21dae-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="21dae-104">Schaltfläche "Abbrechen" geklickt wird, wenn der Benutzer die ESC-Taste drückt, unabhängig davon, die welche anderen Formular auf das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="21dae-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="21dae-105">Eine solche Schaltfläche programmiert wird in der Regel dem Benutzer ermöglichen, schnell einen Vorgang beendet, ohne dass eine Aktion.</span><span class="sxs-lookup"><span data-stu-id="21dae-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21dae-106">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="21dae-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="21dae-107">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="21dae-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="21dae-108">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="21dae-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="21dae-109">Um die Schaltfläche "Abbrechen" zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="21dae-109">To designate the cancel button</span></span>  
  
1.  <span data-ttu-id="21dae-110">Wählen Sie das Formular, das auf dem sich die Schaltfläche befindet.</span><span class="sxs-lookup"><span data-stu-id="21dae-110">Select the form on which the button resides.</span></span>  
  
2.  <span data-ttu-id="21dae-111">In der **Eigenschaften** legen des Formulars <xref:System.Windows.Forms.Form.CancelButton%2A> Eigenschaft, um die <xref:System.Windows.Forms.Button> Name des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="21dae-111">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21dae-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21dae-112">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="21dae-113">Übersicht über das Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="21dae-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="21dae-114">Methoden zur Auswahl eines Button-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="21dae-114">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="21dae-115">Vorgehensweise: Reagieren auf das Anklicken von Schaltflächen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="21dae-115">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="21dae-116">Vorgehensweise: Definieren einer Windows Forms-Schaltfläche als „Annehmen“-Schaltfläche mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="21dae-116">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [<span data-ttu-id="21dae-117">Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="21dae-117">Button Control</span></span>](button-control-windows-forms.md)

---
title: 'Gewusst wie: Definieren einer Windows Forms-Schaltfläche als "Abbrechen"-Schaltfläche mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: e94553a31ecdbf325c12815aa7a782cb68b95f19
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526138"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a><span data-ttu-id="72a51-102">Gewusst wie: Definieren einer Windows Forms-Schaltfläche als "Abbrechen"-Schaltfläche mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="72a51-102">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>
<span data-ttu-id="72a51-103">Auf jedem Windows-Formular, legen Sie eine <xref:System.Windows.Forms.Button> Steuerelement die Schaltfläche "Abbrechen" befinden.</span><span class="sxs-lookup"><span data-stu-id="72a51-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="72a51-104">Eine Schaltfläche "Abbrechen" geklickt wird, wenn der Benutzer die ESC-Taste drückt, unabhängig davon, die welche anderen Formular auf das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="72a51-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="72a51-105">Eine solche Schaltfläche programmiert wird in der Regel dem Benutzer ermöglichen, schnell einen Vorgang zu beenden, ohne dass auf eine beliebige Aktion.</span><span class="sxs-lookup"><span data-stu-id="72a51-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72a51-106">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="72a51-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="72a51-107">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="72a51-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="72a51-108">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="72a51-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="72a51-109">Die Schaltfläche "Abbrechen" festlegen</span><span class="sxs-lookup"><span data-stu-id="72a51-109">To designate the cancel button</span></span>  
  
1.  <span data-ttu-id="72a51-110">Wählen Sie das Formular, das auf dem sich die Schaltfläche befindet.</span><span class="sxs-lookup"><span data-stu-id="72a51-110">Select the form on which the button resides.</span></span>  
  
2.  <span data-ttu-id="72a51-111">In der **Eigenschaften** fest des Formulars <xref:System.Windows.Forms.Form.CancelButton%2A> Eigenschaft, um die <xref:System.Windows.Forms.Button> der Name des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="72a51-111">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72a51-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72a51-112">See Also</span></span>  
 <xref:System.Windows.Forms.Form.CancelButton%2A>  
 [<span data-ttu-id="72a51-113">Übersicht über das Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="72a51-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="72a51-114">Methoden zur Auswahl eines Button-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="72a51-114">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="72a51-115">Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="72a51-115">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="72a51-116">Gewusst wie: Festlegen eine Windows Forms-Schaltfläche als "Annehmen"-Schaltfläche mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="72a51-116">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)  
 [<span data-ttu-id="72a51-117">Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="72a51-117">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)

---
title: "Gewusst wie: Definieren einer Windows Forms-Schaltfläche als \"Annehmen\"-Schaltfläche mithilfe des Designers"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: be2fe788be4aeaa2e8eccaaf539a08b076f2da01
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a><span data-ttu-id="2ac1c-102">Gewusst wie: Definieren einer Windows Forms-Schaltfläche als "Annehmen"-Schaltfläche mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="2ac1c-102">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>
<span data-ttu-id="2ac1c-103">Auf jedem Windows-Formular, legen Sie eine <xref:System.Windows.Forms.Button> Steuerelement Bestätigungsschaltfläche, auch bekannt als Standardschaltfläche befinden.</span><span class="sxs-lookup"><span data-stu-id="2ac1c-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="2ac1c-104">Wenn der Benutzer die EINGABETASTE drückt, wird die Standardschaltfläche geklickt haben, unabhängig davon, welche anderen Formular auf das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="2ac1c-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="2ac1c-105">Die Ausnahmen, wenn das Steuerelement den Fokus besitzt eine weitere Schaltfläche ist an diesem – in diesem Fall wird die Schaltfläche mit den Fokus geklickt werden – oder ein mehrzeiliges Textfeld oder ein benutzerdefiniertes Steuerelement, das die EINGABETASTE aufgefangen.</span><span class="sxs-lookup"><span data-stu-id="2ac1c-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ac1c-106">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="2ac1c-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="2ac1c-107">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2ac1c-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="2ac1c-108">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="2ac1c-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="2ac1c-109">Die Schaltfläche "Annehmen" festlegen</span><span class="sxs-lookup"><span data-stu-id="2ac1c-109">To designate the accept button</span></span>  
  
1.  <span data-ttu-id="2ac1c-110">Wählen Sie das Formular, das auf dem sich die Schaltfläche befindet.</span><span class="sxs-lookup"><span data-stu-id="2ac1c-110">Select the form on which the button resides.</span></span>  
  
2.  <span data-ttu-id="2ac1c-111">In der **Eigenschaften** fest des Formulars <xref:System.Windows.Forms.Form.AcceptButton%2A> Eigenschaft, um die <xref:System.Windows.Forms.Button> der Name des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="2ac1c-111">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ac1c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ac1c-112">See Also</span></span>  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>  
 [<span data-ttu-id="2ac1c-113">Übersicht über das Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2ac1c-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="2ac1c-114">Methoden zur Auswahl eines Button-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ac1c-114">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="2ac1c-115">Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ac1c-115">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="2ac1c-116">Gewusst wie: Definieren einer Windows Forms-Schaltfläche als "Abbrechen"-Schaltfläche mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="2ac1c-116">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)  
 [<span data-ttu-id="2ac1c-117">Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2ac1c-117">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)

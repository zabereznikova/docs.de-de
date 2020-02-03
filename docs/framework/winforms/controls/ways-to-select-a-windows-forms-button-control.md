---
title: Möglichkeiten zum Auswählen eines Schaltflächen-Steuer Elements
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: 145166d182f1ec51068ab3e0c23c12b471b69231
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740003"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a><span data-ttu-id="7fd72-102">Methoden zur Auswahl eines Button-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7fd72-102">Ways to Select a Windows Forms Button Control</span></span>
<span data-ttu-id="7fd72-103">Eine Schaltfläche "Windows Forms" kann auf folgende Weise ausgewählt werden:</span><span class="sxs-lookup"><span data-stu-id="7fd72-103">A Windows Forms button can be selected in the following ways:</span></span>  
  
- <span data-ttu-id="7fd72-104">Klicken Sie mit der Maus auf die Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="7fd72-104">Use a mouse to click the button.</span></span>  
  
- <span data-ttu-id="7fd72-105">Rufen Sie das <xref:System.Windows.Forms.Control.Click>-Ereignis der Schaltfläche im Code auf.</span><span class="sxs-lookup"><span data-stu-id="7fd72-105">Invoke the button's <xref:System.Windows.Forms.Control.Click> event in code.</span></span>  
  
- <span data-ttu-id="7fd72-106">Verschieben Sie den Fokus auf die Schaltfläche, indem Sie die Tab-Taste drücken, und wählen Sie dann die Schaltfläche durch Drücken der Leertaste oder EINGABETASTE aus.</span><span class="sxs-lookup"><span data-stu-id="7fd72-106">Move the focus to the button by pressing the TAB key, and then choose the button by pressing the SPACEBAR or ENTER.</span></span>  
  
- <span data-ttu-id="7fd72-107">Drücken Sie die Zugriffstaste (alt + den unterstrichenen Buchstaben) für die Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="7fd72-107">Press the access key (ALT + the underlined letter) for the button.</span></span> <span data-ttu-id="7fd72-108">Weitere Informationen zu Zugriffs Schlüsseln finden Sie unter Gewusst [wie: Erstellen von Zugriffs Schlüsseln für Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md)-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="7fd72-108">For more information about access keys, see [How to: Create Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
- <span data-ttu-id="7fd72-109">Wenn die Schaltfläche die "Accept"-Schaltfläche des Formulars ist, wählt durch Drücken der EINGABETASTE die Schaltfläche aus. Dies gilt auch dann, wenn ein anderes Steuerelement den Fokus besitzt – es sei denn, das andere Steuerelement ist eine andere Schaltfläche, ein mehrzeilige Textfeld oder ein benutzerdefiniertes Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7fd72-109">If the button is the "accept" button of the form, pressing ENTER chooses the button, even if another control has the focus — except if that other control is another button, a multi-line text box, or a custom control that traps the enter key.</span></span>  
  
- <span data-ttu-id="7fd72-110">Wenn die Schaltfläche die Schaltfläche "Abbrechen" im Formular ist, wählt die Taste ESC die Schaltfläche aus, auch wenn ein anderes Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="7fd72-110">If the button is the "cancel" button of the form, pressing ESC chooses the button, even if another control has the focus.</span></span>  
  
- <span data-ttu-id="7fd72-111">Ruft die <xref:System.Windows.Forms.Button.PerformClick%2A>-Methode auf, um die Schaltfläche Programm gesteuert auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="7fd72-111">Call the <xref:System.Windows.Forms.Button.PerformClick%2A> method to select the button programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fd72-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7fd72-112">See also</span></span>

- [<span data-ttu-id="7fd72-113">Übersicht über das Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7fd72-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="7fd72-114">Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7fd72-114">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="7fd72-115">Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7fd72-115">Button Control</span></span>](button-control-windows-forms.md)

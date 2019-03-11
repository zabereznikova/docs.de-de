---
title: 'Vorgehensweise: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente, die mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
ms.openlocfilehash: 3d4112d87dbd448c7e34d2b84d11b49f56e1dc44
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713344"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a><span data-ttu-id="c8c65-102">Vorgehensweise: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente, die mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="c8c65-102">How to: Create Access Keys for Windows Forms Controls Using the Designer</span></span>
<span data-ttu-id="c8c65-103">Ein *Zugriffsschlüssel* ist ein unterstrichenes Zeichen im Text eines Menüs, Menüelement oder die Bezeichnung eines Steuerelements wie einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="c8c65-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="c8c65-104">Dadurch wird den Benutzer auf eine Schaltfläche "klicken", durch Drücken der ALT-Taste in Kombination mit dem vordefinierten Zugriffsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="c8c65-104">It enables the user to "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="c8c65-105">Angenommen, eine Schaltfläche eine Prozedur zum Drucken eines Formulars ausgeführt wird und daher seine `Text` -Eigenschaftensatz "Print", ein kaufmännisches und-Zeichen (&) vor dem Buchstaben "P" bewirkt, die Buchstaben "P dass" unterstrichen werden in den Text der Schaltfläche zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="c8c65-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand (&) before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="c8c65-106">Der Benutzer kann den Befehl mit der Schaltfläche durch Drücken von ALT + P verknüpften ausführen.</span><span class="sxs-lookup"><span data-stu-id="c8c65-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="c8c65-107">Sie keine Zugriffstaste für ein Steuerelement, die keinen Fokus erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="c8c65-107">You cannot have an access key for a control that cannot receive focus.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8c65-108">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="c8c65-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c8c65-109">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c8c65-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c8c65-110">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="c8c65-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="c8c65-111">Um einen Zugriffsschlüssel für ein Steuerelement zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c8c65-111">To create an access key for a control</span></span>  
  
1.  <span data-ttu-id="c8c65-112">In der **Eigenschaften** legen die `Text` Eigenschaft eine Zeichenfolge, die ein kaufmännisches und-Zeichen (&) vor dem Buchstaben, die den Zugriffsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="c8c65-112">In the **Properties** window, set the `Text` property to a string that includes an ampersand (&) before the letter that will be the access key.</span></span> <span data-ttu-id="c8c65-113">Geben Sie den Buchstaben "P" als Zugriffstaste festlegen, z. B. **& Drucken** in das Raster.</span><span class="sxs-lookup"><span data-stu-id="c8c65-113">For example, to set the letter "P" as the access key, type **&Print** into the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8c65-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8c65-114">See also</span></span>
- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="c8c65-115">Vorgehensweise: Reagieren Sie auf eine Windows Forms-Schaltfläche geklickt</span><span class="sxs-lookup"><span data-stu-id="c8c65-115">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="c8c65-116">Vorgehensweise: Legen Sie den Text von einer Windows Forms-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c8c65-116">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="c8c65-117">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="c8c65-117">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)

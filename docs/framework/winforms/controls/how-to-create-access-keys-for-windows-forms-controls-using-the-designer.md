---
title: "Gewusst wie: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente mithilfe des Designers"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 19c47c21526ca6e7aa4046a1853f3d1743438d17
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a><span data-ttu-id="ccafa-102">Gewusst wie: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="ccafa-102">How to: Create Access Keys for Windows Forms Controls Using the Designer</span></span>
<span data-ttu-id="ccafa-103">Ein *Zugriffsschlüssel* ist ein unterstrichenes Zeichen im Text eines Menüs, Menüelements oder die Bezeichnung eines Steuerelements, z. B. eine Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="ccafa-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="ccafa-104">Er ermöglicht es dem Benutzer eine Schaltfläche "auf", durch Drücken der ALT-Taste in Kombination mit den vordefinierten Zugriffsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="ccafa-104">It enables the user to "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="ccafa-105">Angenommen, eine Schaltfläche eine Prozedur zum Drucken eines Formulars ausgeführt wird und daher seine `Text` Eigenschaft "Print", Hinzufügen von ein kaufmännisches und-Zeichen (&) vor dem Buchstaben "P" bewirkt, der Buchstabe "P dass" unterstrichen werden in den Text der Schaltfläche zur Laufzeit festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ccafa-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand (&) before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="ccafa-106">Der Benutzer kann die Schaltfläche mit den durch Drücken von ALT + P zugeordneten Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="ccafa-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="ccafa-107">Sie keine Zugriffstaste für ein Steuerelement, die Fokus erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="ccafa-107">You cannot have an access key for a control that cannot receive focus.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ccafa-108">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="ccafa-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ccafa-109">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ccafa-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ccafa-110">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="ccafa-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="ccafa-111">So erstellen eine Zugriffstaste für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ccafa-111">To create an access key for a control</span></span>  
  
1.  <span data-ttu-id="ccafa-112">In der **Eigenschaften** legen die `Text` Eigenschaft eine Zeichenfolge, die ein kaufmännisches und-Zeichen (&) vor dem Buchstaben, die den Zugriffsschlüssel werden.</span><span class="sxs-lookup"><span data-stu-id="ccafa-112">In the **Properties** window, set the `Text` property to a string that includes an ampersand (&) before the letter that will be the access key.</span></span> <span data-ttu-id="ccafa-113">Geben Sie den Buchstaben "P" als Zugriffstaste festlegen, z. B. **& Drucken** in das Raster.</span><span class="sxs-lookup"><span data-stu-id="ccafa-113">For example, to set the letter "P" as the access key, type **&Print** into the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccafa-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ccafa-114">See Also</span></span>  
 <xref:System.Windows.Forms.Button>  
 [<span data-ttu-id="ccafa-115">Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ccafa-115">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="ccafa-116">Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Texts</span><span class="sxs-lookup"><span data-stu-id="ccafa-116">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [<span data-ttu-id="ccafa-117">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="ccafa-117">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)

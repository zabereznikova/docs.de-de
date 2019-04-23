---
title: 'Vorgehensweise: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
ms.openlocfilehash: e6c829553163359301bad2cd896fc43562ee8069
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334457"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a><span data-ttu-id="1d3e3-102">Vorgehensweise: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="1d3e3-102">How to: Create Access Keys for Windows Forms Controls</span></span>
<span data-ttu-id="1d3e3-103">Ein *Zugriffsschlüssel* ist ein unterstrichenes Zeichen im Text eines Menüs, Menüelement oder die Bezeichnung eines Steuerelements wie einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="1d3e3-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="1d3e3-104">Zusammen mit einer Zugriffstaste kann der Benutzer "eine Schaltfläche klicken Sie auf" durch Drücken der ALT-Taste in Kombination mit dem vordefinierten Zugriffsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="1d3e3-104">With an access key, the user can "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="1d3e3-105">Angenommen, eine Schaltfläche eine Prozedur zum Drucken eines Formulars ausführt und daher seine `Text` -Eigenschaftensatz auf "Print", ein kaufmännisches und-Zeichen vor der Buchstaben "P" den Buchstaben "P" in den Text der Schaltfläche unterstrichen werden, zur Laufzeit bewirkt, dass.</span><span class="sxs-lookup"><span data-stu-id="1d3e3-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="1d3e3-106">Der Benutzer kann den Befehl mit der Schaltfläche durch Drücken von ALT + P verknüpften ausführen.</span><span class="sxs-lookup"><span data-stu-id="1d3e3-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="1d3e3-107">Sie keine Zugriffstaste für ein Steuerelement, die keinen Fokus erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="1d3e3-107">You cannot have an access key for a control that cannot receive focus.</span></span>  
  
### <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="1d3e3-108">Um einen Zugriffsschlüssel für ein Steuerelement zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1d3e3-108">To create an access key for a control</span></span>  
  
1. <span data-ttu-id="1d3e3-109">Legen Sie die `Text` Eigenschaft eine Zeichenfolge, die ein kaufmännisches und-Zeichen (&) vor dem Buchstaben, die die Verknüpfung werden.</span><span class="sxs-lookup"><span data-stu-id="1d3e3-109">Set the `Text` property to a string that includes an ampersand (&) before the letter that will be the shortcut.</span></span>  
  
    ```vb  
    ' Set the letter "P" as an access key.  
    Button1.Text = "&Print"  
    ```  
  
    ```csharp  
    // Set the letter "P" as an access key.  
    button1.Text = "&Print";  
    ```  
  
    ```cpp  
    // Set the letter "P" as an access key.  
    button1->Text = "&Print";  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="1d3e3-110">Wenn ein kaufmännisches und-Zeichen in einer Beschriftung einschließen möchten, ohne eine Tastenkombination erstellen, umfassen zwei kaufmännische und-Zeichen (& &).</span><span class="sxs-lookup"><span data-stu-id="1d3e3-110">To include an ampersand in a caption without creating an access key, include two ampersands (&&).</span></span> <span data-ttu-id="1d3e3-111">Ein einzelnes kaufmännisches und-Zeichen in der Beschriftung angezeigt, und es werden keine Zeichen unterstrichen.</span><span class="sxs-lookup"><span data-stu-id="1d3e3-111">A single ampersand is displayed in the caption and no characters are underlined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d3e3-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d3e3-112">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="1d3e3-113">Vorgehensweise: Reagieren Sie auf eine Windows Forms-Schaltfläche geklickt</span><span class="sxs-lookup"><span data-stu-id="1d3e3-113">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="1d3e3-114">Vorgehensweise: Legen Sie den Text von einer Windows Forms-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1d3e3-114">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="1d3e3-115">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="1d3e3-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)

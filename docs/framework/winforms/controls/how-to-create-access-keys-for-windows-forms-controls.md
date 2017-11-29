---
title: "Gewusst wie: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: af4cbcc5dacc4f9a0b5312b67838479bf6817228
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a><span data-ttu-id="af176-102">Gewusst wie: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="af176-102">How to: Create Access Keys for Windows Forms Controls</span></span>
<span data-ttu-id="af176-103">Ein *Zugriffsschlüssel* ist ein unterstrichenes Zeichen im Text eines Menüs, Menüelements oder die Bezeichnung eines Steuerelements, z. B. eine Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="af176-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="af176-104">Mit einer Zugriffstaste kann der Benutzer "eine Schaltfläche klicken" durch Drücken der ALT-Taste in Kombination mit den vordefinierten Zugriffsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="af176-104">With an access key, the user can "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="af176-105">Angenommen, eine Schaltfläche eine Prozedur zum Drucken eines Formulars ausgeführt wird und daher seine `Text` auf "Drucken"-Eigenschaft festgelegt ist, ein kaufmännisches und-Zeichen hinzufügen, bevor der Buchstabe "P" den Buchstaben "P" in den Text der Schaltfläche unterstrichen werden, zur Laufzeit ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="af176-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="af176-106">Der Benutzer kann die Schaltfläche mit den durch Drücken von ALT + P zugeordneten Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="af176-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="af176-107">Sie keine Zugriffstaste für ein Steuerelement, die Fokus erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="af176-107">You cannot have an access key for a control that cannot receive focus.</span></span>  
  
### <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="af176-108">So erstellen eine Zugriffstaste für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="af176-108">To create an access key for a control</span></span>  
  
1.  <span data-ttu-id="af176-109">Legen Sie die `Text` Eigenschaft eine Zeichenfolge, die ein kaufmännisches und-Zeichen (&) vor dem Buchstaben, die die Verknüpfung werden.</span><span class="sxs-lookup"><span data-stu-id="af176-109">Set the `Text` property to a string that includes an ampersand (&) before the letter that will be the shortcut.</span></span>  
  
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
    >  <span data-ttu-id="af176-110">Wenn Sie ein kaufmännisches und-Zeichen in eine Beschriftung einschließen möchten, ohne eine Zugriffstaste zu erstellen, enthalten zwei kaufmännische und-Zeichen (& &).</span><span class="sxs-lookup"><span data-stu-id="af176-110">To include an ampersand in a caption without creating an access key, include two ampersands (&&).</span></span> <span data-ttu-id="af176-111">Ein einzelnes kaufmännisches und-Zeichen in der Beschriftung angezeigt, und keine Zeichen sind unterstrichen.</span><span class="sxs-lookup"><span data-stu-id="af176-111">A single ampersand is displayed in the caption and no characters are underlined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af176-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af176-112">See Also</span></span>  
 <xref:System.Windows.Forms.Button>  
 [<span data-ttu-id="af176-113">Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af176-113">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="af176-114">Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Texts</span><span class="sxs-lookup"><span data-stu-id="af176-114">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [<span data-ttu-id="af176-115">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="af176-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)

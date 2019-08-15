---
title: 'Vorgehensweise: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente mithilfe des Designers'
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
ms.openlocfilehash: 01bed04483702ba2e62162b675aa1138bc1b0e01
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039522"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a><span data-ttu-id="64e7e-102">Vorgehensweise: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="64e7e-102">How to: Create Access Keys for Windows Forms Controls Using the Designer</span></span>
<span data-ttu-id="64e7e-103">Eine *Zugriffstaste* ist ein unterstrichenes Zeichen im Text eines Menüs, Menü Elements oder der Bezeichnung eines Steuer Elements, z. b. einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="64e7e-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="64e7e-104">Dadurch kann der Benutzer auf eine Schaltfläche klicken, indem er die Alt-Taste in Kombination mit der vordefinierten Zugriffstaste drückt.</span><span class="sxs-lookup"><span data-stu-id="64e7e-104">It enables the user to "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="64e7e-105">Wenn z. b. eine Schaltfläche eine Prozedur zum Drucken eines Formulars ausführt und die `Text` -Eigenschaft daher auf "Print" festgelegt ist, wird durch das Hinzufügen eines kaufmännischen und-Zeichens (&) vor dem Buchstaben "p" der Buchstabe "p" im Schaltflächen Text zur Laufzeit unterstrichen.</span><span class="sxs-lookup"><span data-stu-id="64e7e-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand (&) before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="64e7e-106">Der Benutzer kann den Befehl ausführen, der der Schaltfläche zugeordnet ist, indem er alt + P drückt.</span><span class="sxs-lookup"><span data-stu-id="64e7e-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="64e7e-107">Sie können keinen Zugriffsschlüssel für ein Steuerelement haben, das keinen Fokus erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="64e7e-107">You cannot have an access key for a control that cannot receive focus.</span></span>

## <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="64e7e-108">So erstellen Sie einen Zugriffsschlüssel für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="64e7e-108">To create an access key for a control</span></span>

1. <span data-ttu-id="64e7e-109">Legen Sie im Fenster **Eigenschaften** die `Text` -Eigenschaft auf eine Zeichenfolge fest, die ein kaufmännisches und-Zeichen (&) vor dem Buchstaben enthält, der als Zugriffstaste verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="64e7e-109">In the **Properties** window, set the `Text` property to a string that includes an ampersand (&) before the letter that will be the access key.</span></span> <span data-ttu-id="64e7e-110">Wenn Sie z. b. den Buchstaben "P" als Zugriffsschlüssel festlegen möchten, geben Sie **& Drucken** im Raster ein.</span><span class="sxs-lookup"><span data-stu-id="64e7e-110">For example, to set the letter "P" as the access key, type **&Print** into the grid.</span></span>

## <a name="see-also"></a><span data-ttu-id="64e7e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64e7e-111">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="64e7e-112">Vorgehensweise: Antworten auf Windows Forms Schaltflächen Klicks</span><span class="sxs-lookup"><span data-stu-id="64e7e-112">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="64e7e-113">Vorgehensweise: Festlegen des von einem Windows Forms-Steuerelement angezeigten Texts</span><span class="sxs-lookup"><span data-stu-id="64e7e-113">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="64e7e-114">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="64e7e-114">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)

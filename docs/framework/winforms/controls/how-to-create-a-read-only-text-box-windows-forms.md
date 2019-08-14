---
title: 'Vorgehensweise: Erstellen eines schreibgeschützten Textfelds (Windows Forms)'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 18d2f5ed2530957487ac25c3eb6240f8bc50a938
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971944"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a><span data-ttu-id="5e918-102">Vorgehensweise: Erstellen eines schreibgeschützten Textfelds (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5e918-102">How to: Create a Read-Only Text Box (Windows Forms)</span></span>

<span data-ttu-id="5e918-103">Sie können eine bearbeitbare Windows Forms Textfeld in ein Schreib geschütztes Steuerelement umwandeln.</span><span class="sxs-lookup"><span data-stu-id="5e918-103">You can transform an editable Windows Forms text box into a read-only control.</span></span> <span data-ttu-id="5e918-104">Beispielsweise kann im Textfeld ein Wert angezeigt werden, der normalerweise bearbeitet wird, aber aufgrund des Status der Anwendung möglicherweise nicht aktuell ist.</span><span class="sxs-lookup"><span data-stu-id="5e918-104">For example, the text box may display a value that is usually edited but may not be currently, due to the state of the application.</span></span>

## <a name="to-create-a-read-only-text-box"></a><span data-ttu-id="5e918-105">So erstellen Sie ein Schreib geschütztes Textfeld</span><span class="sxs-lookup"><span data-stu-id="5e918-105">To create a read-only text box</span></span>

1. <span data-ttu-id="5e918-106">Legen Sie <xref:System.Windows.Forms.TextBox> die- <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> Eigenschaft des `true`-Steuer Elements auf fest.</span><span class="sxs-lookup"><span data-stu-id="5e918-106">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property to `true`.</span></span> <span data-ttu-id="5e918-107">Wenn die-Eigenschaft auf `true`festgelegt ist, können Benutzer einen Bildlauf durchführen und Text in einem Textfeld hervorheben, ohne Änderungen zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="5e918-107">With the property set to `true`, users can still scroll and highlight text in a text box without allowing changes.</span></span> <span data-ttu-id="5e918-108">Ein **Kopier** Befehl ist in einem Textfeld funktionsfähig, **Ausschneide** -und **Einfüge** Befehle hingegen nicht.</span><span class="sxs-lookup"><span data-stu-id="5e918-108">A **Copy** command is functional in a text box, but **Cut** and **Paste** commands are not.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5e918-109">Die <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> -Eigenschaft wirkt sich nur auf die Benutzerinteraktion zur Laufzeit aus.</span><span class="sxs-lookup"><span data-stu-id="5e918-109">The <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property only affects user interaction at run time.</span></span> <span data-ttu-id="5e918-110">Text Feldinhalte können zur Laufzeit weiterhin Programm gesteuert geändert werden, indem Sie die <xref:System.Windows.Forms.TextBox.Text%2A> -Eigenschaft des Textfelds ändern.</span><span class="sxs-lookup"><span data-stu-id="5e918-110">You can still change text box contents programmatically at run time by changing the <xref:System.Windows.Forms.TextBox.Text%2A> property of the text box.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e918-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e918-111">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="5e918-112">Übersicht über das TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5e918-112">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="5e918-113">Vorgehensweise: Steuern der Einfügemarke in einem Windows Forms TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5e918-113">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="5e918-114">Vorgehensweise: Textfeld "Kennwort" mit dem Windows Forms TextBox-Steuerelement erstellen</span><span class="sxs-lookup"><span data-stu-id="5e918-114">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="5e918-115">Vorgehensweise: Anführungszeichen in eine Zeichenfolge einfügen</span><span class="sxs-lookup"><span data-stu-id="5e918-115">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="5e918-116">Vorgehensweise: Text im TextBox-Steuerelement Windows Forms auswählen</span><span class="sxs-lookup"><span data-stu-id="5e918-116">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="5e918-117">Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5e918-117">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="5e918-118">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5e918-118">TextBox Control</span></span>](textbox-control-windows-forms.md)

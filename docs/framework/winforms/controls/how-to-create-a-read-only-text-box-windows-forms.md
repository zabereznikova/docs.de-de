---
title: 'Vorgehensweise: Erstellen eines schreibgeschützten Textfelds'
description: Erfahren Sie, wie Sie eine bearbeitbare Windows Forms Textfeld in ein Schreib geschütztes Windows Forms Textfeld transformieren.
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 5baa7c66d5f16560a4ea23861d563b099592957f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619363"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a><span data-ttu-id="1330a-103">Gewusst wie: Erstellen eines schreibgeschützten Textfelds (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="1330a-103">How to: Create a Read-Only Text Box (Windows Forms)</span></span>

<span data-ttu-id="1330a-104">Sie können eine bearbeitbare Windows Forms Textfeld in ein Schreib geschütztes Steuerelement umwandeln.</span><span class="sxs-lookup"><span data-stu-id="1330a-104">You can transform an editable Windows Forms text box into a read-only control.</span></span> <span data-ttu-id="1330a-105">Beispielsweise kann im Textfeld ein Wert angezeigt werden, der normalerweise bearbeitet wird, aber aufgrund des Status der Anwendung möglicherweise nicht aktuell ist.</span><span class="sxs-lookup"><span data-stu-id="1330a-105">For example, the text box may display a value that is usually edited but may not be currently, due to the state of the application.</span></span>

## <a name="to-create-a-read-only-text-box"></a><span data-ttu-id="1330a-106">So erstellen Sie ein Schreib geschütztes Textfeld</span><span class="sxs-lookup"><span data-stu-id="1330a-106">To create a read-only text box</span></span>

1. <span data-ttu-id="1330a-107">Legen <xref:System.Windows.Forms.TextBox> Sie die-Eigenschaft des-Steuer Elements <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> auf fest `true` .</span><span class="sxs-lookup"><span data-stu-id="1330a-107">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property to `true`.</span></span> <span data-ttu-id="1330a-108">Wenn die-Eigenschaft auf festgelegt `true` ist, können Benutzer einen Bildlauf durchführen und Text in einem Textfeld hervorheben, ohne Änderungen zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="1330a-108">With the property set to `true`, users can still scroll and highlight text in a text box without allowing changes.</span></span> <span data-ttu-id="1330a-109">Ein **Kopier** Befehl ist in einem Textfeld funktionsfähig, **Ausschneide** -und **Einfüge** Befehle hingegen nicht.</span><span class="sxs-lookup"><span data-stu-id="1330a-109">A **Copy** command is functional in a text box, but **Cut** and **Paste** commands are not.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1330a-110">Die- <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> Eigenschaft wirkt sich nur auf die Benutzerinteraktion zur Laufzeit aus.</span><span class="sxs-lookup"><span data-stu-id="1330a-110">The <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property only affects user interaction at run time.</span></span> <span data-ttu-id="1330a-111">Text Feldinhalte können zur Laufzeit weiterhin Programm gesteuert geändert werden, indem Sie die- <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft des Textfelds ändern.</span><span class="sxs-lookup"><span data-stu-id="1330a-111">You can still change text box contents programmatically at run time by changing the <xref:System.Windows.Forms.TextBox.Text%2A> property of the text box.</span></span>

## <a name="see-also"></a><span data-ttu-id="1330a-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1330a-112">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="1330a-113">Übersicht über das TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1330a-113">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="1330a-114">Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1330a-114">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="1330a-115">Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1330a-115">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="1330a-116">Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="1330a-116">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="1330a-117">Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1330a-117">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="1330a-118">Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1330a-118">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="1330a-119">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1330a-119">TextBox Control</span></span>](textbox-control-windows-forms.md)

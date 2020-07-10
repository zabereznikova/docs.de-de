---
title: ComboBox und ListBox
description: Erfahren Sie, wie Sie Windows Forms ComboBox und Windows Forms ListBox verwenden, und erfahren Sie, wie Sie erkennen, wenn eine oder die andere besser für eine Aufgabe geeignet ist.
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], vs. ComboBox
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- ComboBox control [Windows Forms], compared to ListBox
- combo boxes [Windows Forms], compared to list boxes
- ListBox control [Windows Forms], accessing items
- ListCount property
ms.assetid: 7bcaea58-1cfa-46db-9baf-b75a69d8f9ec
ms.openlocfilehash: ca6ad6bec2dbc30128ea09808af2806687b17a8c
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174418"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="56556-103">Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?</span><span class="sxs-lookup"><span data-stu-id="56556-103">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="56556-104">Das <xref:System.Windows.Forms.ComboBox> -Steuerelement und das-Steuerelement <xref:System.Windows.Forms.ListBox> weisen ähnliche Verhalten auf, und in manchen Fällen kann es austauschbar sein.</span><span class="sxs-lookup"><span data-stu-id="56556-104">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="56556-105">Es gibt jedoch Zeiten, in denen eine oder die andere für eine Aufgabe besser geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="56556-105">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="56556-106">Im Allgemeinen ist ein Kombinations Feld geeignet, wenn eine Liste der vorgeschlagenen Optionen vorliegt, und ein Listenfeld ist geeignet, wenn Sie die Eingabe auf die Liste der Listen beschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="56556-106">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="56556-107">Ein Kombinations Feld enthält ein Textfeld Feld, sodass die Auswahl nicht in der Liste eingegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="56556-107">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="56556-108">Die Ausnahme ist, wenn die- <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> Eigenschaft auf festgelegt ist <xref:System.Windows.Forms.ComboBoxStyle.DropDownList> .</span><span class="sxs-lookup"><span data-stu-id="56556-108">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="56556-109">In diesem Fall wählt das Steuerelement ein Element aus, wenn Sie seinen ersten Buchstaben eingeben.</span><span class="sxs-lookup"><span data-stu-id="56556-109">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="56556-110">Außerdem sparen Kombinations Felder Platz auf einem Formular.</span><span class="sxs-lookup"><span data-stu-id="56556-110">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="56556-111">Da die vollständige Liste erst angezeigt wird, wenn der Benutzer auf den Pfeil nach unten klickt, kann ein Kombinations Feld problemlos in einen kleinen Bereich passen, in dem ein Listenfeld nicht passt.</span><span class="sxs-lookup"><span data-stu-id="56556-111">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="56556-112">Eine Ausnahme ist, wenn die- <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> Eigenschaft auf festgelegt ist <xref:System.Windows.Forms.ComboBoxStyle.Simple> : die vollständige Liste wird angezeigt, und das Kombinations Feld benötigt mehr Platz als ein Listenfeld.</span><span class="sxs-lookup"><span data-stu-id="56556-112">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56556-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56556-113">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="56556-114">Vorgehensweise: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="56556-114">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="56556-115">Vorgehensweise: Sortieren des Inhalts eines ComboBox-, ListBox- oder CheckedListBox-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="56556-115">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="56556-116">Steuerelemente in Windows Forms zum Auflisten von Optionen</span><span class="sxs-lookup"><span data-stu-id="56556-116">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)

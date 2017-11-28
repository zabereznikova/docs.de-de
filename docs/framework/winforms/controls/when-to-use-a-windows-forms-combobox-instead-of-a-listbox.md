---
title: "Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8b4eb1ce70b1ec4b249eb126b608c9f8578d327c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="6b947-102">Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?</span><span class="sxs-lookup"><span data-stu-id="6b947-102">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="6b947-103">Die <xref:System.Windows.Forms.ComboBox> und <xref:System.Windows.Forms.ListBox> Steuerelemente weisen ähnliche Verhaltensweisen und in einigen Fällen austauschbar.</span><span class="sxs-lookup"><span data-stu-id="6b947-103">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="6b947-104">Es gibt jedoch Situationen, wenn eines dieser Zuordnungsverfahren an eine Aufgabe besser geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="6b947-104">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="6b947-105">Im Allgemeinen eignet sich ein Kombinationsfeld, wenn es eine Liste der vorgeschlagenen Optionen wird usw. ein Listenfeld eignet sich, wenn Sie Eingabe, die in der Liste ist beschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="6b947-105">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="6b947-106">Ein Kombinationsfeld enthält ein Textfeld, Optionen, die nicht in der Liste in eingegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="6b947-106">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="6b947-107">Die Ausnahme ist, wenn die <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span><span class="sxs-lookup"><span data-stu-id="6b947-107">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="6b947-108">In diesem Fall wird das Steuerelement ein Element auswählen, wenn Sie den ersten Buchstaben eingeben.</span><span class="sxs-lookup"><span data-stu-id="6b947-108">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="6b947-109">Darüber hinaus speichern Kombinationsfelder Speicherplatz auf einem Formular an.</span><span class="sxs-lookup"><span data-stu-id="6b947-109">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="6b947-110">Da die vollständige Liste nicht angezeigt wird, bis der Benutzer auf den Pfeil nach unten klickt, kann ein Kombinationsfeld problemlos in einem kleinen Bereich entsprechen, in denen ein Listenfeld nicht passen würde.</span><span class="sxs-lookup"><span data-stu-id="6b947-110">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="6b947-111">Eine Ausnahme ist, wenn die <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.ComboBoxStyle.Simple>: die vollständige Liste angezeigt wird, und das Kombinationsfeld beanspruchen mehr Platz als ein Listenfeld würde.</span><span class="sxs-lookup"><span data-stu-id="6b947-111">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b947-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b947-112">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 [<span data-ttu-id="6b947-113">Gewusst wie: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6b947-113">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 [<span data-ttu-id="6b947-114">Gewusst wie: Sortieren des Inhalts eines ComboBox-, ListBox- oder CheckedListBox-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6b947-114">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 [<span data-ttu-id="6b947-115">Windows Forms-Steuerelemente zum Auflisten von Optionen</span><span class="sxs-lookup"><span data-stu-id="6b947-115">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)

---
title: Inhalt von ComboBox-, ListBox-oder CheckedListBox-Steuerelement sortieren
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: dee969d777edf76434622fe632f7e934987a1dc3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742957"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="80f2c-102">Gewusst wie: Sortieren des Inhalts eines ComboBox-, ListBox- oder CheckedListBox-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80f2c-102">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="80f2c-103">Windows Forms Steuerelemente werden nicht sortiert, wenn Sie Daten gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="80f2c-103">Windows Forms controls do not sort when they are data-bound.</span></span> <span data-ttu-id="80f2c-104">Um sortierte Daten anzuzeigen, verwenden Sie eine Datenquelle, die das Sortieren unterstützt, und lassen Sie dann die Datenquelle sortieren.</span><span class="sxs-lookup"><span data-stu-id="80f2c-104">To display sorted data, use a data source that supports sorting and then have the data source sort it.</span></span> <span data-ttu-id="80f2c-105">Datenquellen, die das Sortieren unterstützen, sind Daten Sichten, Datenansichts-Manager und sortierte Arrays.</span><span class="sxs-lookup"><span data-stu-id="80f2c-105">Data sources that support sorting are data views, data view managers, and sorted arrays.</span></span>  
  
 <span data-ttu-id="80f2c-106">Wenn das Steuerelement nicht Daten gebunden ist, können Sie es sortieren.</span><span class="sxs-lookup"><span data-stu-id="80f2c-106">If the control is not data-bound, you can sort it.</span></span>  
  
### <a name="to-sort-the-list"></a><span data-ttu-id="80f2c-107">So sortieren Sie die Liste</span><span class="sxs-lookup"><span data-stu-id="80f2c-107">To sort the list</span></span>  
  
1. <span data-ttu-id="80f2c-108">Setzen Sie die `Sorted`-Eigenschaft auf `true`.</span><span class="sxs-lookup"><span data-stu-id="80f2c-108">Set the `Sorted` property to `true`.</span></span>  
  
     <span data-ttu-id="80f2c-109">Mit dieser Einstellung werden alle vorhandenen Listenelemente in sortierter Reihenfolge neu positioniert.</span><span class="sxs-lookup"><span data-stu-id="80f2c-109">This setting repositions all existing list items in sorted order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80f2c-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="80f2c-110">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="80f2c-111">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="80f2c-111">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="80f2c-112">Gewusst wie: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80f2c-112">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="80f2c-113">Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?</span><span class="sxs-lookup"><span data-stu-id="80f2c-113">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="80f2c-114">Windows Forms-Steuerelemente zum Auflisten von Optionen</span><span class="sxs-lookup"><span data-stu-id="80f2c-114">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)

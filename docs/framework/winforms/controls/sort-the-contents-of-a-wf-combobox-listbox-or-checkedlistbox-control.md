---
title: 'Vorgehensweise: Sortieren des Inhalts eines ComboBox-, ListBox- oder CheckedListBox-Steuerelements in Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: bd26d396c238bfc53858320b8f4487df84b3436a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59312578"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="4f799-102">Vorgehensweise: Sortieren des Inhalts eines ComboBox-, ListBox- oder CheckedListBox-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4f799-102">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="4f799-103">Windows Forms-Steuerelemente werden nicht sortiert werden, wenn sie die Daten gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="4f799-103">Windows Forms controls do not sort when they are data-bound.</span></span> <span data-ttu-id="4f799-104">Um sortierte Daten anzuzeigen, verwenden Sie eine Datenquelle, die das Sortieren unterstützt, und lassen Sie dann die Datenquelle sortiert das System.</span><span class="sxs-lookup"><span data-stu-id="4f799-104">To display sorted data, use a data source that supports sorting and then have the data source sort it.</span></span> <span data-ttu-id="4f799-105">Datenquellen, die das Sortieren unterstützt, sind Ansichten, Data Manager anzuzeigen, und sortiert Sie Arrays.</span><span class="sxs-lookup"><span data-stu-id="4f799-105">Data sources that support sorting are data views, data view managers, and sorted arrays.</span></span>  
  
 <span data-ttu-id="4f799-106">Wenn das Steuerelement nicht datengebunden ist, können Sie sie sortieren.</span><span class="sxs-lookup"><span data-stu-id="4f799-106">If the control is not data-bound, you can sort it.</span></span>  
  
### <a name="to-sort-the-list"></a><span data-ttu-id="4f799-107">Um die Liste sortieren</span><span class="sxs-lookup"><span data-stu-id="4f799-107">To sort the list</span></span>  
  
1. <span data-ttu-id="4f799-108">Legen Sie die `Sorted` -Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="4f799-108">Set the `Sorted` property to `true`.</span></span>  
  
     <span data-ttu-id="4f799-109">Diese Einstellung automatisch neu positioniert und alle vorhandenen Auflisten von Elementen in sortierter Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="4f799-109">This setting repositions all existing list items in sorted order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f799-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f799-110">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="4f799-111">Datenbindung in Web Forms</span><span class="sxs-lookup"><span data-stu-id="4f799-111">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="4f799-112">Vorgehensweise: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4f799-112">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="4f799-113">Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?</span><span class="sxs-lookup"><span data-stu-id="4f799-113">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="4f799-114">Steuerelemente in Windows Forms zum Auflisten von Optionen</span><span class="sxs-lookup"><span data-stu-id="4f799-114">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)

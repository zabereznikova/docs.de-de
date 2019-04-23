---
title: Verwenden des Designers mit dem DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- tables [Windows Forms]
- DataGridView control [Windows Forms], designer support
- formatting [Windows Forms]
ms.assetid: b66057a6-5983-4864-b4e7-8cbc88a7010c
ms.openlocfilehash: daac7dca27ac5dca8df4db24c9a3e22dae831377
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59231473"
---
# <a name="using-the-designer-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="0754f-102">Verwenden des Designers mit dem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0754f-102">Using the Designer with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="0754f-103">Visual Studio bietet die Designer-Unterstützung für die `DataGridView` -Steuerelement, das Ihnen ermöglicht, viele Setupaufgaben auszuführen, ohne Code zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="0754f-103">Visual Studio provides designer support for the `DataGridView` control that enables you to perform many setup tasks without writing code.</span></span> <span data-ttu-id="0754f-104">Dazu gehören die Bindung, die das Steuerelement an eine Datenquelle, und Ändern von Spalten zum Anzeigen von Daten verwendet und Anpassen der Darstellung und das grundlegende Verhalten des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="0754f-104">These tasks include binding the control to a data source, modifying the columns used to display data, and adjusting the appearance and basic behavior of the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0754f-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0754f-105">In This Section</span></span>  
 [<span data-ttu-id="0754f-106">Vorgehensweise: Hinzufügen und Entfernen von Spalten in der DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="0754f-106">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="0754f-107">Beschreibt, wie die **Add Columns** und **Spalten bearbeiten** Dialogfelder zum Auffüllen und die Auflistung der Spalten zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0754f-107">Describes how to use the **Add Columns** and **Edit Columns** dialog boxes to populate and modify the columns collection.</span></span>  
  
 [<span data-ttu-id="0754f-108">Vorgehensweise: Binden von Daten an das DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="0754f-108">How to: Bind Data to the Windows Forms DataGridView Control Using the Designer</span></span>](bind-data-to-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="0754f-109">Beschreibt, wie die **Datenquelle auswählen** Option smart Tag des Steuerelements mit Daten herstellen.</span><span class="sxs-lookup"><span data-stu-id="0754f-109">Describes how to use the **Choose Data Source** option on the control's smart tag to connect to data.</span></span>  
  
 [<span data-ttu-id="0754f-110">Vorgehensweise: Ändern der Reihenfolge der Spalten in der DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="0754f-110">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="0754f-111">Beschreibt, wie die **Spalten bearbeiten** Dialogfeld, um Spalten neu anordnen.</span><span class="sxs-lookup"><span data-stu-id="0754f-111">Describes how to use the **Edit Columns** dialog box to rearrange columns.</span></span>  
  
 [<span data-ttu-id="0754f-112">Vorgehensweise: Ändern des Typs einer DataGridView-Spalte in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="0754f-112">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>](change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 <span data-ttu-id="0754f-113">Beschreibt, wie die **Spalten bearbeiten** Dialogfelds Spaltentypen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0754f-113">Describes how to use the **Edit Columns** dialog box to change column types.</span></span>  
  
 [<span data-ttu-id="0754f-114">Vorgehensweise: Aktivieren der Neuanordnung von Spalten in der DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="0754f-114">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](enable-column-reordering-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="0754f-115">Beschreibt, wie smart Tag des Steuerelements verwendet wird, damit Benutzer auf die Spalten neu anordnen können.</span><span class="sxs-lookup"><span data-stu-id="0754f-115">Describes how to use the control's smart tag to enable users to rearrange columns.</span></span>  
  
 [<span data-ttu-id="0754f-116">Vorgehensweise: Einfrieren von Spalten in der DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="0754f-116">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="0754f-117">Beschreibt, wie die **Spalten bearbeiten** Dialogfeld, um zu verhindern, dass bestimmte Spalten scrollen.</span><span class="sxs-lookup"><span data-stu-id="0754f-117">Describes how to use the **Edit Columns** dialog box to prevent specific columns from scrolling.</span></span>  
  
 [<span data-ttu-id="0754f-118">Vorgehensweise: Ausblenden von Spalten in der DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="0754f-118">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](hide-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="0754f-119">Beschreibt, wie die **Spalten bearbeiten** im Dialogfeld, um bestimmte Spalten auszublenden.</span><span class="sxs-lookup"><span data-stu-id="0754f-119">Describes how to use the **Edit Columns** dialog box to hide specific columns.</span></span>  
  
 [<span data-ttu-id="0754f-120">Vorgehensweise: Stellen Sie Spalten aus, in das DataGridView-Steuerelement in Windows Forms mithilfe des Designers schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0754f-120">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>](make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="0754f-121">Beschreibt, wie die **Spalten bearbeiten** Dialogfeld, um zu verhindern, dass Benutzer bearbeiten Werte in bestimmte Spalten.</span><span class="sxs-lookup"><span data-stu-id="0754f-121">Describes how to use the **Edit Columns** dialog box to prevent users from editing values in specific columns.</span></span>  
  
 [<span data-ttu-id="0754f-122">Vorgehensweise: Zu verhindern, dass Hinzufügens und Löschens in das DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="0754f-122">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="0754f-123">Beschreibt das Smarttag des Steuerelements zu verwenden, um zu verhindern, dass Benutzer hinzufügen oder Löschen von Zeilen.</span><span class="sxs-lookup"><span data-stu-id="0754f-123">Describes how to use the control's smart tag to prevent users from adding or deleting rows.</span></span>  
  
 [<span data-ttu-id="0754f-124">Vorgehensweise: Festlegen von abwechselnden Zeilenstilen für das DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="0754f-124">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="0754f-125">Beschreibt, wie die **CellStyle-Generator** im Dialogfeld eine Ledger Darstellung im Steuerelement zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0754f-125">Describes how to use the **CellStyle Builder** dialog box to create a ledger-like appearance in the control.</span></span>  
  
 [<span data-ttu-id="0754f-126">Vorgehensweise: Festlegen von standardmäßigen Zellenstilen und Datenformaten für das DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="0754f-126">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>](default-cell-styles-datagridview.md)  
 <span data-ttu-id="0754f-127">Beschreibt, wie die **CellStyle-Generator** Dialogfeld zum Einrichten der grundlegenden Darstellung und Datenanzeige formatiert für das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0754f-127">Describes how to use the **CellStyle Builder** dialog box to set up the basic appearance and data-display formats for the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0754f-128">Referenz</span><span class="sxs-lookup"><span data-stu-id="0754f-128">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="0754f-129">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0754f-129">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0754f-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0754f-130">See also</span></span>

- [<span data-ttu-id="0754f-131">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0754f-131">DataGridView Control</span></span>](datagridview-control-windows-forms.md)

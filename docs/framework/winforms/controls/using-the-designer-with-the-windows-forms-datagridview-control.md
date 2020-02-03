---
title: Verwenden des Designers mit dem DataGridView-Steuerelement
ms.date: 03/30/2017
helpviewer_keywords:
- tables [Windows Forms]
- DataGridView control [Windows Forms], designer support
- formatting [Windows Forms]
ms.assetid: b66057a6-5983-4864-b4e7-8cbc88a7010c
ms.openlocfilehash: 50e8bddb97c2dfb84cebdbb2ca4d42a6c5743304
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728358"
---
# <a name="using-the-designer-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="97747-102">Verwenden des Designers mit dem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="97747-102">Using the Designer with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="97747-103">Visual Studio bietet Designer Unterstützung für das `DataGridView`-Steuerelement, mit dem Sie viele Setup Tasks ausführen können, ohne Code schreiben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="97747-103">Visual Studio provides designer support for the `DataGridView` control that enables you to perform many setup tasks without writing code.</span></span> <span data-ttu-id="97747-104">Zu diesen Aufgaben gehören das Binden des Steuer Elements an eine Datenquelle, das Ändern der zum Anzeigen von Daten verwendeten Spalten und das Anpassen des Erscheinungs Bilds und des grundlegenden Verhaltens des Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="97747-104">These tasks include binding the control to a data source, modifying the columns used to display data, and adjusting the appearance and basic behavior of the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="97747-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="97747-105">In This Section</span></span>  
 [<span data-ttu-id="97747-106">Vorgehensweise: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="97747-106">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="97747-107">Beschreibt, wie die Dialogfelder Spalten **Hinzufügen** und **Spalten bearbeiten** verwendet werden, um die Columns-Auflistung aufzufüllen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="97747-107">Describes how to use the **Add Columns** and **Edit Columns** dialog boxes to populate and modify the columns collection.</span></span>  
  
 [<span data-ttu-id="97747-108">Gewusst wie: Binden von Daten an das DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="97747-108">How to: Bind Data to the Windows Forms DataGridView Control Using the Designer</span></span>](bind-data-to-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="97747-109">Beschreibt, wie die Option **Datenquelle auswählen** für das Smarttag des-Steuer Elements verwendet wird, um eine Verbindung mit Daten herzustellen.</span><span class="sxs-lookup"><span data-stu-id="97747-109">Describes how to use the **Choose Data Source** option on the control's smart tag to connect to data.</span></span>  
  
 [<span data-ttu-id="97747-110">Vorgehensweise: Ändern der Reihenfolge von Spalten des DataGridView-Steuerelements in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="97747-110">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="97747-111">Beschreibt, wie das Dialogfeld **Spalten bearbeiten** verwendet wird, um Spalten neu anzuordnen.</span><span class="sxs-lookup"><span data-stu-id="97747-111">Describes how to use the **Edit Columns** dialog box to rearrange columns.</span></span>  
  
 [<span data-ttu-id="97747-112">Vorgehensweise: Ändern des Typs einer DataGridView-Spalte in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="97747-112">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>](change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 <span data-ttu-id="97747-113">Beschreibt, wie das Dialogfeld **Spalten bearbeiten** verwendet wird, um Spaltentypen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="97747-113">Describes how to use the **Edit Columns** dialog box to change column types.</span></span>  
  
 [<span data-ttu-id="97747-114">Gewusst wie: Aktivieren der Neuanordnung von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="97747-114">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](enable-column-reordering-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="97747-115">Beschreibt, wie das Smarttag des-Steuer Elements verwendet wird, um es Benutzern zu ermöglichen, Spalten neu anzuordnen.</span><span class="sxs-lookup"><span data-stu-id="97747-115">Describes how to use the control's smart tag to enable users to rearrange columns.</span></span>  
  
 [<span data-ttu-id="97747-116">Vorgehensweise: Fixieren von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="97747-116">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="97747-117">Beschreibt, wie das Dialogfeld **Spalten bearbeiten** verwendet wird, um zu verhindern, dass bestimmte Spalten durch Scrollen werden.</span><span class="sxs-lookup"><span data-stu-id="97747-117">Describes how to use the **Edit Columns** dialog box to prevent specific columns from scrolling.</span></span>  
  
 [<span data-ttu-id="97747-118">Vorgehensweise: Ausblenden von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="97747-118">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](hide-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="97747-119">Beschreibt, wie das Dialogfeld **Spalten bearbeiten** verwendet wird, um bestimmte Spalten auszublenden.</span><span class="sxs-lookup"><span data-stu-id="97747-119">Describes how to use the **Edit Columns** dialog box to hide specific columns.</span></span>  
  
 [<span data-ttu-id="97747-120">Vorgehensweise: Festlegen von schreibgeschützten Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="97747-120">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>](make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="97747-121">Beschreibt, wie das Dialogfeld **Spalten bearbeiten** verwendet wird, um Benutzer daran zu hindern, Werte in bestimmten Spalten zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="97747-121">Describes how to use the **Edit Columns** dialog box to prevent users from editing values in specific columns.</span></span>  
  
 [<span data-ttu-id="97747-122">Gewusst wie: Verhindern des Hinzufügens und Löschens von Zeilen im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="97747-122">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="97747-123">Beschreibt, wie das Smarttag des-Steuer Elements verwendet wird, um zu verhindern, dass Benutzer Zeilen hinzufügen oder löschen.</span><span class="sxs-lookup"><span data-stu-id="97747-123">Describes how to use the control's smart tag to prevent users from adding or deleting rows.</span></span>  
  
 [<span data-ttu-id="97747-124">Gewusst wie: Festlegen von abwechselnden Zeilenstilen für das Windows Forms-Steuerelement DataGridView mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="97747-124">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="97747-125">Beschreibt, wie das Dialogfeld **CellStyle Builder** verwendet wird, um eine Ledger-Darstellung im-Steuerelement zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="97747-125">Describes how to use the **CellStyle Builder** dialog box to create a ledger-like appearance in the control.</span></span>  
  
 [<span data-ttu-id="97747-126">Gewusst wie: Festlegen von standardmäßigen Zellenstilen und Datenformaten für das DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="97747-126">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>](default-cell-styles-datagridview.md)  
 <span data-ttu-id="97747-127">Beschreibt die Verwendung des Dialog Felds **CellStyle Builder** zum Einrichten der grundlegenden Darstellung und der Datenanzeige Formate für das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="97747-127">Describes how to use the **CellStyle Builder** dialog box to set up the basic appearance and data-display formats for the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="97747-128">Verweis</span><span class="sxs-lookup"><span data-stu-id="97747-128">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="97747-129">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="97747-129">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97747-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="97747-130">See also</span></span>

- [<span data-ttu-id="97747-131">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="97747-131">DataGridView Control</span></span>](datagridview-control-windows-forms.md)

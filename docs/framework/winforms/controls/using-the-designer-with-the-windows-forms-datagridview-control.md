---
title: Verwenden des Designers mit dem DataGridView-Steuerelement in Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tables [Windows Forms]
- DataGridView control [Windows Forms], designer support
- formatting [Windows Forms]
ms.assetid: b66057a6-5983-4864-b4e7-8cbc88a7010c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b29904954a593607a7872c0b59265bbf241dce98
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-designer-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="3f196-102">Verwenden des Designers mit dem DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3f196-102">Using the Designer with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="3f196-103">Visual Studio stellt Designer-Unterstützung für die `DataGridView` Steuerelement, das Ihnen ermöglicht, viele Aufgaben zur methodeneinrichtung auszuführen, ohne Code zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="3f196-103">Visual Studio provides designer support for the `DataGridView` control that enables you to perform many setup tasks without writing code.</span></span> <span data-ttu-id="3f196-104">Diesen Aufgaben zählt das Steuerelement mit einer Datenquelle, und Ändern von Spalten zum Anzeigen von Daten verwendete Bindung und das Anpassen der Darstellung und das grundlegende Verhalten des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="3f196-104">These tasks include binding the control to a data source, modifying the columns used to display data, and adjusting the appearance and basic behavior of the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3f196-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3f196-105">In This Section</span></span>  
 [<span data-ttu-id="3f196-106">Vorgehensweise: Hinzufügen und Entfernen von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="3f196-106">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="3f196-107">Beschreibt, wie die **Add Columns** und **Spalten bearbeiten** Dialogfelder zum Auffüllen und die Sammlung "Spalten" ändern.</span><span class="sxs-lookup"><span data-stu-id="3f196-107">Describes how to use the **Add Columns** and **Edit Columns** dialog boxes to populate and modify the columns collection.</span></span>  
  
 [<span data-ttu-id="3f196-108">Gewusst wie: Binden von Daten an das DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="3f196-108">How to: Bind Data to the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/bind-data-to-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="3f196-109">Beschreibt, wie die **Datenquelle auswählen** Option für das Steuerelement Smarttag Verbindung zu Daten herstellen.</span><span class="sxs-lookup"><span data-stu-id="3f196-109">Describes how to use the **Choose Data Source** option on the control's smart tag to connect to data.</span></span>  
  
 [<span data-ttu-id="3f196-110">Vorgehensweise: Ändern der Reihenfolge von Spalten des DataGridView-Steuerelements in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="3f196-110">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="3f196-111">Beschreibt, wie die **Spalten bearbeiten** (Dialogfeld), um Spalten neu anzuordnen.</span><span class="sxs-lookup"><span data-stu-id="3f196-111">Describes how to use the **Edit Columns** dialog box to rearrange columns.</span></span>  
  
 [<span data-ttu-id="3f196-112">Vorgehensweise: Ändern des Typs einer DataGridView-Spalte in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="3f196-112">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 <span data-ttu-id="3f196-113">Beschreibt, wie die **Spalten bearbeiten** Dialogfelds Spaltentypen ändern.</span><span class="sxs-lookup"><span data-stu-id="3f196-113">Describes how to use the **Edit Columns** dialog box to change column types.</span></span>  
  
 [<span data-ttu-id="3f196-114">Gewusst wie: Aktivieren der Neuanordnung von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="3f196-114">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/enable-column-reordering-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="3f196-115">Beschreibt das Smarttag für das Steuerelement zu verwenden, um Benutzer Spalten neu anordnen können.</span><span class="sxs-lookup"><span data-stu-id="3f196-115">Describes how to use the control's smart tag to enable users to rearrange columns.</span></span>  
  
 [<span data-ttu-id="3f196-116">Vorgehensweise: Fixieren von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="3f196-116">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="3f196-117">Beschreibt, wie die **Spalten bearbeiten** (Dialogfeld), um zu verhindern, dass bestimmte Spalten durchführen eines Bildlaufs.</span><span class="sxs-lookup"><span data-stu-id="3f196-117">Describes how to use the **Edit Columns** dialog box to prevent specific columns from scrolling.</span></span>  
  
 [<span data-ttu-id="3f196-118">Vorgehensweise: Ausblenden von Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="3f196-118">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="3f196-119">Beschreibt, wie die **Spalten bearbeiten** (Dialogfeld), um bestimmte Spalten auszublenden.</span><span class="sxs-lookup"><span data-stu-id="3f196-119">Describes how to use the **Edit Columns** dialog box to hide specific columns.</span></span>  
  
 [<span data-ttu-id="3f196-120">Vorgehensweise: Festlegen von schreibgeschützten Spalten im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="3f196-120">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="3f196-121">Beschreibt, wie die **Spalten bearbeiten** (Dialogfeld), um zu verhindern, dass Benutzer bearbeiten Werte in bestimmte Spalten.</span><span class="sxs-lookup"><span data-stu-id="3f196-121">Describes how to use the **Edit Columns** dialog box to prevent users from editing values in specific columns.</span></span>  
  
 [<span data-ttu-id="3f196-122">Gewusst wie: Verhindern des Hinzufügens und Löschens von Zeilen im DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="3f196-122">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="3f196-123">Beschreibt das Smarttag für das Steuerelement zu verwenden, um zu verhindern, dass Benutzer hinzufügen oder Löschen von Zeilen.</span><span class="sxs-lookup"><span data-stu-id="3f196-123">Describes how to use the control's smart tag to prevent users from adding or deleting rows.</span></span>  
  
 [<span data-ttu-id="3f196-124">Gewusst wie: Festlegen von abwechselnden Zeilenstilen für das Windows Forms-Steuerelement DataGridView mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="3f196-124">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="3f196-125">Beschreibt, wie die **CellStyle-Generator** (Dialogfeld), um eine Ledger Darstellung im Steuerelement zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3f196-125">Describes how to use the **CellStyle Builder** dialog box to create a ledger-like appearance in the control.</span></span>  
  
 [<span data-ttu-id="3f196-126">Gewusst wie: Festlegen von standardmäßigen Zellenstilen und Datenformaten für das DataGridView-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="3f196-126">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/default-cell-styles-datagridview.md)  
 <span data-ttu-id="3f196-127">Beschreibt, wie die **CellStyle-Generator** Dialogfeld zum Einrichten die grundlegende Darstellung und die Darstellung der Daten für das Steuerelement formatiert.</span><span class="sxs-lookup"><span data-stu-id="3f196-127">Describes how to use the **CellStyle Builder** dialog box to set up the basic appearance and data-display formats for the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3f196-128">Verweis</span><span class="sxs-lookup"><span data-stu-id="3f196-128">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="3f196-129">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.DataGridView>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="3f196-129">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f196-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f196-130">See Also</span></span>  
 [<span data-ttu-id="3f196-131">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="3f196-131">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)

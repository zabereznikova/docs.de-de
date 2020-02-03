---
title: Gruppieren von Steuerelementen mit Panel-Steuerelement mithilfe des Designers
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: 927aeb5b51bc1ac4e22a45e487b49424b4e67b71
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745654"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a><span data-ttu-id="c9ff6-102">Gewusst wie: Gruppieren von Steuerelementen mit dem Windows Forms-Bereichssteuerelement im Designer</span><span class="sxs-lookup"><span data-stu-id="c9ff6-102">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>
<span data-ttu-id="c9ff6-103">Windows Forms <xref:System.Windows.Forms.Panel>-Steuerelemente werden verwendet, um andere Steuerelemente zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-103">Windows Forms <xref:System.Windows.Forms.Panel> controls are used to group other controls.</span></span> <span data-ttu-id="c9ff6-104">Es gibt drei Gründe für das Gruppieren von Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-104">There are three reasons to group controls.</span></span> <span data-ttu-id="c9ff6-105">Eine ist die visuelle Gruppierung verwandter Formularelemente für eine eindeutige Benutzeroberfläche. eine andere ist die programmatische Gruppierung von Options Feldern, z. b. die letzte dient zum Verschieben der Steuerelemente als Einheit zur Entwurfszeit.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-105">One is visual grouping of related form elements for a clear user interface; another is programmatic grouping, of radio buttons for example; the last is for moving the controls as a unit at design time.</span></span>

## <a name="to-create-a-group-of-controls"></a><span data-ttu-id="c9ff6-106">So erstellen Sie eine Gruppe von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="c9ff6-106">To create a group of controls</span></span>

1. <span data-ttu-id="c9ff6-107">Ziehen Sie ein <xref:System.Windows.Forms.Panel>-Steuerelement von der Registerkarte **Windows Forms** der Toolbox auf ein Formular.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-107">Drag a <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab of the Toolbox onto a form.</span></span>

2. <span data-ttu-id="c9ff6-108">Fügen Sie dem Panel weitere Steuerelemente hinzu, und zeichnen Sie die einzelnen Elemente innerhalb des Panels.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-108">Add other controls to the panel, drawing each inside the panel.</span></span>

     <span data-ttu-id="c9ff6-109">Wenn Sie über vorhandene Steuerelemente verfügen, die Sie in einem Panel einschließen möchten, können Sie alle Steuerelemente auswählen, Sie in die Zwischenablage Ausschneiden, das <xref:System.Windows.Forms.Panel> Steuerelement auswählen und dann in das Panel einfügen.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-109">If you have existing controls that you want to enclose in a panel, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.Panel> control, and then paste them into the panel.</span></span> <span data-ttu-id="c9ff6-110">Sie können Sie auch in das Panel ziehen.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-110">You can also drag them into the panel.</span></span>

3. <span data-ttu-id="c9ff6-111">Optionale Wenn Sie einem Panel einen Rahmen hinzufügen möchten, legen Sie dessen <xref:System.Windows.Forms.BorderStyle>-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-111">(Optional) If you want to add a border to a panel, set its <xref:System.Windows.Forms.BorderStyle> property.</span></span> <span data-ttu-id="c9ff6-112">Es gibt drei Optionen: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>und <xref:System.Windows.Forms.BorderStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-112">There are three choices: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, and <xref:System.Windows.Forms.BorderStyle.None>.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9ff6-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9ff6-113">See also</span></span>

- [<span data-ttu-id="c9ff6-114">Panel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c9ff6-114">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="c9ff6-115">Übersicht über das Panel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c9ff6-115">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="c9ff6-116">Gewusst wie: Festlegen des Hintergrunds eines Bereichs</span><span class="sxs-lookup"><span data-stu-id="c9ff6-116">How to: Set the Background of a Panel</span></span>](how-to-set-the-background-of-a-windows-forms-panel.md)

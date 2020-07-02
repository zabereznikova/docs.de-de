---
title: Hinzufügen und Entfernen von Registerkarten mit TabControl mithilfe des Designers
description: Erfahren Sie, wie Sie mithilfe des-Designers Registerkarten mit dem Windows Forms TabControl-Steuerelement hinzufügen und entfernen.
ms.date: 03/30/2017
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabPage control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 480633db-413a-45d2-9c8f-0427cc13adbe
ms.openlocfilehash: 955a671693243ab212180046bb60241c8113a854
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622873"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="094e1-103">Vorgehensweise: Hinzufügen und Entfernen von Registerkarten zu TabControls in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="094e1-103">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="094e1-104">Wenn Sie ein <xref:System.Windows.Forms.TabControl> Steuerelement auf dem Formular platzieren, enthält es standardmäßig zwei Registerkarten.</span><span class="sxs-lookup"><span data-stu-id="094e1-104">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="094e1-105">Sie können Registerkarten mithilfe des Designers hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="094e1-105">You can add or remove tabs using the designer.</span></span>

 <span data-ttu-id="094e1-106">Das folgende Verfahren erfordert ein **Windows-Anwendungs** Projekt mit einem Formular, das ein-Steuerelement enthält <xref:System.Windows.Forms.TabControl> .</span><span class="sxs-lookup"><span data-stu-id="094e1-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="094e1-107">Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter Gewusst [wie: Erstellen eines Windows Forms-Anwendungs Projekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und Gewusst [wie: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="094e1-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="094e1-108">So können Sie eine Registerkarte mithilfe des Designers hinzufügen oder entfernen</span><span class="sxs-lookup"><span data-stu-id="094e1-108">To add or remove a tab using the designer</span></span>

- <span data-ttu-id="094e1-109">Klicken Sie im Smarttags des Steuer Elements auf **Registerkarte hinzufügen** oder **Registerkarte entfernen** .</span><span class="sxs-lookup"><span data-stu-id="094e1-109">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>

     <span data-ttu-id="094e1-110">- oder -</span><span class="sxs-lookup"><span data-stu-id="094e1-110">-or-</span></span>

     <span data-ttu-id="094e1-111">Klicken Sie im **Eigenschaften** Fenster **auf die Schaltfläche mit den** Auslassungs Punkten (die Schaltfläche mit den Auslassungs Punkten ![ (...) im Eigenschaftenfenster von Visual Studio. ](./media/visual-studio-ellipsis-button.png) ) neben der <xref:System.Windows.Forms.TabControl.TabPages%2A> Eigenschaft, um den **TabPage**-Auflistungs-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="094e1-111">In the **Properties** window, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="094e1-112">Klicken Sie auf die Schaltfläche **Hinzufügen** oder **Entfernen** .</span><span class="sxs-lookup"><span data-stu-id="094e1-112">Click the **Add** or **Remove** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="094e1-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="094e1-113">See also</span></span>

- [<span data-ttu-id="094e1-114">TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="094e1-114">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="094e1-115">Übersicht über das TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="094e1-115">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="094e1-116">Vorgehensweise: Hinzufügen eines Steuerelements zu einer Registerkarte</span><span class="sxs-lookup"><span data-stu-id="094e1-116">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="094e1-117">Vorgehensweise: Deaktivieren von Registerkartenseiten</span><span class="sxs-lookup"><span data-stu-id="094e1-117">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="094e1-118">Vorgehensweise: Ändern der Darstellung der TabControl-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="094e1-118">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)

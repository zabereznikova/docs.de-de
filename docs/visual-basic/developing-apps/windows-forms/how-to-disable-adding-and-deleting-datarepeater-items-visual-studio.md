---
title: 'Vorgehensweise: Deaktivieren des Hinzufügens und Löschens von DataRepeater-Elementen (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, disabling delete
- DataRepeater, disabling add
ms.assetid: 298d8f60-ddfe-4361-ab66-cf76d0df5220
ms.openlocfilehash: 3a304132d0514da4c19811be2536c9516e2838f0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618541"
---
# <a name="how-to-disable-adding-and-deleting-datarepeater-items-visual-studio"></a><span data-ttu-id="af631-102">Vorgehensweise: Deaktivieren des Hinzufügens und Löschens von DataRepeater-Elementen (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="af631-102">How to: Disable Adding and Deleting DataRepeater Items (Visual Studio)</span></span>
<span data-ttu-id="af631-103">Standardmäßig können Benutzer hinzufügen und Löschen von Elementen in einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="af631-103">By default, users can add and delete items in a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="af631-104">Benutzer können ein neues Element hinzufügen, indem Sie STRG + N drücken Wenn eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> den Fokus besitzt, oder durch Klicken auf die **AddNewItem** auf auf die Schaltfläche der <xref:System.Windows.Forms.BindingNavigator> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="af631-104">Users can add a new item by pressing CTRL+N when a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> has focus or by clicking the **AddNewItem** button on the <xref:System.Windows.Forms.BindingNavigator> control.</span></span> <span data-ttu-id="af631-105">Benutzer können ein Element löschen, durch Drücken von löschen, wenn eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> den Fokus besitzt, oder durch Klicken auf die **DeleteItem** Schaltfläche der <xref:System.Windows.Forms.BindingNavigator> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="af631-105">Users can delete an item by pressing DELETE when a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> has focus or by clicking the **DeleteItem** button on the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
 <span data-ttu-id="af631-106">Sie können die hinzufügen bzw. Löschen zur Entwurfszeit oder zur Laufzeit zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="af631-106">You can disable adding and/or deleting at design time or at run time.</span></span>  
  
### <a name="to-disable-adding-and-deleting-at-design-time"></a><span data-ttu-id="af631-107">So deaktivieren Sie zum Hinzufügen und Löschen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="af631-107">To disable adding and deleting at design time</span></span>  
  
1.  <span data-ttu-id="af631-108">Wählen Sie in der Windows Forms-Designer die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="af631-108">In the Windows Forms Designer, select the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="af631-109">Wählen Sie im unteren Abschnitt des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="af631-109">You must select the lower section of the control.</span></span> <span data-ttu-id="af631-110">Wenn Sie den Elementvorlagenbereich auswählen, wird ein anderen Satz von Eigenschaften angezeigt.</span><span class="sxs-lookup"><span data-stu-id="af631-110">If you select the item template section, a different set of properties will be displayed.</span></span>  
  
2.  <span data-ttu-id="af631-111">Legen Sie im Fenster Eigenschaften die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToAddItems%2A> Eigenschaft **"false"**.</span><span class="sxs-lookup"><span data-stu-id="af631-111">In the Properties window, set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToAddItems%2A> property to **False**.</span></span>  
  
3.  <span data-ttu-id="af631-112">Legen Sie die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToDeleteItems%2A> Eigenschaft **"false"**.</span><span class="sxs-lookup"><span data-stu-id="af631-112">Set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToDeleteItems%2A> property to **False**.</span></span>  
  
4.  <span data-ttu-id="af631-113">Wählen Sie in der Windows Forms-Designer die <xref:System.Windows.Forms.BindingNavigator> steuern, und klicken Sie dann auf die **AddNewItem** (die Schaltfläche mit einem Pluszeichen auf).</span><span class="sxs-lookup"><span data-stu-id="af631-113">In the Windows Forms Designer, select the <xref:System.Windows.Forms.BindingNavigator> control, and then click the **AddNewItem** button (the button with a plus sign on it).</span></span>  
  
5.  <span data-ttu-id="af631-114">Legen Sie im Fenster Eigenschaften die <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> Eigenschaft **"false"**.</span><span class="sxs-lookup"><span data-stu-id="af631-114">In the Properties window, set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property to **False**.</span></span>  
  
6.  <span data-ttu-id="af631-115">Wählen Sie in der Windows Forms-Designer die <xref:System.Windows.Forms.BindingNavigator> steuern, und klicken Sie dann auf die **DeleteItem** (die Schaltfläche mit einem roten X).</span><span class="sxs-lookup"><span data-stu-id="af631-115">In the Windows Forms Designer, select the <xref:System.Windows.Forms.BindingNavigator> control, and then click the **DeleteItem** button (the button with a red X on it).</span></span>  
  
7.  <span data-ttu-id="af631-116">Legen Sie im Fenster Eigenschaften die <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> Eigenschaft **"false"**.</span><span class="sxs-lookup"><span data-stu-id="af631-116">In the Properties window, set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property to **False**.</span></span>  
  
8.  <span data-ttu-id="af631-117">Wählen Sie in der Komponentenleiste, die <xref:System.Windows.Forms.BindingSource> , der die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="af631-117">In the Component Tray, select the <xref:System.Windows.Forms.BindingSource> to which the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> is bound.</span></span>  
  
9. <span data-ttu-id="af631-118">Legen Sie im Fenster Eigenschaften die <xref:System.Windows.Forms.BindingSource.AllowNew%2A> Eigenschaft **"false"**.</span><span class="sxs-lookup"><span data-stu-id="af631-118">In the Properties window, set the <xref:System.Windows.Forms.BindingSource.AllowNew%2A> property to **False**.</span></span>  
  
10. <span data-ttu-id="af631-119">Doppelklicken Sie in der Windows Forms-Designer auf die **DeleteItem** Schaltfläche, um den Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="af631-119">In the Windows Forms Designer, double-click the **DeleteItem** button to open the Code Editor.</span></span>  
  
11. <span data-ttu-id="af631-120">Wählen Sie im Dropdown-Liste Ereignisse, die `BindingNavigatorDeleteItem_EnabledChanged` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="af631-120">In the Events drop-down list, select the `BindingNavigatorDeleteItem_EnabledChanged` event.</span></span>  
  
12. <span data-ttu-id="af631-121">Fügen Sie dem `BindingNavigatorDeleteItem_EnabledChanged` -Ereignishandler folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="af631-121">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="af631-122">Dieser Schritt ist erforderlich, da die <xref:System.Windows.Forms.BindingSource> die **DeleteItem** -Schaltfläche bei jeder Änderung des aktuellen Datensatzes aktiviert.</span><span class="sxs-lookup"><span data-stu-id="af631-122">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
### <a name="to-disable-adding-and-deleting-at-run-time"></a><span data-ttu-id="af631-123">So deaktivieren Sie zum Hinzufügen und Löschen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="af631-123">To disable adding and deleting at run time</span></span>  
  
1.  <span data-ttu-id="af631-124">Doppelklicken Sie im Windows Forms-Designer auf das Formular, um den Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="af631-124">In the Windows Forms Designer, double-click the form to open the Code Editor.</span></span>  
  
2.  <span data-ttu-id="af631-125">Fügen Sie dem `Form_Load` -Ereignis folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="af631-125">Add the following code to the `Form_Load` event:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.vb)]  
  
3.  <span data-ttu-id="af631-126">Fügen Sie dem `BindingNavigatorDeleteItem_EnabledChanged` -Ereignishandler folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="af631-126">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="af631-127">Dieser Schritt ist erforderlich, da die <xref:System.Windows.Forms.BindingSource> die **DeleteItem** -Schaltfläche bei jeder Änderung des aktuellen Datensatzes aktiviert.</span><span class="sxs-lookup"><span data-stu-id="af631-127">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af631-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af631-128">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [<span data-ttu-id="af631-129">Einführung in das DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="af631-129">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="af631-130">Problembehandlung beim DataRepeater-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="af631-130">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)

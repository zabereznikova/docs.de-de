---
title: "Gewusst wie: Ändern der Darstellung der TabControl-Komponente in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- icons [Windows Forms], displaying on tabs
- TabControl control [Windows Forms], changing page appearance
- tabs [Windows Forms], controlling appearance
- buttons [Windows Forms], displaying tabs as
ms.assetid: 7c6cc443-ed62-4d26-b94d-b8913b44f773
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61fb11b79459da14384af974dbc403024faa377f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a><span data-ttu-id="29c43-102">Gewusst wie: Ändern der Darstellung der TabControl-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="29c43-102">How to: Change the Appearance of the Windows Forms TabControl</span></span>
<span data-ttu-id="29c43-103">Sie können die Darstellung der Registerkarten in Windows Forms mithilfe von Eigenschaften ändern die <xref:System.Windows.Forms.TabControl> und <xref:System.Windows.Forms.TabPage> Objekte, die die einzelnen Registerkarten des Steuerelements bilden.</span><span class="sxs-lookup"><span data-stu-id="29c43-103">You can change the appearance of tabs in Windows Forms by using properties of the <xref:System.Windows.Forms.TabControl> and the <xref:System.Windows.Forms.TabPage> objects that make up the individual tabs on the control.</span></span> <span data-ttu-id="29c43-104">Durch Festlegen dieser Eigenschaften, können Sie Bilder auf Registerkarten anzeigen, Registerkarten vertikal anstatt horizontal anzuzeigen, mehrere Zeilen mit Registerkarten anzeigen und aktivieren oder deaktivieren Registerkarten programmgesteuert.</span><span class="sxs-lookup"><span data-stu-id="29c43-104">By setting these properties, you can display images on tabs, display tabs vertically instead of horizontally, display multiple rows of tabs, and enable or disable tabs programmatically.</span></span>  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a><span data-ttu-id="29c43-105">Ein Symbol auf dem Etikett Teil einer Registerkarte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="29c43-105">To display an icon on the label part of a tab</span></span>  
  
1.  <span data-ttu-id="29c43-106">Hinzufügen einer <xref:System.Windows.Forms.ImageList> Steuerelement dem Formular.</span><span class="sxs-lookup"><span data-stu-id="29c43-106">Add an <xref:System.Windows.Forms.ImageList> control to the form.</span></span>  
  
2.  <span data-ttu-id="29c43-107">Hinzufügen von Bildern auf die Bildliste.</span><span class="sxs-lookup"><span data-stu-id="29c43-107">Add images to the image list.</span></span>  
  
     <span data-ttu-id="29c43-108">Weitere Informationen zu Bildlisten, finden Sie unter [ImageList-Komponente](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) und [wie: Hinzufügen oder Entfernen von Bildern mit der ImageList-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="29c43-108">For more information about image lists, see [ImageList Component](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
3.  <span data-ttu-id="29c43-109">Festlegen der <xref:System.Windows.Forms.TabControl.ImageList%2A> Eigenschaft von der <xref:System.Windows.Forms.TabControl> auf die <xref:System.Windows.Forms.ImageList> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="29c43-109">Set the <xref:System.Windows.Forms.TabControl.ImageList%2A> property of the <xref:System.Windows.Forms.TabControl> to the <xref:System.Windows.Forms.ImageList> control.</span></span>  
  
4.  <span data-ttu-id="29c43-110">Legen Sie die <xref:System.Windows.Forms.TabPage.ImageIndex%2A> Eigenschaft von der <xref:System.Windows.Forms.TabPage> auf den Index des geeigneten Bildes in der Liste.</span><span class="sxs-lookup"><span data-stu-id="29c43-110">Set the <xref:System.Windows.Forms.TabPage.ImageIndex%2A> property of the <xref:System.Windows.Forms.TabPage> to the index of an appropriate image in the list.</span></span>  
  
### <a name="to-create-multiple-rows-of-tabs"></a><span data-ttu-id="29c43-111">So erstellen mehrere Zeilen mit Registerkarten</span><span class="sxs-lookup"><span data-stu-id="29c43-111">To create multiple rows of tabs</span></span>  
  
1.  <span data-ttu-id="29c43-112">Fügen Sie die Anzahl der gewünschten Registerkarten hinzu.</span><span class="sxs-lookup"><span data-stu-id="29c43-112">Add the number of tab pages you want.</span></span>  
  
2.  <span data-ttu-id="29c43-113">Festlegen der <xref:System.Windows.Forms.TabControl.Multiline%2A> Eigenschaft von der <xref:System.Windows.Forms.TabControl> auf `true`.</span><span class="sxs-lookup"><span data-stu-id="29c43-113">Set the <xref:System.Windows.Forms.TabControl.Multiline%2A> property of the <xref:System.Windows.Forms.TabControl> to `true`.</span></span>  
  
3.  <span data-ttu-id="29c43-114">Wenn die Registerkarten nicht bereits in mehreren Zeilen angezeigt werden, legen Sie die <xref:System.Windows.Forms.Control.Width%2A> Eigenschaft von der <xref:System.Windows.Forms.TabControl> enger gefasst als aller Registerkarten werden.</span><span class="sxs-lookup"><span data-stu-id="29c43-114">If the tabs do not already appear in multiple rows, set the <xref:System.Windows.Forms.Control.Width%2A> property of the <xref:System.Windows.Forms.TabControl> to be narrower than all the tabs.</span></span>  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a><span data-ttu-id="29c43-115">So ordnen Sie die Registerkarten auf das Steuerelement an</span><span class="sxs-lookup"><span data-stu-id="29c43-115">To arrange tabs on the side of the control</span></span>  
  
-   <span data-ttu-id="29c43-116">Festlegen der <xref:System.Windows.Forms.TabControl.Alignment%2A> Eigenschaft von der <xref:System.Windows.Forms.TabControl> auf <xref:System.Windows.Forms.TabAlignment.Left> oder <xref:System.Windows.Forms.TabAlignment.Right>.</span><span class="sxs-lookup"><span data-stu-id="29c43-116">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAlignment.Left> or <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a><span data-ttu-id="29c43-117">Programmgesteuertes aktivieren oder deaktivieren alle Steuerelemente auf einer Registerkarte</span><span class="sxs-lookup"><span data-stu-id="29c43-117">To programmatically enable or disable all controls on a tab</span></span>  
  
1.  <span data-ttu-id="29c43-118">Festlegen der <xref:System.Windows.Forms.TabPage.Enabled%2A> Eigenschaft von der <xref:System.Windows.Forms.TabPage> auf `true` oder `false`.</span><span class="sxs-lookup"><span data-stu-id="29c43-118">Set the <xref:System.Windows.Forms.TabPage.Enabled%2A> property of the <xref:System.Windows.Forms.TabPage> to `true` or `false`.</span></span>  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a><span data-ttu-id="29c43-119">Zum Anzeigen von Registerkarten als Schaltflächen</span><span class="sxs-lookup"><span data-stu-id="29c43-119">To display tabs as buttons</span></span>  
  
-   <span data-ttu-id="29c43-120">Festlegen der <xref:System.Windows.Forms.TabControl.Appearance%2A> Eigenschaft von der <xref:System.Windows.Forms.TabControl> auf <xref:System.Windows.Forms.TabAppearance.Buttons> oder <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span><span class="sxs-lookup"><span data-stu-id="29c43-120">Set the <xref:System.Windows.Forms.TabControl.Appearance%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAppearance.Buttons> or <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29c43-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29c43-121">See Also</span></span>  
 [<span data-ttu-id="29c43-122">TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="29c43-122">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="29c43-123">Übersicht über das TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="29c43-123">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="29c43-124">Gewusst wie: Hinzufügen eines Steuerelements zu einer Registerkarte</span><span class="sxs-lookup"><span data-stu-id="29c43-124">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="29c43-125">Gewusst wie: Deaktivieren von Registerkarten</span><span class="sxs-lookup"><span data-stu-id="29c43-125">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="29c43-126">Gewusst wie: Hinzufügen und Entfernen von Registerkarten mit dem TabControl-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="29c43-126">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)

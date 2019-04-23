---
title: 'Vorgehensweise: Ändern der Darstellung der TabControl-Komponente in Windows Forms'
ms.date: 03/30/2017
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
ms.openlocfilehash: 05df05a52914f27a4b62cf7bde92e5d942b6ea06
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331337"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a><span data-ttu-id="84e7a-102">Vorgehensweise: Ändern der Darstellung der TabControl-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="84e7a-102">How to: Change the Appearance of the Windows Forms TabControl</span></span>
<span data-ttu-id="84e7a-103">Sie können die Darstellung der Registerkarten in Windows Forms ändern, indem Sie mit den Eigenschaften des der <xref:System.Windows.Forms.TabControl> und <xref:System.Windows.Forms.TabPage> Objekte, die die einzelnen Registerkarten des Steuerelements bilden.</span><span class="sxs-lookup"><span data-stu-id="84e7a-103">You can change the appearance of tabs in Windows Forms by using properties of the <xref:System.Windows.Forms.TabControl> and the <xref:System.Windows.Forms.TabPage> objects that make up the individual tabs on the control.</span></span> <span data-ttu-id="84e7a-104">Durch Festlegen dieser Eigenschaften an, können Sie Bilder auf Registerkarten anzeigen, Anzeigen von Registerkarten vertikal statt horizontal, Anzeigen mehrerer Zeilen mit Registerkarten, und aktivieren oder deaktivieren Registerkarten programmgesteuert.</span><span class="sxs-lookup"><span data-stu-id="84e7a-104">By setting these properties, you can display images on tabs, display tabs vertically instead of horizontally, display multiple rows of tabs, and enable or disable tabs programmatically.</span></span>  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a><span data-ttu-id="84e7a-105">Ein Symbol auf dem Label-Teil einer Registerkarte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="84e7a-105">To display an icon on the label part of a tab</span></span>  
  
1. <span data-ttu-id="84e7a-106">Hinzufügen einer <xref:System.Windows.Forms.ImageList> -Steuerelement auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="84e7a-106">Add an <xref:System.Windows.Forms.ImageList> control to the form.</span></span>  
  
2. <span data-ttu-id="84e7a-107">Hinzufügen von Bildern der Bildliste.</span><span class="sxs-lookup"><span data-stu-id="84e7a-107">Add images to the image list.</span></span>  
  
     <span data-ttu-id="84e7a-108">Weitere Informationen zu Bildlisten, finden Sie unter [ImageList-Komponente](imagelist-component-windows-forms.md) und [Vorgehensweise: Hinzufügen oder Entfernen von Bildern mit der Windows Forms ImageList-Komponente](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="84e7a-108">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
3. <span data-ttu-id="84e7a-109">Legen Sie die <xref:System.Windows.Forms.TabControl.ImageList%2A> Eigenschaft der <xref:System.Windows.Forms.TabControl> auf der <xref:System.Windows.Forms.ImageList> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="84e7a-109">Set the <xref:System.Windows.Forms.TabControl.ImageList%2A> property of the <xref:System.Windows.Forms.TabControl> to the <xref:System.Windows.Forms.ImageList> control.</span></span>  
  
4. <span data-ttu-id="84e7a-110">Legen Sie die <xref:System.Windows.Forms.TabPage.ImageIndex%2A> Eigenschaft der <xref:System.Windows.Forms.TabPage> auf den Index der geeigneten Bildes in der Liste.</span><span class="sxs-lookup"><span data-stu-id="84e7a-110">Set the <xref:System.Windows.Forms.TabPage.ImageIndex%2A> property of the <xref:System.Windows.Forms.TabPage> to the index of an appropriate image in the list.</span></span>  
  
### <a name="to-create-multiple-rows-of-tabs"></a><span data-ttu-id="84e7a-111">Um mehrere Zeilen mit Registerkarten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="84e7a-111">To create multiple rows of tabs</span></span>  
  
1. <span data-ttu-id="84e7a-112">Fügen Sie die Anzahl der gewünschten Registerkartenseiten hinzu.</span><span class="sxs-lookup"><span data-stu-id="84e7a-112">Add the number of tab pages you want.</span></span>  
  
2. <span data-ttu-id="84e7a-113">Legen Sie die <xref:System.Windows.Forms.TabControl.Multiline%2A> Eigenschaft der <xref:System.Windows.Forms.TabControl> zu `true`.</span><span class="sxs-lookup"><span data-stu-id="84e7a-113">Set the <xref:System.Windows.Forms.TabControl.Multiline%2A> property of the <xref:System.Windows.Forms.TabControl> to `true`.</span></span>  
  
3. <span data-ttu-id="84e7a-114">Wenn die Registerkarten nicht bereits in mehreren Zeilen angezeigt werden, legen Sie die <xref:System.Windows.Forms.Control.Width%2A> Eigenschaft der <xref:System.Windows.Forms.TabControl> schmaler als alle Registerkarten sein.</span><span class="sxs-lookup"><span data-stu-id="84e7a-114">If the tabs do not already appear in multiple rows, set the <xref:System.Windows.Forms.Control.Width%2A> property of the <xref:System.Windows.Forms.TabControl> to be narrower than all the tabs.</span></span>  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a><span data-ttu-id="84e7a-115">So ordnen Sie die Registerkarten im Zweifelsfall das Steuerelement an</span><span class="sxs-lookup"><span data-stu-id="84e7a-115">To arrange tabs on the side of the control</span></span>  
  
-   <span data-ttu-id="84e7a-116">Legen Sie die <xref:System.Windows.Forms.TabControl.Alignment%2A> Eigenschaft der <xref:System.Windows.Forms.TabControl> zu <xref:System.Windows.Forms.TabAlignment.Left> oder <xref:System.Windows.Forms.TabAlignment.Right>.</span><span class="sxs-lookup"><span data-stu-id="84e7a-116">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAlignment.Left> or <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a><span data-ttu-id="84e7a-117">Programmgesteuertes aktivieren oder deaktivieren alle Steuerelemente auf einer Registerkarte</span><span class="sxs-lookup"><span data-stu-id="84e7a-117">To programmatically enable or disable all controls on a tab</span></span>  
  
1. <span data-ttu-id="84e7a-118">Legen Sie die <xref:System.Windows.Forms.TabPage.Enabled%2A> Eigenschaft der <xref:System.Windows.Forms.TabPage> zu `true` oder `false`.</span><span class="sxs-lookup"><span data-stu-id="84e7a-118">Set the <xref:System.Windows.Forms.TabPage.Enabled%2A> property of the <xref:System.Windows.Forms.TabPage> to `true` or `false`.</span></span>  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a><span data-ttu-id="84e7a-119">Zum Anzeigen von Registerkarten als Schaltflächen</span><span class="sxs-lookup"><span data-stu-id="84e7a-119">To display tabs as buttons</span></span>  
  
-   <span data-ttu-id="84e7a-120">Legen Sie die <xref:System.Windows.Forms.TabControl.Appearance%2A> Eigenschaft der <xref:System.Windows.Forms.TabControl> zu <xref:System.Windows.Forms.TabAppearance.Buttons> oder <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span><span class="sxs-lookup"><span data-stu-id="84e7a-120">Set the <xref:System.Windows.Forms.TabControl.Appearance%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAppearance.Buttons> or <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84e7a-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84e7a-121">See also</span></span>

- [<span data-ttu-id="84e7a-122">TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="84e7a-122">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="84e7a-123">Übersicht über das TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="84e7a-123">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="84e7a-124">Vorgehensweise: Hinzufügen eines Steuerelements zu einer Registerkarte</span><span class="sxs-lookup"><span data-stu-id="84e7a-124">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="84e7a-125">Vorgehensweise: Deaktivieren von Registerkarten</span><span class="sxs-lookup"><span data-stu-id="84e7a-125">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="84e7a-126">Vorgehensweise: Hinzufügen und Entfernen von Registerkarten zu TabControls in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="84e7a-126">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)

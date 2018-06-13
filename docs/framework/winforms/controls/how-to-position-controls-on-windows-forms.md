---
title: 'Gewusst wie: Positionieren von Steuerelementen in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
ms.openlocfilehash: 6db021f2b1a29c3ef52a182c45bbc7878feebb97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538711"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="a28e8-102">Gewusst wie: Positionieren von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a28e8-102">How to: Position Controls on Windows Forms</span></span>
<span data-ttu-id="a28e8-103">Positionieren von Steuerelementen, die Windows Forms-Designer verwenden, oder geben den <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a28e8-103">To position controls, use the Windows Forms Designer, or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a28e8-104">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="a28e8-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a28e8-105">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a28e8-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a28e8-106">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="a28e8-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="a28e8-107">Um ein Steuerelement auf der Entwurfsoberfläche der Windows Forms-Designer zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="a28e8-107">To position a control on the design surface of the Windows Forms Designer</span></span>  
  
-   <span data-ttu-id="a28e8-108">Ziehen Sie das Steuerelement an die gewünschte Position mit der Maus ein.</span><span class="sxs-lookup"><span data-stu-id="a28e8-108">Drag the control to the appropriate location with the mouse.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a28e8-109">Wählen Sie das Steuerelement, und verschieben Sie es mit dem Pfeil Schlüssel, um genauer zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="a28e8-109">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="a28e8-110">Darüber hinaus *Ausrichtungslinien* unterstützen Sie beim Einfügen von Steuerelementen auf dem Formular genau.</span><span class="sxs-lookup"><span data-stu-id="a28e8-110">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="a28e8-111">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="a28e8-111">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>  
  
### <a name="to-position-a-control-using-the-properties-window"></a><span data-ttu-id="a28e8-112">Um ein Steuerelement über das Eigenschaftenfenster zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="a28e8-112">To position a control using the Properties window</span></span>  
  
1.  <span data-ttu-id="a28e8-113">Klicken Sie auf das Steuerelement, das Sie positionieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a28e8-113">Click the control you want to position.</span></span>  
  
2.  <span data-ttu-id="a28e8-114">In der **Eigenschaften** Fenster geben Werte für die <xref:System.Windows.Forms.Control.Location%2A> -Eigenschaft, getrennt durch ein Komma, um das Steuerelement innerhalb des Containers zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="a28e8-114">In the **Properties** window, type values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>  
  
     <span data-ttu-id="a28e8-115">Die erste Zahl (X) entspricht dem Abstand vom linken Rand des Containers; die zweite Zahl (Y) entspricht dem Abstand vom oberen Rand der Containerbereich, gemessen in Pixel.</span><span class="sxs-lookup"><span data-stu-id="a28e8-115">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a28e8-116">Sie erweitern, können die <xref:System.Windows.Forms.Control.Location%2A> -Eigenschaft, um die **X** und **Y** einzeln Werte.</span><span class="sxs-lookup"><span data-stu-id="a28e8-116">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>  
  
### <a name="to-position-a-control-programmatically"></a><span data-ttu-id="a28e8-117">Um ein Steuerelement programmgesteuert zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="a28e8-117">To position a control programmatically</span></span>  
  
1.  <span data-ttu-id="a28e8-118">Legen Sie die <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft des Steuerelements ein <xref:System.Drawing.Point>.</span><span class="sxs-lookup"><span data-stu-id="a28e8-118">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2.  <span data-ttu-id="a28e8-119">Ändern Sie die X-Koordinate der Position des Steuerelements mithilfe der <xref:System.Windows.Forms.Control.Left%2A> Untereigenschaften.</span><span class="sxs-lookup"><span data-stu-id="a28e8-119">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### <a name="to-increment-a-controls-location-programmatically"></a><span data-ttu-id="a28e8-120">Um die Position eines Steuerelements programmgesteuert erhöht</span><span class="sxs-lookup"><span data-stu-id="a28e8-120">To increment a control's location programmatically</span></span>  
  
1.  <span data-ttu-id="a28e8-121">Legen Sie die <xref:System.Windows.Forms.Control.Left%2A> untergeordnete Eigenschaft, um die X-Koordinate des Steuerelements zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="a28e8-121">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>  
  
    ```vb  
    Button1.Left += 200  
    ```  
  
    ```csharp  
    button1.Left += 200;  
    ```  
  
    ```cpp  
    button1->Left += 200;  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="a28e8-122">Verwenden der <xref:System.Windows.Forms.Control.Location%2A> -Eigenschaft festzulegende eines Steuerelements X- und Y-Positionen gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="a28e8-122">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="a28e8-123">Um eine Position einzeln festzulegen, verwenden Sie des Steuerelements <xref:System.Windows.Forms.Control.Left%2A> (**X**) oder <xref:System.Windows.Forms.Control.Top%2A> (**Y**) Untereigenschaften.</span><span class="sxs-lookup"><span data-stu-id="a28e8-123">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="a28e8-124">Versuchen Sie nicht implizit die X- und Y-Koordinaten der Festlegen der <xref:System.Drawing.Point> -Struktur, die Position der Schaltfläche, darstellt, da diese Struktur eine Kopie der Schaltfläche Koordinaten enthält.</span><span class="sxs-lookup"><span data-stu-id="a28e8-124">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a28e8-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a28e8-125">See Also</span></span>  
 [<span data-ttu-id="a28e8-126">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="a28e8-126">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="a28e8-127">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien</span><span class="sxs-lookup"><span data-stu-id="a28e8-127">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="a28e8-128">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a28e8-128">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="a28e8-129">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a28e8-129">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [<span data-ttu-id="a28e8-130">Anordnen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a28e8-130">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="a28e8-131">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="a28e8-131">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="a28e8-132">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="a28e8-132">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="a28e8-133">Windows Forms-Steuerelemente nach Funktion</span><span class="sxs-lookup"><span data-stu-id="a28e8-133">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [<span data-ttu-id="a28e8-134">Vorgehensweise: festlegen die Bildschirmposition von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a28e8-134">How to: Set the Screen Location of Windows Forms</span></span>](http://msdn.microsoft.com/library/cb023ab7-dea7-4284-9aa6-8c03c59b60c6)

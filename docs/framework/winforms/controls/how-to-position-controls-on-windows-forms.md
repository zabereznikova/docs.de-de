---
title: 'Vorgehensweise: Positionieren von Steuerelementen in Windows Forms'
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
ms.openlocfilehash: 241edbe60c327493c9123c6cf7bdc19b7ba2b724
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211656"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="dab75-102">Vorgehensweise: Positionieren von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dab75-102">How to: Position Controls on Windows Forms</span></span>

<span data-ttu-id="dab75-103">Positionieren von Steuerelementen, die Windows Forms-Designer in Visual Studio verwenden oder Angeben der <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="dab75-103">To position controls, use the Windows Forms Designer in Visual Studio or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="dab75-104">Positionieren Sie ein Steuerelement auf der Entwurfsoberfläche des Windows Forms-Designers</span><span class="sxs-lookup"><span data-stu-id="dab75-104">Position a control on the design surface of the Windows Forms Designer</span></span>

<span data-ttu-id="dab75-105">Ziehen Sie in Visual Studio das Steuerelement an die gewünschte Position mit der Maus.</span><span class="sxs-lookup"><span data-stu-id="dab75-105">In Visual Studio, drag the control to the appropriate location with the mouse.</span></span>

> [!NOTE]
> <span data-ttu-id="dab75-106">Wählen Sie das Steuerelement, und verschieben Sie, dass es mit dem Pfeil Schlüssel, um genauer zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="dab75-106">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="dab75-107">Darüber hinaus *Ausrichtungslinien* unterstützen Sie beim Einfügen von Steuerelementen genauer auf dem Formular.</span><span class="sxs-lookup"><span data-stu-id="dab75-107">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="dab75-108">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="dab75-108">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

## <a name="position-a-control-using-the-properties-window"></a><span data-ttu-id="dab75-109">Positionieren Sie ein Steuerelement, das mithilfe des Eigenschaftenfensters</span><span class="sxs-lookup"><span data-stu-id="dab75-109">Position a control using the Properties window</span></span>

1. <span data-ttu-id="dab75-110">Klicken Sie in Visual Studio auf das Steuerelement platzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="dab75-110">In Visual Studio, click the control you want to position.</span></span>

2. <span data-ttu-id="dab75-111">In der **Eigenschaften** Fenster Typwerte für die <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft, getrennt durch ein Komma, um das Steuerelement innerhalb des Containers zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="dab75-111">In the **Properties** window, type values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>

     <span data-ttu-id="dab75-112">Die erste Zahl (X) ist der Abstand vom linken Rand des Containers. die zweite Zahl (Y) wird der Abstand zwischen den oberen Rand des Container-Bereichs, gemessen in Pixel.</span><span class="sxs-lookup"><span data-stu-id="dab75-112">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dab75-113">Sie können erweitern die <xref:System.Windows.Forms.Control.Location%2A> -Eigenschaft, um die **X** und **Y** Werte einzeln.</span><span class="sxs-lookup"><span data-stu-id="dab75-113">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>

## <a name="position-a-control-programmatically"></a><span data-ttu-id="dab75-114">Ein Steuerelement programmgesteuert zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="dab75-114">Position a control programmatically</span></span>

1. <span data-ttu-id="dab75-115">Legen Sie die <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft des Steuerelements, das eine <xref:System.Drawing.Point>.</span><span class="sxs-lookup"><span data-stu-id="dab75-115">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. <span data-ttu-id="dab75-116">Ändern Sie die X-Koordinate der Position des Steuerelements mit der <xref:System.Windows.Forms.Control.Left%2A> Untereigenschaften.</span><span class="sxs-lookup"><span data-stu-id="dab75-116">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a><span data-ttu-id="dab75-117">Programmgesteuerte Inkrementieren der Position eines Steuerelements</span><span class="sxs-lookup"><span data-stu-id="dab75-117">Increment a control's location programmatically</span></span>

<span data-ttu-id="dab75-118">Legen Sie die <xref:System.Windows.Forms.Control.Left%2A> untergeordnete Eigenschaft, um die X-Koordinate des Steuerelements zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="dab75-118">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>

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
> <span data-ttu-id="dab75-119">Verwenden der <xref:System.Windows.Forms.Control.Location%2A> -Eigenschaft festlegen eines Steuerelements X- und Y-Positionen gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="dab75-119">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="dab75-120">Um eine Position einzeln festgelegt werden, verwenden Sie das Steuerelement des <xref:System.Windows.Forms.Control.Left%2A> (**X**) oder <xref:System.Windows.Forms.Control.Top%2A> (**Y**) Untereigenschaften.</span><span class="sxs-lookup"><span data-stu-id="dab75-120">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="dab75-121">Versuchen Sie nicht implizit die X- und Y-Koordinaten der Festlegen der <xref:System.Drawing.Point> Struktur, die die Position der Schaltfläche, darstellt, da diese Struktur eine Kopie der Schaltfläche Koordinaten enthält.</span><span class="sxs-lookup"><span data-stu-id="dab75-121">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>

## <a name="see-also"></a><span data-ttu-id="dab75-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dab75-122">See also</span></span>

- [<span data-ttu-id="dab75-123">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="dab75-123">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="dab75-124">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien</span><span class="sxs-lookup"><span data-stu-id="dab75-124">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="dab75-125">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="dab75-125">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="dab75-126">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="dab75-126">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="dab75-127">Anordnen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dab75-127">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="dab75-128">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="dab75-128">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="dab75-129">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="dab75-129">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="dab75-130">Windows Forms-Steuerelemente nach Funktion</span><span class="sxs-lookup"><span data-stu-id="dab75-130">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="dab75-131">[Vorgehensweise: Festlegen der Bildschirmposition von Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="dab75-131">[How to: Set the Screen Location of Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span></span>

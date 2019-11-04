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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: bb57d14397a4626e01c41dd687dfed7331282a10
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458323"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="19f18-102">Gewusst wie: Positionieren von Steuerelementen auf Windows Forms</span><span class="sxs-lookup"><span data-stu-id="19f18-102">How to: Position controls on Windows Forms</span></span>

<span data-ttu-id="19f18-103">Verwenden Sie zum Positionieren von Steuerelementen die Windows Forms-Designer in Visual Studio, oder geben Sie die <xref:System.Windows.Forms.Control.Location%2A>-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="19f18-103">To position controls, use the Windows Forms Designer in Visual Studio or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="19f18-104">Positionieren eines Steuer Elements auf der Entwurfs Oberfläche des Windows Forms-Designer</span><span class="sxs-lookup"><span data-stu-id="19f18-104">Position a control on the design surface of the Windows Forms Designer</span></span>

<span data-ttu-id="19f18-105">Ziehen Sie das Steuerelement in Visual Studio mit der Maus an die entsprechende Position.</span><span class="sxs-lookup"><span data-stu-id="19f18-105">In Visual Studio, drag the control to the appropriate location with the mouse.</span></span>

> [!NOTE]
> <span data-ttu-id="19f18-106">Wählen Sie das Steuerelement aus, und verschieben Sie es mit den Pfeiltasten, um es genauer zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="19f18-106">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="19f18-107">Außerdem unterstützen Sie mit den Richtungs *Linien* , dass Sie Steuerelemente genau in Ihrem Formular platzieren.</span><span class="sxs-lookup"><span data-stu-id="19f18-107">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="19f18-108">Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Anordnen von Steuerelementen auf Windows Forms mithilfe](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)von Ausrichtungs Linien.</span><span class="sxs-lookup"><span data-stu-id="19f18-108">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

## <a name="position-a-control-using-the-properties-window"></a><span data-ttu-id="19f18-109">Positionieren eines Steuer Elements mithilfe des Eigenschaftenfenster</span><span class="sxs-lookup"><span data-stu-id="19f18-109">Position a control using the Properties window</span></span>

1. <span data-ttu-id="19f18-110">Wählen Sie in Visual Studio das Steuerelement aus, das Sie positionieren möchten.</span><span class="sxs-lookup"><span data-stu-id="19f18-110">In Visual Studio, select the control you want to position.</span></span>

2. <span data-ttu-id="19f18-111">Geben Sie im Fenster **Eigenschaften** Werte für die <xref:System.Windows.Forms.Control.Location%2A>-Eigenschaft, getrennt durch ein Komma, ein, um das Steuerelement in seinem Container zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="19f18-111">In the **Properties** window, enter values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>

   <span data-ttu-id="19f18-112">Die erste Zahl (X) ist die Entfernung vom linken Rand des Containers. die zweite Zahl (Y) ist der Abstand zwischen dem oberen Rand des Container Bereichs (gemessen in Pixel).</span><span class="sxs-lookup"><span data-stu-id="19f18-112">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>

   > [!NOTE]
   > <span data-ttu-id="19f18-113">Sie können die <xref:System.Windows.Forms.Control.Location%2A>-Eigenschaft erweitern, um die **X** -und **Y** -Werte einzeln einzugeben.</span><span class="sxs-lookup"><span data-stu-id="19f18-113">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>

## <a name="position-a-control-programmatically"></a><span data-ttu-id="19f18-114">Programm gesteuertes Positionieren eines Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="19f18-114">Position a control programmatically</span></span>

1. <span data-ttu-id="19f18-115">Legen Sie die <xref:System.Windows.Forms.Control.Location%2A>-Eigenschaft des-Steuer Elements auf einen <xref:System.Drawing.Point>fest.</span><span class="sxs-lookup"><span data-stu-id="19f18-115">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. <span data-ttu-id="19f18-116">Ändern Sie die X-Koordinate der Position des Steuer Elements mithilfe der <xref:System.Windows.Forms.Control.Left%2A> Untereigenschaft.</span><span class="sxs-lookup"><span data-stu-id="19f18-116">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a><span data-ttu-id="19f18-117">Programm gesteuertes erhöhen der Position eines Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="19f18-117">Increment a control's location programmatically</span></span>

<span data-ttu-id="19f18-118">Legen Sie die <xref:System.Windows.Forms.Control.Left%2A> Untereigenschaft fest, um die X-Koordinate des Steuer Elements zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="19f18-118">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>

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
> <span data-ttu-id="19f18-119">Verwenden Sie die Eigenschaft <xref:System.Windows.Forms.Control.Location%2A>, um die X-und Y-Positionen eines Steuer Elements gleichzeitig festzulegen.</span><span class="sxs-lookup"><span data-stu-id="19f18-119">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="19f18-120">Um eine Position einzeln festzulegen, verwenden Sie die <xref:System.Windows.Forms.Control.Left%2A> (**X**)-oder <xref:System.Windows.Forms.Control.Top%2A> (**Y**)-Untereigenschaft des Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="19f18-120">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="19f18-121">Versuchen Sie nicht, die X-und Y-Koordinaten der <xref:System.Drawing.Point> Struktur, die den Speicherort der Schaltfläche darstellt, implizit festzulegen, da diese Struktur eine Kopie der Koordinaten der Schaltfläche enthält.</span><span class="sxs-lookup"><span data-stu-id="19f18-121">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>

## <a name="see-also"></a><span data-ttu-id="19f18-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19f18-122">See also</span></span>

- [<span data-ttu-id="19f18-123">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="19f18-123">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="19f18-124">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien</span><span class="sxs-lookup"><span data-stu-id="19f18-124">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="19f18-125">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="19f18-125">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="19f18-126">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="19f18-126">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="19f18-127">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="19f18-127">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="19f18-128">Steuerelemente für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="19f18-128">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="19f18-129">Windows Forms-Steuerelemente nach Funktion</span><span class="sxs-lookup"><span data-stu-id="19f18-129">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="19f18-130">[Vorgehensweise: Festlegen der Bildschirmposition von Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="19f18-130">[How to: Set the Screen Location of Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span></span>

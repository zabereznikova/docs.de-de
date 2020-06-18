---
title: Positionieren von Steuerelementen
description: Erfahren Sie, wie Sie die-Steuerelemente mit dem Windows Forms-Designer in Visual Studio oder der Location-Eigenschaft positionieren.
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
ms.openlocfilehash: 0aa3faade71e0f7e0a9d5e676327a80747524b8c
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904298"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="0dfba-103">Gewusst wie: Positionieren von Steuerelementen auf Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0dfba-103">How to: Position controls on Windows Forms</span></span>

<span data-ttu-id="0dfba-104">Verwenden Sie zum Positionieren von Steuerelementen die Windows Forms-Designer in Visual Studio, oder geben Sie die- <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="0dfba-104">To position controls, use the Windows Forms Designer in Visual Studio or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="0dfba-105">Positionieren eines Steuer Elements auf der Entwurfs Oberfläche des Windows Forms-Designer</span><span class="sxs-lookup"><span data-stu-id="0dfba-105">Position a control on the design surface of the Windows Forms Designer</span></span>

<span data-ttu-id="0dfba-106">Ziehen Sie das Steuerelement in Visual Studio mit der Maus an die entsprechende Position.</span><span class="sxs-lookup"><span data-stu-id="0dfba-106">In Visual Studio, drag the control to the appropriate location with the mouse.</span></span>

> [!NOTE]
> <span data-ttu-id="0dfba-107">Wählen Sie das Steuerelement aus, und verschieben Sie es mit den Pfeiltasten, um es genauer zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="0dfba-107">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="0dfba-108">Außerdem unterstützen Sie mit den Richtungs *Linien* , dass Sie Steuerelemente genau in Ihrem Formular platzieren.</span><span class="sxs-lookup"><span data-stu-id="0dfba-108">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="0dfba-109">Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Anordnen von Steuerelementen auf Windows Forms mithilfe](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)von Ausrichtungs Linien.</span><span class="sxs-lookup"><span data-stu-id="0dfba-109">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

## <a name="position-a-control-using-the-properties-window"></a><span data-ttu-id="0dfba-110">Positionieren eines Steuer Elements mithilfe des Eigenschaftenfenster</span><span class="sxs-lookup"><span data-stu-id="0dfba-110">Position a control using the Properties window</span></span>

1. <span data-ttu-id="0dfba-111">Wählen Sie in Visual Studio das Steuerelement aus, das Sie positionieren möchten.</span><span class="sxs-lookup"><span data-stu-id="0dfba-111">In Visual Studio, select the control you want to position.</span></span>

2. <span data-ttu-id="0dfba-112">Geben Sie im Fenster **Eigenschaften** Werte für die <xref:System.Windows.Forms.Control.Location%2A> durch Kommas getrennte Eigenschaft ein, um das Steuerelement in seinem Container zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="0dfba-112">In the **Properties** window, enter values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>

   <span data-ttu-id="0dfba-113">Die erste Zahl (X) ist die Entfernung vom linken Rand des Containers. die zweite Zahl (Y) ist der Abstand zwischen dem oberen Rand des Container Bereichs (gemessen in Pixel).</span><span class="sxs-lookup"><span data-stu-id="0dfba-113">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0dfba-114">Sie können die <xref:System.Windows.Forms.Control.Location%2A> -Eigenschaft erweitern, um die **X** -und **Y** -Werte einzeln einzugeben.</span><span class="sxs-lookup"><span data-stu-id="0dfba-114">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>

## <a name="position-a-control-programmatically"></a><span data-ttu-id="0dfba-115">Programm gesteuertes Positionieren eines Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="0dfba-115">Position a control programmatically</span></span>

1. <span data-ttu-id="0dfba-116">Legen Sie die- <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft des-Steuer Elements auf fest <xref:System.Drawing.Point> .</span><span class="sxs-lookup"><span data-stu-id="0dfba-116">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. <span data-ttu-id="0dfba-117">Ändern Sie die X-Koordinate der Position des Steuer Elements mithilfe der <xref:System.Windows.Forms.Control.Left%2A> untergeordneten Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="0dfba-117">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a><span data-ttu-id="0dfba-118">Programm gesteuertes erhöhen der Position eines Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="0dfba-118">Increment a control's location programmatically</span></span>

<span data-ttu-id="0dfba-119">Legen <xref:System.Windows.Forms.Control.Left%2A> Sie die untergeordnete Eigenschaft fest, um die X-Koordinate des Steuer Elements zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="0dfba-119">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>

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
> <span data-ttu-id="0dfba-120">Mit der <xref:System.Windows.Forms.Control.Location%2A> -Eigenschaft können Sie die X-und Y-Positionen eines Steuer Elements gleichzeitig festlegen.</span><span class="sxs-lookup"><span data-stu-id="0dfba-120">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="0dfba-121">Um eine Position einzeln festzulegen, verwenden Sie die <xref:System.Windows.Forms.Control.Left%2A> untergeordnete Eigenschaft (**X**) oder <xref:System.Windows.Forms.Control.Top%2A> (**Y**) des Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="0dfba-121">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="0dfba-122">Versuchen Sie nicht, die X-und Y-Koordinaten der <xref:System.Drawing.Point> -Struktur, die die Position der Schaltfläche darstellt, implizit festzulegen, da diese Struktur eine Kopie der Koordinaten der Schaltfläche enthält.</span><span class="sxs-lookup"><span data-stu-id="0dfba-122">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>

## <a name="see-also"></a><span data-ttu-id="0dfba-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0dfba-123">See also</span></span>

- [<span data-ttu-id="0dfba-124">Windows Forms Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="0dfba-124">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="0dfba-125">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien</span><span class="sxs-lookup"><span data-stu-id="0dfba-125">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="0dfba-126">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="0dfba-126">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="0dfba-127">Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="0dfba-127">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="0dfba-128">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="0dfba-128">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="0dfba-129">Steuerelemente für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0dfba-129">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="0dfba-130">Windows Forms-Steuerelemente nach Funktion</span><span class="sxs-lookup"><span data-stu-id="0dfba-130">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="0dfba-131">[Gewusst wie: Festlegen der Bildschirmposition von Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0dfba-131">[How to: Set the Screen Location of Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span></span>

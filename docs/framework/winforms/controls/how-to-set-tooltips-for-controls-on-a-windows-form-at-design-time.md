---
title: 'Vorgehensweise: Festlegen von QuickInfos für Steuerelemente auf einem Windows Form zur Entwurfszeit'
description: Erfahren Sie, wie Sie Quick Infos für Steuerelemente Programm gesteuert oder in der Windows Forms-Designer in Visual Studio festlegen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 144ba5b6bffb4a538e345f7b2df4a453fc6fd63d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618024"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="d67fe-103">Gewusst wie: Festlegen von Quick Infos für Steuerelemente auf einem Windows Form zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="d67fe-103">How to: Set ToolTips for controls on a Windows Form at design time</span></span>

<span data-ttu-id="d67fe-104">Sie können eine <xref:System.Windows.Forms.ToolTip> Zeichenfolge im Code oder in der Windows Forms-Designer in Visual Studio festlegen.</span><span class="sxs-lookup"><span data-stu-id="d67fe-104">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="d67fe-105">Weitere Informationen zur <xref:System.Windows.Forms.ToolTip> Komponente finden Sie unter Übersicht über die [ToolTip-Komponente](tooltip-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d67fe-105">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](tooltip-component-overview-windows-forms.md).</span></span>

## <a name="set-a-tooltip-programmatically"></a><span data-ttu-id="d67fe-106">Programm gesteuertes Festlegen einer QuickInfo</span><span class="sxs-lookup"><span data-stu-id="d67fe-106">Set a ToolTip programmatically</span></span>

1. <span data-ttu-id="d67fe-107">Fügen Sie das Steuerelement hinzu, das die QuickInfo anzeigt.</span><span class="sxs-lookup"><span data-stu-id="d67fe-107">Add the control that will display the ToolTip.</span></span>

2. <span data-ttu-id="d67fe-108">Verwenden Sie die- <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> Methode der- <xref:System.Windows.Forms.ToolTip> Komponente.</span><span class="sxs-lookup"><span data-stu-id="d67fe-108">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

    ```vb
    ' In this example, Button1 is the control to display the ToolTip.
    ToolTip1.SetToolTip(Button1, "Save changes")
    ```

    ```csharp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1.SetToolTip(button1, "Save changes");
    ```

    ```cpp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1->SetToolTip(button1, "Save changes");
    ```

## <a name="set-a-tooltip-in-the-designer"></a><span data-ttu-id="d67fe-109">Festlegen einer QuickInfo im Designer</span><span class="sxs-lookup"><span data-stu-id="d67fe-109">Set a ToolTip in the designer</span></span>

1. <span data-ttu-id="d67fe-110">Fügen Sie in Visual Studio <xref:System.Windows.Forms.ToolTip> dem Formular eine Komponente hinzu.</span><span class="sxs-lookup"><span data-stu-id="d67fe-110">In Visual Studio, add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>

2. <span data-ttu-id="d67fe-111">Wählen Sie das Steuerelement aus, von dem die QuickInfo angezeigt wird, oder fügen Sie es dem Formular hinzu.</span><span class="sxs-lookup"><span data-stu-id="d67fe-111">Select the control that will display the ToolTip, or add it to the form.</span></span>

3. <span data-ttu-id="d67fe-112">Legen Sie im Fenster **Eigenschaften** die QuickInfo **für den ToolTip1** -Wert auf eine entsprechende Text Zeichenfolge fest.</span><span class="sxs-lookup"><span data-stu-id="d67fe-112">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>

### <a name="to-remove-a-tooltip-programmatically"></a><span data-ttu-id="d67fe-113">So entfernen Sie eine QuickInfo Programm gesteuert</span><span class="sxs-lookup"><span data-stu-id="d67fe-113">To remove a ToolTip programmatically</span></span>

1. <span data-ttu-id="d67fe-114">Verwenden Sie die- <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> Methode der- <xref:System.Windows.Forms.ToolTip> Komponente.</span><span class="sxs-lookup"><span data-stu-id="d67fe-114">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

    ```vb
    ' In this example, Button1 is the control displaying the ToolTip.
    ToolTip1.SetToolTip(Button1, Nothing)
    ```

    ```csharp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1.SetToolTip(button1, null);
    ```

    ```cpp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1->SetToolTip(button1, NULL);
    ```

## <a name="remove-a-tooltip-in-the-designer"></a><span data-ttu-id="d67fe-115">Entfernen einer QuickInfo im Designer</span><span class="sxs-lookup"><span data-stu-id="d67fe-115">Remove a ToolTip in the designer</span></span>

1. <span data-ttu-id="d67fe-116">Wählen Sie in Visual Studio das Steuerelement aus, das die QuickInfo anzeigt.</span><span class="sxs-lookup"><span data-stu-id="d67fe-116">In Visual Studio, select the control that is displaying the ToolTip.</span></span>

2. <span data-ttu-id="d67fe-117">Löschen Sie im Fenster **Eigenschaften** den Text in der QuickInfo **auf ToolTip1**.</span><span class="sxs-lookup"><span data-stu-id="d67fe-117">In the **Properties** window, delete the text in the **ToolTip on ToolTip1**.</span></span>

## <a name="see-also"></a><span data-ttu-id="d67fe-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d67fe-118">See also</span></span>

- [<span data-ttu-id="d67fe-119">Übersicht über die ToolTip-Komponente</span><span class="sxs-lookup"><span data-stu-id="d67fe-119">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="d67fe-120">Vorgehensweise: Ändern der Verzögerung der ToolTip-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d67fe-120">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [<span data-ttu-id="d67fe-121">ToolTip-Komponente</span><span class="sxs-lookup"><span data-stu-id="d67fe-121">ToolTip Component</span></span>](tooltip-component-windows-forms.md)

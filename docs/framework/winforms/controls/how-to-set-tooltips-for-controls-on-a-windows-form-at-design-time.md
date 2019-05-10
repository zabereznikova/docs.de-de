---
title: 'Vorgehensweise: Festlegen von QuickInfos für Steuerelemente auf einem Windows Form zur Entwurfszeit'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 0d6725fc1a00826870e6400bffce63a1788e802c
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211687"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="40348-102">Vorgehensweise: Festlegen von QuickInfos für Steuerelemente in Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="40348-102">How to: Set ToolTips for controls on a Windows Form at design time</span></span>

<span data-ttu-id="40348-103">Sie können festlegen, eine <xref:System.Windows.Forms.ToolTip> Zeichenfolge im Code oder in Windows Forms-Designer in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="40348-103">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="40348-104">Weitere Informationen zu den <xref:System.Windows.Forms.ToolTip> Komponente finden Sie unter [Übersicht über die ToolTip-Komponente](tooltip-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="40348-104">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](tooltip-component-overview-windows-forms.md).</span></span>

## <a name="set-a-tooltip-programmatically"></a><span data-ttu-id="40348-105">Programmgesteuertes Festlegen einer QuickInfos</span><span class="sxs-lookup"><span data-stu-id="40348-105">Set a ToolTip programmatically</span></span>

1. <span data-ttu-id="40348-106">Fügen Sie das Steuerelement, das die QuickInfo angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="40348-106">Add the control that will display the ToolTip.</span></span>

2. <span data-ttu-id="40348-107">Verwenden der <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> Methode der <xref:System.Windows.Forms.ToolTip> Komponente.</span><span class="sxs-lookup"><span data-stu-id="40348-107">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

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

## <a name="set-a-tooltip-in-the-designer"></a><span data-ttu-id="40348-108">Festlegen einer QuickInfos im designer</span><span class="sxs-lookup"><span data-stu-id="40348-108">Set a ToolTip in the designer</span></span>

1. <span data-ttu-id="40348-109">Fügen Sie in Visual Studio eine <xref:System.Windows.Forms.ToolTip> -Komponente zum Formular.</span><span class="sxs-lookup"><span data-stu-id="40348-109">In Visual Studio, add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>

2. <span data-ttu-id="40348-110">Wählen Sie das Steuerelement, das die QuickInfo angezeigt, oder fügen Sie es dem Formular hinzu.</span><span class="sxs-lookup"><span data-stu-id="40348-110">Select the control that will display the ToolTip, or add it to the form.</span></span>

3. <span data-ttu-id="40348-111">In der **Eigenschaften** legen die **QuickInfo auf ToolTip1** Wert, der eine entsprechende Zeichenfolge des Texts.</span><span class="sxs-lookup"><span data-stu-id="40348-111">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>

### <a name="to-remove-a-tooltip-programmatically"></a><span data-ttu-id="40348-112">Das programmgesteuerte Entfernen von einer QuickInfo</span><span class="sxs-lookup"><span data-stu-id="40348-112">To remove a ToolTip programmatically</span></span>

1. <span data-ttu-id="40348-113">Verwenden der <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> Methode der <xref:System.Windows.Forms.ToolTip> Komponente.</span><span class="sxs-lookup"><span data-stu-id="40348-113">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

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

## <a name="remove-a-tooltip-in-the-designer"></a><span data-ttu-id="40348-114">Entfernen einer QuickInfos im designer</span><span class="sxs-lookup"><span data-stu-id="40348-114">Remove a ToolTip in the designer</span></span>

1. <span data-ttu-id="40348-115">Wählen Sie in Visual Studio das Steuerelement, das die QuickInfo angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="40348-115">In Visual Studio, select the control that is displaying the ToolTip.</span></span>

2. <span data-ttu-id="40348-116">In der **Eigenschaften** Fenster, löschen Sie den Text in die **QuickInfo auf ToolTip1**.</span><span class="sxs-lookup"><span data-stu-id="40348-116">In the **Properties** window, delete the text in the **ToolTip on ToolTip1**.</span></span>

## <a name="see-also"></a><span data-ttu-id="40348-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40348-117">See also</span></span>

- [<span data-ttu-id="40348-118">Übersicht über die ToolTip-Komponente</span><span class="sxs-lookup"><span data-stu-id="40348-118">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="40348-119">Vorgehensweise: Ändern der Verzögerung der ToolTip-Komponente von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="40348-119">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [<span data-ttu-id="40348-120">ToolTip-Komponente</span><span class="sxs-lookup"><span data-stu-id="40348-120">ToolTip Component</span></span>](tooltip-component-windows-forms.md)

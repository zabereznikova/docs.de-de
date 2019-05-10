---
title: 'Vorgehensweise: Anzeigen der kontextbezogenen Hilfe'
ms.date: 03/30/2017
helpviewer_keywords:
- pop-up Help
- Help [Windows Forms], pop-up Help
- Windows Forms, displaying Help
- forms [Windows Forms], displaying Help
- modal dialog boxes [Windows Forms], pop-up Help
- F1 Help [Windows Forms], in dialog boxes
- HelpProvider component [Windows Forms]
- Help [Windows Forms], adding to dialog boxes
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
ms.openlocfilehash: bf3bcbff0cd6f3bbf71e96e748cb170d5ce68dfc
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211398"
---
# <a name="how-to-display-pop-up-help"></a><span data-ttu-id="206ba-102">Vorgehensweise: Kontextbezogene Hilfe anzeigen</span><span class="sxs-lookup"><span data-stu-id="206ba-102">How to: Display pop-up Help</span></span>

<span data-ttu-id="206ba-103">Eine Möglichkeit zum Anzeigen von Hilfe in Windows Forms die **Hilfe** Schaltfläche auf der rechten Seite der Titelleiste, über die <xref:System.Windows.Forms.Form.HelpButton%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="206ba-103">One way to display Help on Windows Forms is through the **Help** button, located on the right side of the title bar, accessible through the <xref:System.Windows.Forms.Form.HelpButton%2A> property.</span></span> <span data-ttu-id="206ba-104">Diese Art, die Hilfe aufzurufen, eignet sich besonders für Dialogfelder.</span><span class="sxs-lookup"><span data-stu-id="206ba-104">This type of Help display is well-suited for use with dialog boxes.</span></span> <span data-ttu-id="206ba-105">In modal (mit der <xref:System.Windows.Forms.Form.ShowDialog%2A>-Methode) angezeigten Dialogfeldern ist das Aufrufen externer Hilfesysteme problematisch, da modale Dialogfelder zuerst geschlossen werden müssen, ehe der Fokus auf ein anderes Fenster gerichtet werden kann.</span><span class="sxs-lookup"><span data-stu-id="206ba-105">Dialog boxes shown modally (with the <xref:System.Windows.Forms.Form.ShowDialog%2A> method) have trouble bringing up external Help systems, because modal dialog boxes need to be closed before focus can shift to another window.</span></span> <span data-ttu-id="206ba-106">Außerdem ist die Verwendung der **Hilfe** Schaltfläche ist erforderlich, dass es ist keine **Minimieren** Schaltfläche oder **Maximieren** Schaltfläche in der Titelleiste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="206ba-106">Additionally, using the **Help** button requires that there is no **Minimize** button or **Maximize** button shown in the title bar.</span></span> <span data-ttu-id="206ba-107">Dies ist eine Konvention Dialogfelder, während der Formulare, die in der Regel über **Minimieren** und **Maximieren** Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="206ba-107">This is a standard dialog-box convention, whereas forms usually have **Minimize** and **Maximize** buttons.</span></span>

<span data-ttu-id="206ba-108">Sie können auch die <xref:System.Windows.Forms.HelpProvider> Komponente, um Steuerelemente auf Dateien in einem Hilfesystem verknüpfen, auch wenn Sie kontextbezogene Hilfe implementiert haben.</span><span class="sxs-lookup"><span data-stu-id="206ba-108">You can also use the <xref:System.Windows.Forms.HelpProvider> component to link controls to files in a Help system, even if you have implemented pop-up Help.</span></span> <span data-ttu-id="206ba-109">Weitere Informationen finden Sie unter [Bereitstellen von Hilfeinformationen in einer Windows-Anwendung](how-to-provide-help-in-a-windows-application.md).</span><span class="sxs-lookup"><span data-stu-id="206ba-109">For more information, see [Providing Help in a Windows Application](how-to-provide-help-in-a-windows-application.md).</span></span>

## <a name="display-pop-up-help"></a><span data-ttu-id="206ba-110">Kontextbezogene Hilfe anzeigen</span><span class="sxs-lookup"><span data-stu-id="206ba-110">Display pop-up Help</span></span>

1. <span data-ttu-id="206ba-111">Ziehen Sie in Visual Studio eine [HelpProvider](../controls/helpprovider-component-windows-forms.md) -Komponente aus der Toolbox zu Ihrem Formular.</span><span class="sxs-lookup"><span data-stu-id="206ba-111">In Visual Studio, drag a [HelpProvider](../controls/helpprovider-component-windows-forms.md) component from the Toolbox to your form.</span></span>

   <span data-ttu-id="206ba-112">Sie befindet sich in der Komponentenleiste im unteren Bereich des Windows Forms Designer.</span><span class="sxs-lookup"><span data-stu-id="206ba-112">It will sit in the tray at the bottom of the Windows Forms Designer.</span></span>

2. <span data-ttu-id="206ba-113">Legen Sie im Fenster "Eigenschaften" die Eigenschaft <xref:System.Windows.Forms.Form.HelpButton%2A> auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="206ba-113">In the Properties window, set the <xref:System.Windows.Forms.Form.HelpButton%2A> property to `true`.</span></span> <span data-ttu-id="206ba-114">Dadurch wird in der Titelleiste des Formulars auf der rechten Seite eine Schaltfläche mit einem Fragezeichen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="206ba-114">This will display a button with a question mark in it on the right side of the title bar of the form.</span></span>

3. <span data-ttu-id="206ba-115">Damit die Hilfeschaltfläche <xref:System.Windows.Forms.Form.HelpButton%2A> angezeigt werden kann, müssen Sie die Eigenschaften <xref:System.Windows.Forms.Form.MinimizeBox%2A> und <xref:System.Windows.Forms.Form.MaximizeBox%2A> des Formulars auf `false`, die Eigenschaft <xref:System.Windows.Forms.Form.ControlBox%2A> auf `true` und die Eigenschaft <xref:System.Windows.Forms.Form.FormBorderStyle%2A> auf einen der folgenden Werte festlegen: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> oder <xref:System.Windows.Forms.FormBorderStyle.Sizable>.</span><span class="sxs-lookup"><span data-stu-id="206ba-115">In order for the <xref:System.Windows.Forms.Form.HelpButton%2A> to display, the form's <xref:System.Windows.Forms.Form.MinimizeBox%2A> and <xref:System.Windows.Forms.Form.MaximizeBox%2A> properties must be set to `false`, the <xref:System.Windows.Forms.Form.ControlBox%2A> property set to `true`, and the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to one of the following values: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> or <xref:System.Windows.Forms.FormBorderStyle.Sizable>.</span></span>

4. <span data-ttu-id="206ba-116">Wählen Sie das Steuerelement aus, für das Sie Hilfeinformationen in Ihrem Formular anzeigen möchten, und legen Sie im Fenster "Eigenschaften" den Hilfetext fest.</span><span class="sxs-lookup"><span data-stu-id="206ba-116">Select the control for which you want to show help on your form and set the Help string in the Properties window.</span></span> <span data-ttu-id="206ba-117">Dies ist die Zeichenfolge mit Text, der in ein ähnliches Fenster angezeigt wird eine [QuickInfo](../controls/tooltip-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="206ba-117">This is the string of text that will be displayed in a window similar to a [ToolTip](../controls/tooltip-component-windows-forms.md).</span></span>

5. <span data-ttu-id="206ba-118">Drücken Sie **F5**.</span><span class="sxs-lookup"><span data-stu-id="206ba-118">Press **F5**.</span></span>

6. <span data-ttu-id="206ba-119">Drücken Sie die **Hilfe** in der Titelleiste auf die Schaltfläche, und klicken Sie auf das Steuerelement auf dem Sie den Hilfetext festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="206ba-119">Press the **Help** button on the title bar and click the control on which you set the Help string.</span></span>

## <a name="see-also"></a><span data-ttu-id="206ba-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="206ba-120">See also</span></span>

- [<span data-ttu-id="206ba-121">Benutzerführung mithilfe von QuickInfos</span><span class="sxs-lookup"><span data-stu-id="206ba-121">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)
- [<span data-ttu-id="206ba-122">Integrieren von Benutzerhilfe in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="206ba-122">Integrating User Help in Windows Forms</span></span>](integrating-user-help-in-windows-forms.md)
- [<span data-ttu-id="206ba-123">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="206ba-123">Windows Forms</span></span>](../index.md)

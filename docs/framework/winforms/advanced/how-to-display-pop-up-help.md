---
title: 'Gewusst wie: Anzeigen der kontextbezogenen Hilfe'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e5f57e0a7981e8cae93960c8ffc3ed2168594cf5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-pop-up-help"></a><span data-ttu-id="c826e-102">Gewusst wie: Anzeigen der kontextbezogenen Hilfe</span><span class="sxs-lookup"><span data-stu-id="c826e-102">How to: Display Pop-up Help</span></span>
<span data-ttu-id="c826e-103">Eine Möglichkeit zum Anzeigen von Hilfe in Windows Forms wird durch die **Hilfe** Schaltfläche auf der rechten Seite der Titelleiste, über die <xref:System.Windows.Forms.Form.HelpButton%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c826e-103">One way to display Help on Windows Forms is through the **Help** button, located on the right side of the title bar, accessible through the <xref:System.Windows.Forms.Form.HelpButton%2A> property.</span></span> <span data-ttu-id="c826e-104">Diese Art, die Hilfe aufzurufen, eignet sich besonders für Dialogfelder.</span><span class="sxs-lookup"><span data-stu-id="c826e-104">This type of Help display is well-suited for use with dialog boxes.</span></span> <span data-ttu-id="c826e-105">In modal (mit der <xref:System.Windows.Forms.Form.ShowDialog%2A>-Methode) angezeigten Dialogfeldern ist das Aufrufen externer Hilfesysteme problematisch, da modale Dialogfelder zuerst geschlossen werden müssen, ehe der Fokus auf ein anderes Fenster gerichtet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c826e-105">Dialog boxes shown modally (with the <xref:System.Windows.Forms.Form.ShowDialog%2A> method) have trouble bringing up external Help systems, because modal dialog boxes need to be closed before focus can shift to another window.</span></span> <span data-ttu-id="c826e-106">Darüber hinaus verwenden die **Hilfe** Schaltfläche erfordert, ergibt sich keine **Minimieren** Schaltfläche oder **Maximieren** Schaltfläche in der Titelleiste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c826e-106">Additionally, using the **Help** button requires that there is no **Minimize** button or **Maximize** button shown in the title bar.</span></span> <span data-ttu-id="c826e-107">Dies ist eine Konvention Standardkonvention für Dialogfelder, wohingegen Formulare in der Regel sind **Minimieren** und **Maximieren** Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="c826e-107">This is a standard dialog-box convention, whereas forms usually have **Minimize** and **Maximize** buttons.</span></span>  
  
 <span data-ttu-id="c826e-108">Denken Sie daran, dass Sie Steuerelemente auch mithilfe der <xref:System.Windows.Forms.HelpProvider>-Komponente mit Dateien in einem  Hilfesystem verknüpfen können, selbst wenn Sie kontextbezogene Hilfe implementiert haben.</span><span class="sxs-lookup"><span data-stu-id="c826e-108">Be aware that you can also use the <xref:System.Windows.Forms.HelpProvider> component to link controls to files in a Help system, even if you have implemented pop-up Help.</span></span> <span data-ttu-id="c826e-109">Weitere Informationen finden Sie unter [Bereitstellen von Hilfeinformationen in einer Windows-Anwendung](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md).</span><span class="sxs-lookup"><span data-stu-id="c826e-109">For more information, see [Providing Help in a Windows Application](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c826e-110">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="c826e-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c826e-111">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c826e-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c826e-112">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="c826e-112">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-display-pop-up-help"></a><span data-ttu-id="c826e-113">So zeigen Sie kontextbezogene Hilfe an</span><span class="sxs-lookup"><span data-stu-id="c826e-113">To display pop-up Help</span></span>  
  
1.  <span data-ttu-id="c826e-114">Ziehen Sie eine [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) -Komponente aus der Toolbox in Ihr Formular.</span><span class="sxs-lookup"><span data-stu-id="c826e-114">Drag a [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) component from the Toolbox to your form.</span></span>  
  
     <span data-ttu-id="c826e-115">Sie befindet sich in der Komponentenleiste im unteren Bereich des Windows Forms Designer.</span><span class="sxs-lookup"><span data-stu-id="c826e-115">It will sit in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="c826e-116">Legen Sie im Fenster "Eigenschaften" die Eigenschaft <xref:System.Windows.Forms.Form.HelpButton%2A> auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="c826e-116">In the Properties window, set the <xref:System.Windows.Forms.Form.HelpButton%2A> property to `true`.</span></span> <span data-ttu-id="c826e-117">Dadurch wird in der Titelleiste des Formulars auf der rechten Seite eine Schaltfläche mit einem Fragezeichen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c826e-117">This will display a button with a question mark in it on the right side of the title bar of the form.</span></span>  
  
3.  <span data-ttu-id="c826e-118">Damit die Hilfeschaltfläche <xref:System.Windows.Forms.Form.HelpButton%2A> angezeigt werden kann, müssen Sie die Eigenschaften <xref:System.Windows.Forms.Form.MinimizeBox%2A> und <xref:System.Windows.Forms.Form.MaximizeBox%2A> des Formulars auf `false`, die Eigenschaft <xref:System.Windows.Forms.Form.ControlBox%2A> auf `true` und die Eigenschaft <xref:System.Windows.Forms.Form.FormBorderStyle%2A> auf einen der folgenden Werte festlegen: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> oder <xref:System.Windows.Forms.FormBorderStyle.Sizable>.</span><span class="sxs-lookup"><span data-stu-id="c826e-118">In order for the <xref:System.Windows.Forms.Form.HelpButton%2A> to display, the form's <xref:System.Windows.Forms.Form.MinimizeBox%2A> and <xref:System.Windows.Forms.Form.MaximizeBox%2A> properties must be set to `false`, the <xref:System.Windows.Forms.Form.ControlBox%2A> property set to `true`, and the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to one of the following values: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> or <xref:System.Windows.Forms.FormBorderStyle.Sizable>.</span></span>  
  
4.  <span data-ttu-id="c826e-119">Wählen Sie das Steuerelement aus, für das Sie Hilfeinformationen in Ihrem Formular anzeigen möchten, und legen Sie im Fenster "Eigenschaften" den Hilfetext fest.</span><span class="sxs-lookup"><span data-stu-id="c826e-119">Select the control for which you want to show help on your form and set the Help string in the Properties window.</span></span> <span data-ttu-id="c826e-120">Dies ist die Zeichenfolge in einem Fenster ähnlich angezeigte Text einer [QuickInfo](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c826e-120">This is the string of text that will be displayed in a window similar to a [ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md).</span></span>  
  
5.  <span data-ttu-id="c826e-121">Drücken Sie **F5**.</span><span class="sxs-lookup"><span data-stu-id="c826e-121">Press **F5**.</span></span>  
  
6.  <span data-ttu-id="c826e-122">Drücken Sie die **Hilfe** in der Titelleiste auf die Schaltfläche, und klicken Sie auf das Steuerelement auf dem Sie den Hilfetext festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="c826e-122">Press the **Help** button on the title bar and click the control on which you set the Help string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c826e-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c826e-123">See Also</span></span>  
 [<span data-ttu-id="c826e-124">Benutzerführung mithilfe von QuickInfos</span><span class="sxs-lookup"><span data-stu-id="c826e-124">Control Help Using ToolTips</span></span>](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 [<span data-ttu-id="c826e-125">Integrieren von Benutzerhilfe in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c826e-125">Integrating User Help in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [<span data-ttu-id="c826e-126">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c826e-126">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)

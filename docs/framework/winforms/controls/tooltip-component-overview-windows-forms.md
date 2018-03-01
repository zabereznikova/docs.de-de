---
title: "Übersicht über die ToolTip-Komponente (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fce1cb5750197e52461b4883f1238325fa10fc5e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="tooltip-component-overview-windows-forms"></a><span data-ttu-id="cb329-102">Übersicht über die ToolTip-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="cb329-102">ToolTip Component Overview (Windows Forms)</span></span>
<span data-ttu-id="cb329-103">Die <xref:System.Windows.Forms.ToolTip>-Komponente in Windows Forms zeigt Text an, wenn der Benutzer auf Steuerelemente zeigt.</span><span class="sxs-lookup"><span data-stu-id="cb329-103">The Windows Forms <xref:System.Windows.Forms.ToolTip> component displays text when the user points at controls.</span></span> <span data-ttu-id="cb329-104">Jedem Steuerelement kann eine QuickInfo zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="cb329-104">A ToolTip can be associated with any control.</span></span> <span data-ttu-id="cb329-105">Ein Beispiel für die Verwendung dieser Komponente: um Speicherplatz auf einem Formular zu speichern, können Sie ein kleines Symbol auf einer Schaltfläche anzeigen und verwenden Sie eine QuickInfo, um die Funktion der Schaltfläche zu erklären.</span><span class="sxs-lookup"><span data-stu-id="cb329-105">An example use of this component: to save space on a form, you can display a small icon on a button and use a ToolTip to explain the button's function.</span></span>  
  
## <a name="working-with-the-tooltip-component"></a><span data-ttu-id="cb329-106">Arbeiten mit der ToolTip-Komponente</span><span class="sxs-lookup"><span data-stu-id="cb329-106">Working with the ToolTip Component</span></span>  
 <span data-ttu-id="cb329-107">Ein <xref:System.Windows.Forms.ToolTip> Komponente bietet eine `ToolTip` -Eigenschaft für mehrere Steuerelemente auf einem Windows Form oder einem anderen Container.</span><span class="sxs-lookup"><span data-stu-id="cb329-107">A <xref:System.Windows.Forms.ToolTip> component provides a `ToolTip` property to multiple controls on a Windows Form or other container.</span></span> <span data-ttu-id="cb329-108">Angenommen, wenn Sie eine ablegen <xref:System.Windows.Forms.ToolTip> Komponente auf einem Formular anzeigen "Geben Sie hier Ihren Namen" für eine <xref:System.Windows.Forms.TextBox> steuern und "Klicken Sie hier, um Änderungen zu speichern" für eine <xref:System.Windows.Forms.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="cb329-108">For example, if you place one <xref:System.Windows.Forms.ToolTip> component on a form, you can display "Type your name here" for a <xref:System.Windows.Forms.TextBox> control and "Click here to save changes" for a <xref:System.Windows.Forms.Button> control.</span></span>  
  
 <span data-ttu-id="cb329-109">Folgende Schlüsselmethoden der <xref:System.Windows.Forms.ToolTip> Komponente <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> und <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>.</span><span class="sxs-lookup"><span data-stu-id="cb329-109">The key methods of the <xref:System.Windows.Forms.ToolTip> component are <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> and <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>.</span></span> <span data-ttu-id="cb329-110">Sie können die <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> -Methode zum Festlegen von QuickInfos für Steuerelemente angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb329-110">You can use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method to set the ToolTips displayed for controls.</span></span> <span data-ttu-id="cb329-111">Weitere Informationen finden Sie unter [Vorgehensweise: Festlegen von QuickInfos für Steuerelemente in einem Windows Form zur Entwurfszeit](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="cb329-111">For more information, see [How to: Set ToolTips for Controls on a Windows Form at Design Time](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md).</span></span> <span data-ttu-id="cb329-112">Die Schlüsseleigenschaften sind <xref:System.Windows.Forms.ToolTip.Active%2A>, dem muss festgelegt werden, um `true` für die QuickInfo angezeigt wird, und <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, wodurch die Zeitdauer, die die QuickInfo-Zeichenfolge angezeigt wird, wie lange die Benutzer auf das Steuerelement für die QuickInfo angezeigt wird, verweisen muss und wie er zu lang wird für nachfolgende QuickInfo-Fenster angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cb329-112">The key properties are <xref:System.Windows.Forms.ToolTip.Active%2A>, which must be set to `true` for the ToolTip to appear, and <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, which sets the length of time that the ToolTip string is shown, how long the user must point at the control for the ToolTip to appear, and how long it takes for subsequent ToolTip windows to appear.</span></span> <span data-ttu-id="cb329-113">Weitere Informationen finden Sie unter [Vorgehensweise: Ändern der Verzögerung der ToolTip-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).</span><span class="sxs-lookup"><span data-stu-id="cb329-113">For more information, see [How to: Change the Delay of the Windows Forms ToolTip Component](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb329-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb329-114">See Also</span></span>  
 <xref:System.Windows.Forms.ToolTip>  
 [<span data-ttu-id="cb329-115">Gewusst wie: Festlegen von QuickInfos für Steuerelemente auf einem Windows Form zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="cb329-115">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [<span data-ttu-id="cb329-116">Gewusst wie: Ändern der Verzögerung der ToolTip-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cb329-116">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)

---
title: "Gewusst wie: Gruppieren von RadioButton-Steuerelementen in Windows Forms für die Verwendung als Set"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c92048374941f735568bcd758ed475eba78b81e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a><span data-ttu-id="d8d7c-102">Gewusst wie: Gruppieren von RadioButton-Steuerelementen in Windows Forms für die Verwendung als Set</span><span class="sxs-lookup"><span data-stu-id="d8d7c-102">How to: Group Windows Forms RadioButton Controls to Function as a Set</span></span>
<span data-ttu-id="d8d7c-103">Windows Forms <xref:System.Windows.Forms.RadioButton> Steuerelemente wurden dafür entwickelt, darin, Benutzern eine Auswahl aus mindestens zwei Einstellungen, von denen nur eine an eine Prozedur oder das Objekt zugewiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d8d7c-103">Windows Forms <xref:System.Windows.Forms.RadioButton> controls are designed to give users a choice among two or more settings, of which only one can be assigned to a procedure or object.</span></span> <span data-ttu-id="d8d7c-104">Angenommen, eine Gruppe von <xref:System.Windows.Forms.RadioButton> Steuerelemente können eine Auswahl von Transportunternehmen für eine Bestellung anzeigen, aber nur eines der Netzbetreiber verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d8d7c-104">For example, a group of <xref:System.Windows.Forms.RadioButton> controls may display a choice of package carriers for an order, but only one of the carriers will be used.</span></span> <span data-ttu-id="d8d7c-105">Daher nur ein <xref:System.Windows.Forms.RadioButton> zu einem Zeitpunkt kann ausgewählt werden, auch wenn sie einen Teil einer funktionalen Gruppe ist.</span><span class="sxs-lookup"><span data-stu-id="d8d7c-105">Therefore only one <xref:System.Windows.Forms.RadioButton> at a time can be selected, even if it is a part of a functional group.</span></span>  
  
 <span data-ttu-id="d8d7c-106">Sie Optionsfelder gruppieren, indem Sie z. B. innerhalb eines Containers Zeichnen einer <xref:System.Windows.Forms.Panel> -Steuerelement, ein <xref:System.Windows.Forms.GroupBox> Steuerelement oder ein Formular.</span><span class="sxs-lookup"><span data-stu-id="d8d7c-106">You group radio buttons by drawing them inside a container such as a <xref:System.Windows.Forms.Panel> control, a <xref:System.Windows.Forms.GroupBox> control, or a form.</span></span> <span data-ttu-id="d8d7c-107">Alle Optionsfelder, die direkt auf einem Formular werden einer Gruppe hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d8d7c-107">All radio buttons that are added directly to a form become one group.</span></span> <span data-ttu-id="d8d7c-108">Um separate Gruppen hinzuzufügen, müssen Sie sie innerhalb von Bereichen oder Gruppenfelder platzieren.</span><span class="sxs-lookup"><span data-stu-id="d8d7c-108">To add separate groups, you must place them inside panels or group boxes.</span></span> <span data-ttu-id="d8d7c-109">Weitere Informationen zu Bereichen oder Gruppenfelder, finden Sie unter [Übersicht über das Panel-Steuerelement](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md) oder [Übersicht über das GroupBox-Steuerelement](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d8d7c-109">For more information about panels or group boxes, see [Panel Control Overview](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md) or [GroupBox Control Overview](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a><span data-ttu-id="d8d7c-110">Zum Gruppieren von RadioButton-Steuerelementen als einen Satz an die Funktion unabhängig von anderen Sätze</span><span class="sxs-lookup"><span data-stu-id="d8d7c-110">To group RadioButton controls as a set to function independently of other sets</span></span>  
  
1.  <span data-ttu-id="d8d7c-111">Ziehen Sie eine <xref:System.Windows.Forms.GroupBox> oder <xref:System.Windows.Forms.Panel> -Steuerelement aus der **Windows Forms** Registerkarte auf die **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="d8d7c-111">Drag a <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab on the **Toolbox** onto the form.</span></span>  
  
2.  <span data-ttu-id="d8d7c-112">Zeichnen <xref:System.Windows.Forms.RadioButton> auf steuert die <xref:System.Windows.Forms.GroupBox> oder <xref:System.Windows.Forms.Panel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="d8d7c-112">Draw <xref:System.Windows.Forms.RadioButton> controls on the <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8d7c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8d7c-113">See Also</span></span>  
 <xref:System.Windows.Forms.RadioButton>  
 [<span data-ttu-id="d8d7c-114">Übersicht über das RadioButton-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d8d7c-114">RadioButton Control Overview</span></span>](../../../../docs/framework/winforms/controls/radiobutton-control-overview-windows-forms.md)  
 [<span data-ttu-id="d8d7c-115">Übersicht über das Panel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d8d7c-115">Panel Control Overview</span></span>](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [<span data-ttu-id="d8d7c-116">Übersicht über das GroupBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d8d7c-116">GroupBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="d8d7c-117">Übersicht über das CheckBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d8d7c-117">CheckBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="d8d7c-118">RadioButton-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d8d7c-118">RadioButton Control</span></span>](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)

---
title: Gruppieren von RadioButton-Steuerelementen als Satz
description: Erfahren Sie, wie Sie Windows Forms RadioButton-Steuerelemente gruppieren, um unabhängig von anderen Sätzen zu funktionieren.
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: 9f6795330922e739cca1f2b5c11bb2ec68bb4e84
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325919"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a><span data-ttu-id="88aa0-103">Vorgehensweise: Gruppieren von RadioButton-Steuerelementen in Windows Forms für die Verwendung als Set</span><span class="sxs-lookup"><span data-stu-id="88aa0-103">How to: Group Windows Forms RadioButton Controls to Function as a Set</span></span>
<span data-ttu-id="88aa0-104">Windows Forms Steuer <xref:System.Windows.Forms.RadioButton> Elemente dienen dazu, Benutzern eine Auswahl zwischen zwei oder mehr Einstellungen zu geben, denen nur eine Prozedur oder ein Objekt zugewiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="88aa0-104">Windows Forms <xref:System.Windows.Forms.RadioButton> controls are designed to give users a choice among two or more settings, of which only one can be assigned to a procedure or object.</span></span> <span data-ttu-id="88aa0-105">Beispielsweise kann eine Gruppe von Steuer <xref:System.Windows.Forms.RadioButton> Elementen eine Auswahl von Paket Trägern für eine Bestellung anzeigen, es wird jedoch nur einer der Träger verwendet.</span><span class="sxs-lookup"><span data-stu-id="88aa0-105">For example, a group of <xref:System.Windows.Forms.RadioButton> controls may display a choice of package carriers for an order, but only one of the carriers will be used.</span></span> <span data-ttu-id="88aa0-106">Daher kann nur jeweils eine <xref:System.Windows.Forms.RadioButton> ausgewählt werden, auch wenn Sie Teil einer Funktionsgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="88aa0-106">Therefore only one <xref:System.Windows.Forms.RadioButton> at a time can be selected, even if it is a part of a functional group.</span></span>  
  
 <span data-ttu-id="88aa0-107">Sie gruppieren Options Felder, indem Sie Sie in einem Container, z. b. einem <xref:System.Windows.Forms.Panel> Steuerelement, einem <xref:System.Windows.Forms.GroupBox> Steuerelement oder einem Formular, zeichnen.</span><span class="sxs-lookup"><span data-stu-id="88aa0-107">You group radio buttons by drawing them inside a container such as a <xref:System.Windows.Forms.Panel> control, a <xref:System.Windows.Forms.GroupBox> control, or a form.</span></span> <span data-ttu-id="88aa0-108">Alle Options Felder, die einem Formular direkt hinzugefügt werden, werden zu einer Gruppe.</span><span class="sxs-lookup"><span data-stu-id="88aa0-108">All radio buttons that are added directly to a form become one group.</span></span> <span data-ttu-id="88aa0-109">Um separate Gruppen hinzuzufügen, müssen Sie Sie in Panels oder Gruppen Feldern platzieren.</span><span class="sxs-lookup"><span data-stu-id="88aa0-109">To add separate groups, you must place them inside panels or group boxes.</span></span> <span data-ttu-id="88aa0-110">Weitere Informationen zu Panels oder Gruppen Feldern finden Sie unter Übersicht über das [Panel-Steuer](panel-control-overview-windows-forms.md) Element oder Übersicht über das [GroupBox-Steuer](groupbox-control-overview-windows-forms.md)Element.</span><span class="sxs-lookup"><span data-stu-id="88aa0-110">For more information about panels or group boxes, see [Panel Control Overview](panel-control-overview-windows-forms.md) or [GroupBox Control Overview](groupbox-control-overview-windows-forms.md).</span></span>  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a><span data-ttu-id="88aa0-111">So gruppieren Sie RadioButton-Steuerelemente als eine Menge, die unabhängig von anderen Sätzen funktioniert</span><span class="sxs-lookup"><span data-stu-id="88aa0-111">To group RadioButton controls as a set to function independently of other sets</span></span>  
  
1. <span data-ttu-id="88aa0-112">Ziehen Sie ein-Steuerelement oder ein- <xref:System.Windows.Forms.GroupBox> <xref:System.Windows.Forms.Panel> Steuerelement von der Registerkarte **Windows Forms** der **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="88aa0-112">Drag a <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab on the **Toolbox** onto the form.</span></span>  
  
2. <span data-ttu-id="88aa0-113">Zeichnen Sie <xref:System.Windows.Forms.RadioButton> Steuerelemente auf dem- <xref:System.Windows.Forms.GroupBox> oder-Steuerelement <xref:System.Windows.Forms.Panel> .</span><span class="sxs-lookup"><span data-stu-id="88aa0-113">Draw <xref:System.Windows.Forms.RadioButton> controls on the <xref:System.Windows.Forms.GroupBox> or <xref:System.Windows.Forms.Panel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88aa0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88aa0-114">See also</span></span>

- <xref:System.Windows.Forms.RadioButton>
- [<span data-ttu-id="88aa0-115">Übersicht über das RadioButton-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="88aa0-115">RadioButton Control Overview</span></span>](radiobutton-control-overview-windows-forms.md)
- [<span data-ttu-id="88aa0-116">Übersicht über das Panel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="88aa0-116">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="88aa0-117">Übersicht über das GroupBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="88aa0-117">GroupBox Control Overview</span></span>](groupbox-control-overview-windows-forms.md)
- [<span data-ttu-id="88aa0-118">Übersicht über das CheckBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="88aa0-118">CheckBox Control Overview</span></span>](checkbox-control-overview-windows-forms.md)
- [<span data-ttu-id="88aa0-119">RadioButton-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="88aa0-119">RadioButton Control</span></span>](radiobutton-control-windows-forms.md)

---
title: 'Vorgehensweise: Ändern der Verzögerung der ToolTip-Komponente in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
ms.openlocfilehash: cf257cccd272c16c3d7c3d403456265444fc8ac8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781237"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a><span data-ttu-id="31939-102">Vorgehensweise: Ändern der Verzögerung der ToolTip-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="31939-102">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>
<span data-ttu-id="31939-103">Es gibt mehrere Verzögerungswerte, die Sie für eine Windows Forms festlegen können <xref:System.Windows.Forms.ToolTip> Komponente.</span><span class="sxs-lookup"><span data-stu-id="31939-103">There are multiple delay values that you can set for a Windows Forms <xref:System.Windows.Forms.ToolTip> component.</span></span> <span data-ttu-id="31939-104">Die Maßeinheit für alle diese Eigenschaften ist Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="31939-104">The unit of measure for all these properties is milliseconds.</span></span> <span data-ttu-id="31939-105">Die <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> Eigenschaft bestimmt, wie lange der Benutzer zeigen muss, auf das zugeordnete Steuerelement für die QuickInfo-Zeichenfolge, die angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="31939-105">The <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> property determines how long the user must point at the associated control for the ToolTip string to appear.</span></span> <span data-ttu-id="31939-106">Die <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> Eigenschaft legt fest, die Anzahl der Millisekunden, die es für QuickInfo-Zeichenfolgen angezeigt werden dauert, wenn die Maus von einem zugeordneten QuickInfo-Steuerelement in einen anderen bewegt.</span><span class="sxs-lookup"><span data-stu-id="31939-106">The <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> property sets the number of milliseconds it takes for subsequent ToolTip strings to appear as the mouse moves from one ToolTip-associated control to another.</span></span> <span data-ttu-id="31939-107">Die <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> Eigenschaft bestimmt die Zeitdauer, die die QuickInfo-Zeichenfolge wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="31939-107">The <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> property determines the length of time the ToolTip string is shown.</span></span> <span data-ttu-id="31939-108">Sie können diese Werte festlegen, einzeln oder durch Festlegen des Werts, der die <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> -Eigenschaft, die anderen Eigenschaften werden auf der Basis der zugewiesene Wert Verzögerung der <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="31939-108">You can set these values individually, or by setting the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property; the other delay properties are set based on the value assigned to the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property.</span></span> <span data-ttu-id="31939-109">Z. B., wenn <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> festgelegt ist, auf einen Wert von N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> nastaven NA hodnotu N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> festgelegt ist, auf den Wert der <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> durch fünf geteilt (oder N/5) und <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> nastaven NA hodnotu ein Wert, der fünf Mal der Wert ist die <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> -Eigenschaft (oder 5N).</span><span class="sxs-lookup"><span data-stu-id="31939-109">For example, when <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> is set to a value N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> is set to N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> is set to the value of <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> divided by five (or N/5), and <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> is set to a value that is five times the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property (or 5N).</span></span>  
  
### <a name="to-set-the-delay"></a><span data-ttu-id="31939-110">Um die Verzögerung festzulegen.</span><span class="sxs-lookup"><span data-stu-id="31939-110">To set the delay</span></span>  
  
1. <span data-ttu-id="31939-111">Legen Sie die folgenden Eigenschaften an, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="31939-111">Set the following properties as shown in this example.</span></span>  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="31939-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31939-112">See also</span></span>

- [<span data-ttu-id="31939-113">Übersicht über die ToolTip-Komponente</span><span class="sxs-lookup"><span data-stu-id="31939-113">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="31939-114">Vorgehensweise: Festlegen von QuickInfos für Steuerelemente in Windows Forms zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="31939-114">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [<span data-ttu-id="31939-115">ToolTip-Komponente</span><span class="sxs-lookup"><span data-stu-id="31939-115">ToolTip Component</span></span>](tooltip-component-windows-forms.md)

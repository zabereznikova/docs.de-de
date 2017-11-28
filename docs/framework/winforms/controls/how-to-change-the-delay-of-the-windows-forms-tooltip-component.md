---
title: "Gewusst wie: Ändern der Verzögerung der ToolTip-Komponente in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48bb8c08fa02a54f9bfd3febbe99f683fd68d7f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a><span data-ttu-id="3be65-102">Gewusst wie: Ändern der Verzögerung der ToolTip-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3be65-102">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>
<span data-ttu-id="3be65-103">Es gibt mehrere Verzögerungswerte, die Sie für eine Windows Forms festlegen können <xref:System.Windows.Forms.ToolTip> Komponente.</span><span class="sxs-lookup"><span data-stu-id="3be65-103">There are multiple delay values that you can set for a Windows Forms <xref:System.Windows.Forms.ToolTip> component.</span></span> <span data-ttu-id="3be65-104">Die Maßeinheit für alle diese Eigenschaften ist Millisekunden.</span><span class="sxs-lookup"><span data-stu-id="3be65-104">The unit of measure for all these properties is milliseconds.</span></span> <span data-ttu-id="3be65-105">Die <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> Eigenschaft bestimmt, wie lange der Benutzer zeigen muss, auf das zugeordnete Steuerelement für die QuickInfo-Zeichenfolge, die angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3be65-105">The <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> property determines how long the user must point at the associated control for the ToolTip string to appear.</span></span> <span data-ttu-id="3be65-106">Die <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> Eigenschaft legt die Anzahl der Millisekunden dauert die QuickInfo-Zeichenfolgen angezeigt werden, während die Maus von einem zugeordneten QuickInfo-Steuerelement in einen anderen bewegt.</span><span class="sxs-lookup"><span data-stu-id="3be65-106">The <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> property sets the number of milliseconds it takes for subsequent ToolTip strings to appear as the mouse moves from one ToolTip-associated control to another.</span></span> <span data-ttu-id="3be65-107">Die <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> Eigenschaft bestimmt die Zeitdauer, die die Zeichenfolge für die QuickInfo wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3be65-107">The <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> property determines the length of time the ToolTip string is shown.</span></span> <span data-ttu-id="3be65-108">Sie können diese Werte festlegen, einzeln oder durch Festlegen des Werts, der die <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> Eigenschaft; die anderen Eigenschaften werden auf der Basis der zugewiesene Wert Verzögerung der <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3be65-108">You can set these values individually, or by setting the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property; the other delay properties are set based on the value assigned to the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property.</span></span> <span data-ttu-id="3be65-109">Z. B., wenn <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> festgelegt ist, auf einen Wert von N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> festgelegt ist, bis N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> festgelegt ist, auf den Wert der <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> dividiert durch fünf (oder N/5) und <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> festgelegt ist, auf einen Wert, der fünf Mal den Wert der die <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> -Eigenschaft (oder 5N).</span><span class="sxs-lookup"><span data-stu-id="3be65-109">For example, when <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> is set to a value N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> is set to N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> is set to the value of <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> divided by five (or N/5), and <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> is set to a value that is five times the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property (or 5N).</span></span>  
  
### <a name="to-set-the-delay"></a><span data-ttu-id="3be65-110">Die Verzögerung festlegen</span><span class="sxs-lookup"><span data-stu-id="3be65-110">To set the delay</span></span>  
  
1.  <span data-ttu-id="3be65-111">Die folgenden Eigenschaften fest, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3be65-111">Set the following properties as shown in this example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3be65-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3be65-112">See Also</span></span>  
 [<span data-ttu-id="3be65-113">Übersicht über die ToolTip-Komponente</span><span class="sxs-lookup"><span data-stu-id="3be65-113">ToolTip Component Overview</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [<span data-ttu-id="3be65-114">Gewusst wie: Festlegen von QuickInfos für Steuerelemente auf einem Windows Form zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="3be65-114">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [<span data-ttu-id="3be65-115">ToolTip-Komponente</span><span class="sxs-lookup"><span data-stu-id="3be65-115">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)

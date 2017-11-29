---
title: Energieverwaltung in Windows Forms
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
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e12f39a63a4f81e6deec4512a4e18ad2bda7e5e0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="power-management-in-windows-forms"></a><span data-ttu-id="29e02-102">Energieverwaltung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="29e02-102">Power Management in Windows Forms</span></span>
<span data-ttu-id="29e02-103">Windows Forms-Anwendungen können die Power Management-Funktionen in Windows-Betriebssystems nutzen.</span><span class="sxs-lookup"><span data-stu-id="29e02-103">Your Windows Forms applications can take advantage of the power management features in the Windows operating system.</span></span> <span data-ttu-id="29e02-104">Ihre Anwendungen können den Energiezustand eines Computers überwachen und Maßnahmen ergreifen, tritt eine statusänderung.</span><span class="sxs-lookup"><span data-stu-id="29e02-104">Your applications can monitor the power status of a computer and take action when a status change occurs.</span></span> <span data-ttu-id="29e02-105">Wenn Ihre Anwendung auf einem tragbaren Computer ausgeführt wird, sollten Sie z. B. bestimmte Funktionen in Ihrer Anwendung deaktivieren, wenn der Akku des Computers unter einer bestimmten Ebene liegt.</span><span class="sxs-lookup"><span data-stu-id="29e02-105">For example, if your application is running on a portable computer, you might want to disable certain features in your application when the computer's battery charge falls under a certain level.</span></span>  
  
 <span data-ttu-id="29e02-106">Die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bietet eine <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> Ereignis, das auftritt, sobald sich eine Änderung im Energiestatus, z. B. wenn ein Benutzer hält oder das Betriebssystem, oder wenn der Status des AC oder Akkustatus ändert.</span><span class="sxs-lookup"><span data-stu-id="29e02-106">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provides a <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> event that occurs whenever there is a change in power status, such as when a user suspends or resumes the operating system, or when the AC power status or battery status changes.</span></span> <span data-ttu-id="29e02-107">Die <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> Eigenschaft von der <xref:System.Windows.Forms.SystemInformation> Klasse kann Folgendes sein zur Abfrage für den aktuellen Status, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="29e02-107">The <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property of the <xref:System.Windows.Forms.SystemInformation> class can be used to query for the current status, as shown in the following code example.</span></span>  
  
 [!code-csharp[PowerMode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 <span data-ttu-id="29e02-108">Neben den <xref:System.Windows.Forms.BatteryChargeStatus> Enumerationen, die <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> Eigenschaft enthält auch Enumerationen zur Bestimmung der Akkukapazität (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) und Akku Prozent Rechnung zu stellen (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span><span class="sxs-lookup"><span data-stu-id="29e02-108">Besides the <xref:System.Windows.Forms.BatteryChargeStatus> enumerations, the <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property also contains enumerations for determining battery capacity (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) and battery charge percentage (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span></span>  
  
 <span data-ttu-id="29e02-109">Können Sie die <xref:System.Windows.Forms.Application.SetSuspendState%2A> Methode der <xref:System.Windows.Forms.Application> auf einen Computer in den Ruhezustand oder Standby-Modus.</span><span class="sxs-lookup"><span data-stu-id="29e02-109">You can use the <xref:System.Windows.Forms.Application.SetSuspendState%2A> method of the <xref:System.Windows.Forms.Application> to put a computer into hibernation or suspend mode.</span></span> <span data-ttu-id="29e02-110">Wenn die `force` -Argument festgelegt wird `false`, das Betriebssystem ein Ereignis für alle Anwendungen, die Zustimmung zum Anhalten übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="29e02-110">If the `force` argument is set to `false`, the operating system will broadcast an event to all applications requesting permission to suspend.</span></span> <span data-ttu-id="29e02-111">Wenn die `disableWakeEvent` -Argument festgelegt wird `true`, des Betriebssystems deaktiviert alle Aktivierungsereignisse.</span><span class="sxs-lookup"><span data-stu-id="29e02-111">If the `disableWakeEvent` argument is set to `true`, the operating system disables all wake events.</span></span>  
  
 <span data-ttu-id="29e02-112">Im folgenden Codebeispiel wird veranschaulicht, wie auf einen Computer in den Ruhezustand versetzt wird.</span><span class="sxs-lookup"><span data-stu-id="29e02-112">The following code example demonstrates how to put a computer into hibernation.</span></span>  
  
 [!code-csharp[PowerMode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="29e02-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29e02-113">See Also</span></span>  
 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>  
 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>  
 <xref:System.Windows.Forms.Application.SetSuspendState%2A>  
 <xref:Microsoft.Win32.SystemEvents.SessionSwitch>

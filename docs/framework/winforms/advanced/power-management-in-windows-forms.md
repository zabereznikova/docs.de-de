---
title: Energieverwaltung in Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
ms.openlocfilehash: 77d2096239ec70f98ebfc299f1eda75ad4490be9
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57712421"
---
# <a name="power-management-in-windows-forms"></a><span data-ttu-id="9800c-102">Energieverwaltung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9800c-102">Power Management in Windows Forms</span></span>
<span data-ttu-id="9800c-103">Ihrer Windows Forms-Anwendungen können die Energieverwaltungsfunktionen im Windows-Betriebssystem nutzen.</span><span class="sxs-lookup"><span data-stu-id="9800c-103">Your Windows Forms applications can take advantage of the power management features in the Windows operating system.</span></span> <span data-ttu-id="9800c-104">Ihre Anwendungen können den Status eines Computers überwachen und Maßnahmen ergreifen, wenn eine Änderung des.</span><span class="sxs-lookup"><span data-stu-id="9800c-104">Your applications can monitor the power status of a computer and take action when a status change occurs.</span></span> <span data-ttu-id="9800c-105">Beispielsweise wenn Ihre Anwendung auf einem tragbaren Computer ausgeführt wird, empfiehlt, deaktivieren bestimmte Features in Ihrer Anwendung aus, wenn der Ladezustand des Akkus unter ein bestimmtes Niveau fällt.</span><span class="sxs-lookup"><span data-stu-id="9800c-105">For example, if your application is running on a portable computer, you might want to disable certain features in your application when the computer's battery charge falls under a certain level.</span></span>  
  
 <span data-ttu-id="9800c-106">Die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bietet eine <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> Ereignis tritt auf, wenn eine im Energiestatus Änderung, z. B. wenn ein Benutzer angehalten oder fortgesetzt wird das Betriebssystem oder wenn der Status des AC oder Akkustatus ändert.</span><span class="sxs-lookup"><span data-stu-id="9800c-106">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provides a <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> event that occurs whenever there is a change in power status, such as when a user suspends or resumes the operating system, or when the AC power status or battery status changes.</span></span> <span data-ttu-id="9800c-107">Die <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> Eigenschaft der <xref:System.Windows.Forms.SystemInformation> Klasse kann Folgendes sein verwendet, um die Abfrage für den aktuellen Status, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="9800c-107">The <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property of the <xref:System.Windows.Forms.SystemInformation> class can be used to query for the current status, as shown in the following code example.</span></span>  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 <span data-ttu-id="9800c-108">Neben der <xref:System.Windows.Forms.BatteryChargeStatus> Enumerationen, die <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> Eigenschaft enthält auch die Enumerationen zur Bestimmung der Akkukapazität (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) und Akku rechnen Prozentsatz (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span><span class="sxs-lookup"><span data-stu-id="9800c-108">Besides the <xref:System.Windows.Forms.BatteryChargeStatus> enumerations, the <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property also contains enumerations for determining battery capacity (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) and battery charge percentage (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span></span>  
  
 <span data-ttu-id="9800c-109">Können Sie die <xref:System.Windows.Forms.Application.SetSuspendState%2A> Methode der <xref:System.Windows.Forms.Application> auf einen Computer in den Ruhezustand versetzen oder Standby-Modus.</span><span class="sxs-lookup"><span data-stu-id="9800c-109">You can use the <xref:System.Windows.Forms.Application.SetSuspendState%2A> method of the <xref:System.Windows.Forms.Application> to put a computer into hibernation or suspend mode.</span></span> <span data-ttu-id="9800c-110">Wenn die `force` Argument nastaven NA hodnotu `false`, das Betriebssystem ein Ereignis für alle Anwendungen, die Berechtigung zum Anhalten übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="9800c-110">If the `force` argument is set to `false`, the operating system will broadcast an event to all applications requesting permission to suspend.</span></span> <span data-ttu-id="9800c-111">Wenn die `disableWakeEvent` Argument nastaven NA hodnotu `true`, des Betriebssystems deaktiviert alle Aktivierungsereignisse.</span><span class="sxs-lookup"><span data-stu-id="9800c-111">If the `disableWakeEvent` argument is set to `true`, the operating system disables all wake events.</span></span>  
  
 <span data-ttu-id="9800c-112">Im folgenden Codebeispiel wird veranschaulicht, wie einen Computer in den Ruhezustand versetzt wird.</span><span class="sxs-lookup"><span data-stu-id="9800c-112">The following code example demonstrates how to put a computer into hibernation.</span></span>  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9800c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9800c-113">See also</span></span>
- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>

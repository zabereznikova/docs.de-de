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
ms.openlocfilehash: 172472cf9a2e1bc7bb81448dc8793a4eaeb12da4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546555"
---
# <a name="power-management-in-windows-forms"></a>Energieverwaltung in Windows Forms
Ihrer Windows Forms-Anwendungen können die Energieverwaltungsfunktionen im Windows-Betriebssystem nutzen. Ihre Anwendungen können den Status eines Computers überwachen und Maßnahmen ergreifen, wenn eine Änderung des. Beispielsweise wenn Ihre Anwendung auf einem tragbaren Computer ausgeführt wird, empfiehlt, deaktivieren bestimmte Features in Ihrer Anwendung aus, wenn der Ladezustand des Akkus unter ein bestimmtes Niveau fällt.  
  
 Die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bietet eine <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> Ereignis tritt auf, wenn eine im Energiestatus Änderung, z. B. wenn ein Benutzer angehalten oder fortgesetzt wird das Betriebssystem oder wenn der Status des AC oder Akkustatus ändert. Die <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> Eigenschaft der <xref:System.Windows.Forms.SystemInformation> Klasse kann Folgendes sein verwendet, um die Abfrage für den aktuellen Status, wie im folgenden Codebeispiel gezeigt.  
  
 [!code-csharp[PowerMode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 Neben der <xref:System.Windows.Forms.BatteryChargeStatus> Enumerationen, die <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> Eigenschaft enthält auch die Enumerationen zur Bestimmung der Akkukapazität (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) und Akku rechnen Prozentsatz (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).  
  
 Können Sie die <xref:System.Windows.Forms.Application.SetSuspendState%2A> Methode der <xref:System.Windows.Forms.Application> auf einen Computer in den Ruhezustand versetzen oder Standby-Modus. Wenn die `force` Argument nastaven NA hodnotu `false`, das Betriebssystem ein Ereignis für alle Anwendungen, die Berechtigung zum Anhalten übertragen wird. Wenn die `disableWakeEvent` Argument nastaven NA hodnotu `true`, des Betriebssystems deaktiviert alle Aktivierungsereignisse.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie einen Computer in den Ruhezustand versetzt wird.  
  
 [!code-csharp[PowerMode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>

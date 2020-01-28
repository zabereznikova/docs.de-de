---
title: Energie Verwaltung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
ms.openlocfilehash: 9ac39df43a08f62e50116c61c4bdeda4cd1c8281
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746862"
---
# <a name="power-management-in-windows-forms"></a>Energieverwaltung in Windows Forms
Ihre Windows Forms Anwendungen können die Energie Verwaltungsfunktionen des Windows-Betriebssystems nutzen. Ihre Anwendungen können den Energiestatus eines Computers überwachen und Maßnahmen ergreifen, wenn eine Statusänderung auftritt. Wenn Ihre Anwendung z. b. auf einem tragbaren Computer ausgeführt wird, möchten Sie möglicherweise bestimmte Features in Ihrer Anwendung deaktivieren, wenn die Akku Belastung des Computers unter einer bestimmten Ebene liegt.  
  
 Der .NET Framework bietet ein <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> Ereignis, das auftritt, wenn sich der Energiestatus ändert, z. b. Wenn ein Benutzer das Betriebssystem anhält oder fortsetzt oder wenn sich der Strom Status oder der Akku Status ändert. Die <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>-Eigenschaft der <xref:System.Windows.Forms.SystemInformation>-Klasse kann verwendet werden, um den aktuellen Status abzufragen, wie im folgenden Codebeispiel gezeigt.  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 Neben den <xref:System.Windows.Forms.BatteryChargeStatus> Enumerationen enthält die <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>-Eigenschaft auch Enumerationen zum Ermitteln der Akkukapazität (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) und der Akku Laderate (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).  
  
 Mit der <xref:System.Windows.Forms.Application.SetSuspendState%2A>-Methode des <xref:System.Windows.Forms.Application> können Sie einen Computer in den Ruhezustand oder den Unterbrechungs Modus versetzen. Wenn das `force`-Argument auf `false`festgelegt ist, überträgt das Betriebssystem ein Ereignis an alle Anwendungen, die die Berechtigung zum aussetzen anfordern. Wenn das `disableWakeEvent`-Argument auf `true`festgelegt ist, deaktiviert das Betriebssystem alle Wake-Ereignisse.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie ein Computer in den Ruhezustand versetzt wird.  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>

---
title: "Energieverwaltung in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Batteriezustände"
  - "Energieverbrauchszustand"
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Energieverwaltung in Windows Forms
Ihre Windows Forms\-Anwendungen können die Features zur Energieverwaltung des Windows\-Betriebssystems nutzen.  Anwendungen können den Energiestatus eines Computers überprüfen und Aktionen durchführen, sobald sich der Status ändert.  Wenn die Anwendung beispielsweise auf einem tragbaren Computer ausgeführt wird, möchten Sie möglicherweise bestimmte Features in der Anwendung deaktivieren, wenn der Ladezustand des Akkus unter ein bestimmtes Niveau fällt.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] stellt ein <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>\-Ereignis bereit, das auftritt, sobald sich der Energiezustand ändert, d. h., wenn ein Benutzer das Betriebssystem in den Standbymodus versetzt oder diesen beendet oder wenn sich der Zustand der Netzstrom\- oder Akkuversorgung ändert.  Die <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>\-Eigenschaft der <xref:System.Windows.Forms.SystemInformation>\-Klasse kann verwendet werden, um den aktuellen Zustand abzufragen, wie im folgenden Codebeispiel gezeigt:  
  
 [!code-csharp[PowerMode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 Neben den <xref:System.Windows.Forms.BatteryChargeStatus>\-Enumerationen enthält auch die <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>\-Eigenschaft bestimmte Enumerationen zur Bestimmung der Akkukapazität \(<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>\) und des prozentualen Ladezustands des Akkus \(<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A> und <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>\).  
  
 Mit der <xref:System.Windows.Forms.Application.SetSuspendState%2A>\-Methode der <xref:System.Windows.Forms.Application> können Sie einen Computer in den Ruhezustand oder Standbymodus versetzen.  Wenn das `force`\-Argument auf `false` gesetzt ist, sendet das Betriebssystem ein Ereignis an alle Anwendungen, um die Erlaubnis für den Standbymodus anzufordern.  Wenn das `disableWakeEvent`\-Argument auf `true` gesetzt ist, deaktiviert das Betriebssystem alle Aktivierungsereignisse.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie ein Computer in den Ruhezustand versetzt werden kann.  
  
 [!code-csharp[PowerMode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## Siehe auch  
 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>   
 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>   
 <xref:System.Windows.Forms.Application.SetSuspendState%2A>   
 <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
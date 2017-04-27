---
title: "Entschärfung: Kultur und Verteilervorgänge in WPF-Apps | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 455c1452-8ce0-45ae-a092-21fb8edf1cac
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1aee32c5c50c4ff4309f93bff270e6c3b3c8f7cc
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-culture-and-dispatcher-operations-in-wpf-apps"></a>Entschärfung: Kultur und Verteilervorgänge in WPF-Apps
In Apps, die auf .NET Framework 4.6 und .NET Framework 4.6.1 ausgerichtet sind, gehen Änderungen an den Eigenschaften <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> oder <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> am Ende des Verteilervorgangs verloren, die innerhalb eines <xref:System.Windows.Threading.Dispatcher> erstellt wurden. Auf ähnliche Weise werden Änderungen an <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> oder <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>, die außerhalb eines Verteilervorgangs erfolgen, möglicherweise nicht widergespiegelt, wenn dieser Vorgang ausgeführt wird.  
  
 Der Grund ist eine Änderung in <xref:System.Threading.ExecutionContext>, die dazu führt, dass <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> im Ausführungskontext gespeichert werden. WPF-Verteilungsvorgänge speichern den Ausführungskontext, der dazu verwendet wurde, um den Vorgang zu beginnen und stellen den vorherigen Kontext wieder her, wenn der Vorgang abgeschlossen ist. Da <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> jetzt Teil dieses Kontexts sind, bleiben Änderungen an ihnen innerhalb eines Verteilungsvorgangs außerhalb des Vorgangs nicht erhalten.  
  
## <a name="impact"></a>Auswirkungen  
 Praktisch bedeutet dies, dass Änderungen an den Eigenschaften <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> und <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> möglicherweise nicht zwischen WPF-UI-Rückrufen und anderem Code in einer WPF-Anwendung fließen.  
  
## <a name="mitigation"></a>Problemumgehung  
 Apps, die von dieser Änderung betroffen sind, können sie auf eine von zwei Arten umgehen:  
  
-   Durch Speichern der gewünschten <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> oder <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> in einem Feld und Überprüfen in allen <xref:System.Windows.Threading.Dispatcher>-Vorgangstextkörpern (einschließlich Rückrufhandlern für Benutzeroberflächenereignisse), dass die richtige <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> oder <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> festgelegt ist.  
  
-   Da sich die Änderung an <xref:System.Threading.ExecutionContext> nur auf WPF-Apps mit den Zielplattformen .NET Framework 4.6 oder .NET Framework 4.6.1 auswirkt, kann diese Änderung durch Festlegen von .NET Framework 4.5.2 oder einer Version von .NET Framework, die mit 4.6.2 beginnt, als Zielplattform vermieden werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

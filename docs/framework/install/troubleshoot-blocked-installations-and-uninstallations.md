---
title: "Problembehandlung bei blockierten Installationen und Deinstallationen von .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework, Problembehandlung bei blockierten Installationen"
  - "Blockierte .NET Framework-Installationen, Problembehandlung"
ms.assetid: c3fdfbc1-ed99-4202-a2b0-8c4f1646385d
caps.latest.revision: 57
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 39
---
# Problembehandlung bei blockierten Installationen und Deinstallationen von .NET Framework
Wenn Sie das [Web\- oder Offline](../../../docs/framework/install/guide-for-developers.md)\-Installationsprogramm für das .NET Framework 4.5, 4.5.1, 4.5.2, 4.6 oder 4.6.1 ausführen, kann ein Problem auftreten, das die Installation von .NET Framework verhindert oder blockiert. Die folgende Tabelle enthält Probleme, die zu Blockierungen führen können, und Links zu den Problembehandlungsinformationen.  
  
 4.5.*x* bezieht sich in dieser Tabelle auf .NET Framework 4.5 und dessen Punktversionen 4.5.1, 4.5.2, 4.6 oder 4.6.1.  
  
|Blockierungsmeldung|Weitere Informationen und Informationen zur Problembehebung|  
|-------------------------|-----------------------------------------------------------------|  
|Durch die Deinstallation von Microsoft .NET Framework werden möglicherweise einige Anwendungen nicht mehr ordnungsgemäß arbeiten.|Im Allgemeinen sollten Sie keine der auf dem Computer installierten .NET Framework\-Versionen deinstallieren, da möglicherweise eine von Ihnen verwendete Anwendung von einer bestimmten Version von .NET Framework abhängt. Weitere Informationen finden Sie unter [.NET Framework für Benutzer](../../../docs/framework/get-started/index.md#ForUsers) im Leitfaden *Erste Schritte*.|  
|.NET Framework 4.5*.x*\/4.6*.x* \(*Sprache*\) erfordert .NET Framework 4.5*.x*\/4.6*.x*. Installieren Sie zunächst .NET Framework 4.5.*x*\/4.6*.x* aus dem Download Center, und führen Sie Setup erneut aus.|Sie müssen Sie die englische Version der angegebenen .NET Framework\-Version installieren, bevor Sie ein Language Pack installieren können. Weitere Informationen finden Sie im Abschnitt [So installieren Sie Language Packs](../../../docs/framework/install/guide-for-developers.md#standalone_language_packs) im Installationshandbuch.|  
|.NET Framework 4.5*.x*\/4.6*.x* kann nicht installiert werden. Andere Anwendungen auf dem Computer sind nicht mit diesem Programm kompatibel.<br /><br /> \- oder \-<br /><br /> Andere Anwendungen auf dem Computer sind nicht mit diesem Programm kompatibel.|Die wahrscheinlichste Ursache dieser Meldung ist die Installation einer Vorschau\- oder RC\-Version von .NET Framework 4.5. Deinstallieren Sie die Vorschau\- oder RC\-Version und führen Sie das Setup erneut aus.|  
|.NET Framework 4.5.*x*\/4.6*.x* kann nicht mit diesem Paket deinstalliert werden. Öffnen Sie die **Systemsteuerung**, wählen Sie **Programme und Features**, **Installierte Updates anzeigen**, „Update für Microsoft Windows \(KB2828152\)“ und dann **Deinstallieren** aus, um .NET Framework 4.5*.x*\/4.6*.x* von Ihrem Computer zu deinstallieren.|Das Paket, das Sie installieren, deinstalliert keine Vorschau\- oder RC\-Versionen von .NET Framework.<br /><br /> Deinstallieren Sie die Vorschau\- oder RC\-Version über die Systemsteuerung.|  
|.NET Framework 4.5*.x*\/4.6*.x* kann nicht deinstalliert werden. Andere Anwendungen auf dem Computer sind von diesem Programm abhängig.|Im Allgemeinen sollten Sie keine .NET Framework\-Versionen deinstallieren, da möglicherweise eine von Ihnen verwendete Anwendung von einer bestimmten Version von .NET Framework abhängt. Weitere Informationen finden Sie unter [.NET Framework für Benutzer](../../../docs/framework/get-started/index.md#ForUsers) im Leitfaden *Erste Schritte*.|  
|Das .NET Framework 4.5.*.x*\/4.6*.x*\-Redistributable gilt nicht für dieses Betriebssystem. Laden Sie .NET Framework 4.5.*.x*\/4.6*.x* für Ihr Betriebssystem aus dem Microsoft Download Center herunter.|Sie versuchen möglicherweise, [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], 4.5.2, 4.6 oder 4.6.1 auf einer nicht unterstützten Plattform zu installieren, oder Sie haben das Installationspaket ausgewählt, das nicht alle Komponenten für die unterstützten Betriebssysteme enthält. Führen Sie die Installation erneut mit dem Offlineinstaller aus \([für 4.5.1](http://go.microsoft.com/fwlink/p/?LinkId=309493), [für 4.5.2](http://go.microsoft.com/fwlink/p/?LinkId=397706), [für 4.6](http://go.microsoft.com/fwlink/p/?LinkId=528233) oder [für 4.6.1](http://go.microsoft.com/fwlink/p/?LinkId=671744)\). Weitere Informationen finden Sie unter [Installationsleitfaden](../../../docs/framework/install/guide-for-developers.md) und [Systemanforderungen](../../../docs/framework/get-started/system-requirements.md) für unterstützte Betriebssysteme.|  
|Auf dem Computer wird zurzeit eine Server Core\-Installation des Windows Server 2008\-Betriebssystems ausgeführt. Für .NET Framework 4.5.*x* ist eine neuere Version des Betriebssystems erforderlich. Installieren Sie Windows Server 2008 R2 SP1 oder höher und führen Sie das Setup von .NET Framework 4.5.*x* erneut aus.|[!INCLUDE[net_v451](../../../includes/net-v451-md.md)] und 4.5.2 werden unter Windows Server 2008 R2 SP1 oder höher in der Server Core\-Rolle unterstützt. Siehe [Systemanforderungen](../../../docs/framework/get-started/system-requirements.md).|  
|Sie besitzen keine ausreichenden Berechtigungen, um diesen Vorgang für alle Benutzer dieses Computers durchzuführen. Melden Sie sich als Administrator an, und führen Sie **Setup** erneut aus.|Sie müssen als Administrator auf dem Computer angemeldet sein, um .NET Framework zu installieren.|  
|Setup kann nicht fortgesetzt werden, da der Computer für eine vorherige Installation neu gestartet werden muss. Starten Sie den Computer neu, und führen Sie Setup erneut aus.|Möglicherweise ist ein Neustart ist erforderlich, um die Installation abzuschließen. Folgen Sie den Anweisungen, um den Computer neu zu starten und Setup erneut auszuführen.|  
|.NET Framework 4.5.*.x*\/4.6*.x* \(ENU\) oder ein neueres Update ist bereits auf diesem Computer installiert.|Keine Aktion notwendig.|  
|Setup für .NET Framework kann im Programmkompatibilitätsmodus nicht ausgeführt werden.|Siehe Abschnitt [Programmkompatibilitätsprobleme](#compat) weiter unten in diesem Artikel.|  
|.NET Framework 4.5*.x*\/4.6*.x* wurde nicht installiert, weil der Komponentenspeicher beschädigt ist.|Weitere Informationen finden Sie im Abschnitt [Beheben von Windows Update\-Fehlern mit dem DISM\- oder Systemupdate\-Vorbereitungstool](https://support.microsoft.com/en-us/kb/947821).|  
|Setup kann nicht ausgeführt werden, da der Windows Installer\-Dienst auf diesem Computer nicht verfügbar ist.|Lesen Sie den Artikel [Fehler vom Windows\-Installationsdienst beim Installieren oder Aktualisieren des Programms](http://go.microsoft.com/fwlink/p/?LinkId=248684) auf der Microsoft Support\-Website.|  
|Setup kann möglicherweise nicht ordnungsgemäß ausgeführt werden, da der Windows Update\-Dienst auf diesem Computer nicht verfügbar ist.|Der Computer ist möglicherweise so konfiguriert Windows Server Update Services \(WSUS\) statt Microsoft Windows Update zu verwenden. Weitere Informationen finden Sie im Abschnitt zum Fehlercode „0x800F0906“ in [Fehlercodes beim Installieren von .NET Framework 3.5 in Windows 8 oder Windows Server 2012](http://support.microsoft.com/kb/2734782).<br /><br /> Lesen Sie auch den Artikel [Beziehen der aktuellen Version des Windows Update Agent zum Verwalten von Updates auf einem Computer](http://go.microsoft.com/fwlink/p/?LinkId=248437) auf der Microsoft Support\-Website.|  
|Setup kann möglicherweise nicht ordnungsgemäß ausgeführt werden, da der intelligente Hintergrundübertragungsdienst \(Background Intelligent Transfer Service, BITS\) auf diesem Computer nicht verfügbar ist.|Weitere Informationen finden Sie unter [Ein Update zum Vermeiden eines Absturzes des intelligenten Hintergrundübertragungsdiensts \(BITS\) auf einem Computer mit Windows Vista](http://go.microsoft.com/fwlink/p/?LinkId=248680) auf der Microsoft Support\-Website.|  
|.NET Framework 4.5*.x*\/4.6 ist bereits ein Teil dieses Betriebssystems. Sie müssen die Redistributable\-Version von .NET Framework 4.5.*.x*\/4.6 nicht installieren.|Keine Aktion. Informationen zu unterstützten Betriebssystemen finden Sie unter [Systemanforderungen](../../../docs/framework/get-started/system-requirements.md).|  
|.NET Framework 4.5.*.x*\/4.6*.x* wird unter diesem Betriebssystem nicht unterstützt.|Informationen zu unterstützten Betriebssystemen finden Sie unter [Systemanforderungen](../../../docs/framework/get-started/system-requirements.md).<br /><br /> Bei nicht erfolgreichen Installationen von .NET Framework unter Windows 7 weist diese Meldung typischerweise darauf hin, dass Windows 7 SP1 nicht installiert ist. Auf Windows 7\-Systemen erfordert .NET Framework Windows 7 SP1. Wenn Sie mit Windows 7 arbeiten und Service Pack 1 noch nicht installiert haben, müssen Sie dies nachholen, bevor Sie .NET Framework installieren.|  
|Auf Ihrem Computer wird derzeit folgendes Betriebssystem ausgeführt: Server Core\-Installation des Betriebssystems Windows Server 2008. .NET Framework 4.5.*x* erfordert eine Vollversion des Betriebssystems oder Server Core 2008 R2 SP1. Installieren Sie die Vollversion von Windows Server 2008 SP2 oder Windows Server 2008 R2 SP1 oder Server Core 2008 R2 SP1, und führen Sie das Setup für .NET Framework 4.5.*x* erneut aus.|.NET Framework wird in der Server Core\-Rolle von Windows Server 2008 R2 mit SP1 oder höher unterstützt. Siehe [Systemanforderungen](../../../docs/framework/get-started/system-requirements.md).|  
|.NET Framework 4.5.*x* ist bereits Teil des Betriebssystems, ist jedoch derzeit deaktiviert \(nur [!INCLUDE[winserver8](../../../includes/winserver8-md.md)]\).|Weitere Informationen finden Sie auf der Windows\-Website unter [Aktivieren oder Deaktivieren von Windows\-Features](http://go.microsoft.com/fwlink/p/?LinkId=248438).|  
|Dieses Setupprogramm erfordert einen x86\-Computer. Es kann nicht auf einem x64\- oder IA64\-Computer installiert werden.|Siehe [Systemanforderungen](../../../docs/framework/get-started/system-requirements.md) in der MSDN Library.|  
|Dieses Setupprogramm erfordert einen x64\- oder x86\-Computer. Es kann nicht auf einem IA64\-Computer installiert werden.|Siehe [Systemanforderungen](../../../docs/framework/get-started/system-requirements.md) in der MSDN Library.|  
  
<a name="compat"></a>   
### Programmkompatibilitätsprobleme  
 Die Installation von .NET Framework 4.5 oder einer der Punktversionen verursacht einen Fehler mit Fehlercode 1603 oder blockiert, wenn es im Windows\-Programmkompatibilitätsmodus ausgeführt wird. Der **Programmkompatibilitäts\-Assistent** zeigt an, dass .NET Framework möglicherweise nicht ordnungsgemäß installiert wurde, und Sie werden aufgefordert, das Programm mit der empfohlenen Einstellung \(Programmkompatibilitätsmodus\) neu zu installieren. Es ist auch möglich, dass der Programmkompatibilitätsmodus bei zuvor fehlerhaften oder abgebrochenen Versuchen, Setup für .NET Framework auszuführen, durch den Programmkompatibilitäts\-Assistenten festgelegt wurde.  
  
 Das Installationsprogramm für .NET Framework kann im Programmkompatibilitätsmodus nicht ausgeführt werden. Um dieses Blockierungsproblem zu beheben, müssen Sie sicherstellen, dass der Kompatibilitätsmodus im Registrierungs\-Editor nicht für das gesamte System aktiviert ist:  
  
1.  Klicken Sie auf **Start**, und wählen Sie dann **Ausführen** aus.  
  
2.  Geben Sie im Dialogfeld **Ausführen** die Zeichenfolge `regedit` ein, und klicken Sie dann auf **OK**.  
  
3.  Navigieren Sie im Registrierungs\-Editor zu den folgenden Unterschlüsseln:  
  
    -   HKEY\_CURRENT\_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Compatibility Assistant\\Persisted  
  
    -   HKEY\_CURRENT\_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers  
  
4.  Suchen Sie in der Spalte „Name“ nach Downloadnamen für [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], 4.5.1, 4.5.2, 4.6 oder 4.6.1 mit Bezug auf die zu installierende Version, und entfernen Sie diese Einträge. Downloadnamen finden Sie im Artikel [Installationshandbuch](../../../docs/framework/install/guide-for-developers.md).  
  
5.  Führen Sie den .NET Framework\-Installer für die Version 4.5, 4.5.1, 4.5.2, 4.6 oder 4.6.1 erneut aus.  
  
## Siehe auch  
 [Installationshandbuch](../../../docs/framework/install/guide-for-developers.md)
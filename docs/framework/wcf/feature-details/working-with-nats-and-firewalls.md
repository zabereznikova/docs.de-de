---
title: Arbeiten mit NATs und Firewalls
ms.date: 03/30/2017
helpviewer_keywords:
- firewalls [WCF]
- NATs [WCF]
ms.assetid: 74db0632-1bf0-428b-89c8-bd53b64332e7
ms.openlocfilehash: bab29d738c7562753a826b47c03867eeebac4372
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558978"
---
# <a name="working-with-nats-and-firewalls"></a>Arbeiten mit NATs und Firewalls
Der Austausch von Daten zwischen einem Client und einem Server erfolgt häufig nicht über eine direkte und offene Verbindung. Die Datenpakete werden gefiltert, weitergeleitet, analysiert und transformiert – sowohl vom Absender und vom Empfänger als auch von den Zwischenstationen im Netzwerk. Netzwerkadressübersetzungen (NAT) und Firewalls sind gängige Beispiele für zwischengeschaltete Anwendungen, die an der Kommunikation im Netzwerk beteiligt sein können.  
  
 Windows Communication Foundation (WCF)-Transporte und Nachrichtenaustausch Muster (Nachrichtenaustausch Muster) reagieren auf das vorhanden sein von NATs und Firewalls anders. In diesem Thema wird beschrieben, wie die Netzwerkadressübersetzung und Firewalls in gängigen Netzwerktopologien funktionieren. Es werden Empfehlungen für bestimmte Kombinationen von WCF-Transporten und-Nachrichtenaustausch vorgegeben, damit Ihre Anwendungen für NATs und Firewalls im Netzwerk stabiler werden.  
  
## <a name="how-nats-affect-communication"></a>Einfluss von Netzwerkadressübersetzungen auf die Kommunikation  
 Netzwerkadressübersetzungen wurden konzipiert, um eine externe IP-Adresse mit mehreren Computern nutzen zu können. Bei der Netzwerkadressübersetzung mit Anschlussneuzuordnung werden eine interne IP-Adresse und ein interner Anschluss für die Verbindung mit einer externen IP-Adresse einer neuen Anschlussnummer zugeordnet. Die neue Anschlussnummer ermöglicht es der Netzwerkadressübersetzung, den eingehenden Datenverkehr mit der ursprünglichen Kommunikation in Beziehung zu setzen. Viele Privatanwender verfügen über eine IP-Adresse, die nur privat geroutet werden kann, und verwenden die Netzwerkadressübersetzung für das globale Routing von Datenpaketen.  
  
 Die Netzwerkadressübersetzung fungiert nicht als Sicherheitsgrenze. Durch NAT-Konfigurationen wird jedoch in aller Regel verhindert, dass die internen Computer direkt adressiert werden. Dadurch werden die internen Computer einerseits teilweise vor unerwünschten Verbindungen geschützt und andererseits wird das Schreiben von Serveranwendungen erschwert, die Daten asynchron an den Client zurücksenden müssen. Durch die Netzwerkadressübersetzung werden die Adressen in Datenpaketen geändert, sodass die Verbindungen vom NAT-Computer auszugehen scheinen. Dadurch wird verhindert, dass der Server eine Verbindung zurück zum Client initiiert. Wenn der Server versucht, die erkannte Clientadresse zu verwenden, tritt ein Fehler auf, da die Adresse des Clients nicht öffentlich geroutet werden kann. Wenn der Server die NAT-Adresse verwendet, kann ebenfalls keine Verbindung hergestellt werden, da dieser Computer von keiner Anwendung überwacht wird.  
  
 Einige NAT-Verfahren unterstützen Weiterleitungsregeln, um externen Computern das Herstellen einer Verbindung mit einem bestimmten internen Computer zu ermöglichen. Die Einrichtung von Weiterleitungsregeln ist abhängig von der verwendeten Netzwerkadressübersetzung, und i. d. R. wird davon abgeraten, die NAT-Konfiguration zu ändern. Viele Endbenutzer können oder möchten ihre NAT-Konfiguration nicht für eine bestimmte Anwendung ändern.  
  
## <a name="how-firewalls-affect-communication"></a>Einfluss von Firewalls auf die Kommunikation  
 Bei einer *Firewall* handelt es sich um ein Software-oder Hardware Gerät, das Regeln für den eingehenden Datenverkehr anwendet. Sie können Firewalls konfigurieren, um eingehenden und/oder ausgehenden Datenverkehr zu untersuchen. Firewalls fungieren als Sicherheitsmechanismus für Netzwerke am Rande des Netzwerks oder am Endpunkthost. Geschäftliche Benutzer schützen ihre Server schon länger durch eine Firewall, um böswillige Angriffe zu verhindern. Seit der Einführung der Personal Firewall in Windows XP SP2 hat sich die Anzahl der Heimbenutzer hinter einer Firewall ebenfalls erheblich erhöht. Es ist daher sehr wahrscheinlich, dass die Datenpakete mindestens an einem Verbindungsende von einer Firewall untersucht werden.  
  
 Firewalls unterscheiden sich sehr stark hinsichtlich ihrer Komplexität und der Fähigkeit zum Untersuchen von Datenpaketen. Einfache Firewalls verwenden Regeln auf Basis von Quell- und Zieladressen sowie von Anschlüssen in Datenpaketen. Leistungsfähigere Firewalls können auch den Inhalt von Datenpaketen untersuchen, um Entscheidungen zu treffen. Diese Firewalls weisen eine Vielzahl von Konfigurationen auf und werden oft für spezielle Anwendungen genutzt.  
  
 Private Firewalls sind häufig so konfiguriert, dass eingehende Verbindungen unterbunden werden, es sei denn, es wurde zuvor eine ausgehende Verbindung zum entsprechenden Computer hergestellt. Geschäftliche Firewalls sind häufig so konfiguriert, dass zunächst einmal eingehende Verbindungen auf allen Anschlüssen unterbunden und anschließend Ausnahmen festgelegt werden. Beispielsweise kann eine Firewall alle Verbindungen mit Ausnahme von Verbindungen über den Anschluss 80 und den Anschluss 443 blockieren, um HTTP- und HTTPS-Dienste zu ermöglichen. Sowohl für private als auch für geschäftliche Benutzer gibt es verwaltete Firewalls, die es einem vertrauenswürdigen Benutzer oder einem vertrauenswürdigen Prozess ermöglichen, die Konfiguration der Firewall anzupassen. Verwaltete Firewalls sind häufiger in privaten Umgebungen zu finden, da die Netzwerkverwendung dort i. d. R. keinen spezifischen Richtlinien unterliegt.  
  
## <a name="using-teredo"></a>Verwenden von Teredo  

 Teredo ist eine IPv6-Technologie zur direkten Adressierung von Computern hinter einem Netzwerkadressübersetzungsmechanismus. Das Teredo-Protokoll verwendet einen Server, der öffentlich und global geroutet werden kann, um potenzielle Verbindungen anzukündigen. Der Teredo-Server übernimmt die Rolle eine Vermittlers zwischen dem Client und dem Server der Anwendung und ermöglicht so den Austausch von Verbindungsinformationen. Die Computer fordern dann eine temporäre Teredo-Adresse an, und die Pakete werden durch das vorhandene Netzwerk getunnelt. Die Teredo-Unterstützung in WCF erfordert die Aktivierung der IPv6-und Teredo-Unterstützung im Betriebssystem. Teredo wird von Windows XP und neueren Betriebssystemen unterstützt. Windows Vista und spätere Betriebssysteme unterstützen IPv6 standardmäßig und erfordern nur, dass der Benutzer Teredo aktiviert. Windows XP SP2 und Windows Server 2003 erfordern, dass der Benutzer sowohl IPv6 als auch Teredo aktiviert. Weitere Informationen finden Sie in der [Übersicht über Teredo](/previous-versions/windows/it-pro/windows-xp/bb457011(v=technet.10)).  
  
## <a name="choosing-a-transport-and-message-exchange-pattern"></a>Auswählen eines Transports und eines Nachrichtenaustauschmusters  
 Das Verfahren zum Auswählen eines Transports und eines Nachrichtenaustauschmusters besteht aus drei Schritten:  
  
1. Analysieren Sie zunächst die Adressierbarkeit der Endpunktcomputer. Unternehmensserver verfügen i. d. R. über eine direkte Adressierbarkeit, während die Adressierbarkeit bei Endbenutzern häufig durch die Netzwerkadressübersetzung verhindert wird. Wenn beide Endpunkte hinter einem NAT-Mechanismus liegen, z. B. in einem Peer-to-Peer-Szenario zwischen Endbenutzern, ist möglicherweise eine Technologie wie Teredo erforderlich, um die Adressierbarkeit sicherzustellen.  
  
2. Analysieren Sie die Protokoll- und Anschlusseinschränkungen der Endpunktcomputer. Unternehmensserver werden i. d. R. durch leistungsstarke Firewalls geschützt, die viele Anschlüsse blockieren. Häufig werden jedoch der Anschluss 80 für HTTP- und der Anschluss 443 für HTTPS-Verbindungen geöffnet. Endbenutzer arbeiten normalerweise nicht mit Anschlusseinschränkungen. Sie verwenden jedoch häufig Firewalls, die nur eingehenden Datenverkehr zulassen. Einige Firewalls ermöglichen eine Verwaltung durch Anwendungen auf dem Endpunkt, um ausgewählte Verbindungen zu öffnen.  
  
3. Berechnen Sie die Transporte und Nachrichtenaustauschmuster, die von der Adressierbarkeit und den Anschlusseinschränkungen des Netzwerks ermöglicht werden.  
  
 In einer Standardtopologie für Client-Server-Anwendungen verfügen Clients hinter einer Netzwerkadressübersetzung ohne Teredo über eine Firewall nur für ausgehende Verbindungen, und der direkt adressierbare Server wird durch eine leistungsstarke Firewall geschützt. In diesem Szenario funktionieren der TCP-Transport mit einem Duplex-Nachrichtenaustauschmuster und ein HTTP-Transport mit einem Anforderung-Antwort-Nachrichtenaustauschmuster ordnungsgemäß. In einer gängigen Peer-to-Peer-Topologie befinden sich beide Endpunkte hinter einem NAT-Mechanismus sowie hinter einer Firewall. In diesem Szenario sowie in Szenarien mit einer unbekannten Netzwerktopologie sollten Sie folgende Empfehlungen beachten:  
  
- Verwenden Sie keine dualen Transporte. Duale Transporte öffnen mehr Verbindungen. Dadurch sinkt die Chance, erfolgreich eine Verbindung herzustellen.  
  
- Unterstützen Sie die Einrichtung von Rückkanälen über die ursprüngliche Verbindung. Durch Rückkanäle (wie bei Duplex-TCP) werden weniger Verbindungen geöffnet, und die Wahrscheinlichkeit steigt, dass eine Verbindung hergestellt werden kann.  
  
- Verwenden Sie einen erreichbaren Dienst zum Registrieren von Endpunkten oder zum Weiterleiten von Datenverkehr. Durch einen global erreichbaren Verbindungsdienst wie einem Teredo-Server wird die Wahrscheinlichkeit deutlich erhöht, eine Verbindung herzustellen, wenn die Netzwerktopologie eingeschränkt oder unbekannt ist.  
  
 In den folgenden Tabellen werden die unidirektionalen, Anforderung-Antwort-und Duplex-Nachrichten Nachrichten sowie die standardmäßigen TCP, TCP mit Teredo und die HTTP-Transport Standard und Dual in WCF untersucht.  
  
|Adressierbarkeit|Server direkt|Server direkt mit NAT-Durchlauf|Server-NAT|Server-NAT mit NAT-Durchlauf|  
|--------------------|-------------------|--------------------------------------|----------------|-----------------------------------|  
|Client direkt|Alle Transporte und MEP|Alle Transporte und MEP|Wird nicht unterstützt.|Wird nicht unterstützt.|  
|Client direkt mit NAT-Durchlauf|Alle Transporte und MEP|Alle Transporte und MEP|Wird nicht unterstützt.|TCP mit Teredo und alle MEPs. Windows Vista verfügt über eine Computer weite Konfigurationsoption zur Unterstützung von http mit Teredo.|  
|Client-NAT|Alle nicht dualen Transporte und MEP. Duplex-MEP erfordert TCP-Transport.|Alle nicht dualen Transporte und MEP. Duplex-MEP erfordert TCP-Transport.|Wird nicht unterstützt.|Wird nicht unterstützt.|  
|Client-NAT mit NAT-Durchlauf|Alle nicht dualen Transporte und MEP. Duplex-MEP erfordert TCP-Transport.|Alle außer duale HTTP-Verbindungen sowie MEP. Duplex-MEP erfordert TCP-Transport. Duale TCP-Transporte erfordern Teredo. Windows Vista verfügt über eine Computer weite Konfigurationsoption zur Unterstützung von http mit Teredo.|Wird nicht unterstützt.|TCP mit Teredo und alle MEPs. Windows Vista verfügt über eine Computer weite Konfigurationsoption zur Unterstützung von http mit Teredo.|  
  
|Firewalleinschränkungen|Server offen|Server mit verwalteter Firewall|Server mit Firewall nur für HTTP-Verbindungen|Server mit Firewall nur für ausgehende Verbindungen|  
|---------------------------|-----------------|----------------------------------|-------------------------------------|-----------------------------------------|  
|Client offen|Alle Transporte und MEP|Alle Transporte und MEP|Alle HTTP-Transporte und MEP|Wird nicht unterstützt.|  
|Client mit verwalteter Firewall|Alle nicht dualen Transporte und MEP. Duplex-MEP erfordert TCP-Transport.|Alle nicht dualen Transporte und MEP. Duplex-MEP erfordert TCP-Transport.|Alle HTTP-Transporte und MEP|Wird nicht unterstützt.|  
|Client mit Firewall nur für HTTP-Verbindungen|Alle HTTP-Transporte und MEP|Alle HTTP-Transporte und MEP|Alle HTTP-Transporte und MEP|Wird nicht unterstützt.|  
|Client mit Firewall nur für ausgehende Verbindungen|Alle nicht dualen Transporte und MEP. Duplex-MEP erfordert TCP-Transport.|Alle nicht dualen Transporte und MEP. Duplex-MEP erfordert TCP-Transport.|Alle HTTP-Transporte sowie alle Nicht-Duplex-MEPs|Wird nicht unterstützt.|

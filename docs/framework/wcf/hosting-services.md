---
title: Hosting-Dienste
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- hosting services [WCF]
ms.assetid: 192be927-6be2-4fda-98f0-e513c4881acc
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b23dac1db5252d3ce2bd60e4f8525dd89d9127b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="hosting-services"></a>Hosting-Dienste
Zur Aktivierung muss der Dienst in einer Laufzeitumgebung gehostet werden, die ihn erstellt und seinen Kontext sowie seine Lebensdauer steuert. [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] -Dienste können in jedem Windows-Prozess ausgeführt werden, der verwalteten Code unterstützt.  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] stellt ein einheitliches Programmiermodell zum Erstellen von dienstorientierten Anwendungen bereit. Dieses Programmiermodell bleibt konsistent und ist von der Laufzeitumgebung unabhängig, in der der Dienst bereitgestellt wird. In der Praxis bedeutet das, dass der Code für Dienste relativ unabhängig von der Hostingoption ist.  
  
 Die Hostingoptionen reichen von einfachen Konsolenanwendungen bis zu Serverumgebungen, z.&#160;B. ein Windows-Dienst, der in einem Arbeitsprozess unter Internetinformationsdiensten (IIS) oder Windows Activation Service (WAS) ausgeführt wird. Entwickler wählen die Hostumgebung aus, die die Bereitstellungsanforderungen des Diensts erfüllt. Diese Anforderungen können von der Plattform, auf der die Anwendung bereitgestellt wird, dem Transportprotokoll, mit dem Nachrichten gesendet und empfangen werden müssen, dem Typ der Prozesswiederverwendung oder anderen Prozessverwaltungsfunktionen, die zur Sicherstellung adäquater Verfügbarkeit erforderlich sind, anderen Verwaltungsanforderungen oder Anforderungen bezüglich der Zuverlässigkeit abhängig sein. Im nächsten Abschnitt erhalten Sie Informationen und Hinweise zu Hostingoptionen.  
  
## <a name="hosting-options"></a>Hostingoptionen  
  
#### <a name="self-hosting-in-a-managed-application"></a>Selbsthosting in einer verwalteten Anwendung  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienste können in jeder verwalteten Anwendung gehostet werden. Dies ist die flexibelste Option, da hier die wenigste Infrastruktur bereitzustellen ist. Sie betten den Code für den Dienst in den verwalteten Anwendungscode ein und erstellen und öffnen dann eine Instanz von <xref:System.ServiceModel.ServiceHost> , um den Dienst zur Verfügung zu stellen. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Wie: Hosten eines WCF-Diensts in einer verwalteten Anwendung](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).  
  
 Diese Option ermöglicht zwei gängige Szenarien: [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienste, die in einer Konsolenanwendung ausgeführt werden, und Rich&amp;#160;Client-Anwendungen, wie die auf [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] oder Windows&amp;#160;Forms (WinForms) basierenden Anwendungen. Einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienst in einer Konsolenanwendung zu hosten, ist in der Regel während der Entwicklungsphase der Anwendung nützlich. Die Anwendung lässt sich dann einfach debuggen. Ablaufverfolgungsinformationen über die Anwendung lassen sich leichter ermitteln, um herauszufinden, was intern in der Anwendung vor sich geht. Zudem lässt sich die Anwendung dann einfacher an andere Speicherorte kopieren. Diese Hostingoption erleichtert es Rich&amp;#160;Client-Anwendungen, wie [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] - und WinForms-Anwendungen, mit der Außenwelt zu kommunizieren. Ein Beispiel dafür ist ein Peer-to-Peer-Kollaborationsclient, der [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] als Benutzeroberfläche nutzt und darüber hinaus als Host für einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienst fungiert, der es anderen Clients ermöglicht, eine Verbindung mit ihm herzustellen und Daten auszutauschen.  
  
#### <a name="managed-windows-services"></a>Verwaltete Windows-Dienste  
 Diese Hostingoption besteht in der Registrierung der Anwendungsdomäne (AppDomain), die einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienst als verwalteten Windows-Dienst (früher NT-Dienst genannt) hostet, sodass die Prozesslebensdauer des Diensts vom Dienststeuerungs-Manager für Windows gesteuert wird. Wie bei der Selbsthosting-Option muss auch bei diesem Typ von Hostumgebung ein Teil des Hostingcodes Bestandteil des Anwendungscodes sein. Der Dienst wird sowohl als Windows-Dienst als auch als [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienst implementiert, indem er von der <xref:System.ServiceProcess.ServiceBase> -Klasse und von einer [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienstvertragsschnittstelle abgeleitet wird. Die <xref:System.ServiceModel.ServiceHost> -Instanz wird erstellt, mit einer überschriebenen <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> -Methode geöffnet und mit einer überschriebenen <xref:System.ServiceProcess.ServiceBase.OnStop> -Methode geschlossen. Außerdem muss eine Installerklasse implementiert werden, die von <xref:System.Configuration.Install.Installer> abgeleitet ist, damit das Programm mit dem Tool Installutil.exe als Windows-Dienst installiert werden kann. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Wie: Hosten eines WCF-Diensts in einem verwalteten Windows-Dienst](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md). Das Szenario, das durch die Hostingoption des verwalteten Windows-Diensts ermöglicht wird, besteht in einem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienst mit langer Laufzeit, der außerhalb der Internetinformationsdienste (IIS) in einer sicheren, nicht nachrichtenaktivierten Umgebung gehostet wird. Die Lebensdauer des Diensts wird stattdessen vom Betriebssystem gesteuert. Diese Hostingoption ist in allen Windows-Versionen verfügbar.  
  
#### <a name="internet-information-services-iis"></a>IIS (Internet Information Services)  
 Die IIS-Hostingoption ist in [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] integriert und nutzt die Features dieser Technologie, beispielsweise die Prozesswiederverwendung, das Herunterfahren der Anwendung und ihrer Dienste bei Leerlauf, die Prozessüberwachung und die nachrichtenbasierte Aktivierung. Unter den Betriebssystemen [!INCLUDE[wxp](../../../includes/wxp-md.md)] und [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] ist dies die bevorzugte Lösung für das Hosten von Webdienstanwendungen, die stets verfügbar und weitgehend skalierbar sein müssen. IIS bietet zudem die integrierte Verwaltbarkeit, die Kunden von einem Serverprodukt für Unternehmen erwarten. Diese Hostingoption erfordert, dass IIS korrekt konfiguriert wurde, jedoch muss keinerlei Hostcode für die Anwendung geschrieben werden. [!INCLUDE[crabout](../../../includes/crabout-md.md)] zum Konfigurieren von IIS-Hosting für einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienst finden Sie unter [How to: Host a WCF Service in IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
 Beachten Sie, dass von IIS gehostete Dienste nur den HTTP-Transport verwenden können. Mit der Implementierung in IIS&amp;#160;5.1 wurden einige Einschränkungen in [!INCLUDE[wxp](../../../includes/wxp-md.md)]eingeführt. Durch die nachrichtenbasierte Aktivierung, die von IIS 5.1 unter [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] für einen [!INCLUDE[wxp](../../../includes/wxp-md.md)] -Dienst bereitgestellt wird, werden alle anderen selbst gehosteten [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienste auf demselben Computer daran gehindert, Port 80 für die Kommunikation zu verwenden. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienste können im gleichen Arbeitsprozess unter AppDomain/Application Pool/Worker Process wie andere Anwendungen ausgeführt werden, wenn sie von [!INCLUDE[iis601](../../../includes/iis601-md.md)] unter [!INCLUDE[ws2003](../../../includes/ws2003-md.md)]gehostet werden. Weil jedoch sowohl [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] als auch [!INCLUDE[iis601](../../../includes/iis601-md.md)] den HTTP-Stack (HTTP.sys) des Kernelmodus verwenden, kann [!INCLUDE[iis601](../../../includes/iis601-md.md)] im Gegensatz zu IIS&amp;#160;5.1 den Anschluss&amp;#160;80 mit anderen selbstgehosteten [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Diensten, die auf demselben Computer ausgeführt werden, gemeinsam nutzen.  
  
#### <a name="windows-process-activation-service-was"></a>Windows Process Activation Service (WAS)  
 Windows Process Activation Service (WAS) ist der neue Prozessaktivierungsmechanismus für [!INCLUDE[lserver](../../../includes/lserver-md.md)] , der auch unter [!INCLUDE[wv](../../../includes/wv-md.md)]verfügbar ist. In WAS wurden das bekannte [!INCLUDE[iis601](../../../includes/iis601-md.md)] -Prozessmodell (Anwendungspools und nachrichtenbasierte Prozessaktivierung) und Hostingfunktionen (z. B. schneller Ausfallschutz, Systemüberwachung und Wiederverwendung) beibehalten, jedoch wurde die Abhängigkeit von HTTP aus der Aktivierungsarchitektur getilgt. [!INCLUDE[iisver](../../../includes/iisver-md.md)] nutzt WAS zur nachrichtenbasierten Aktivierung über HTTP. Zusätzliche [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Komponenten sind in WAS integrierbar, um die nachrichtenbasierte Aktivierung mit anderen von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] unterstützten Protokollen zu ermöglichen, wie TCP, MSMQ und Named Pipes. Dies ermöglicht es Anwendungen, die mit Kommunikationsprotokollen arbeiten, die IIS-Features zu nutzen, die nur für HTTP-basierte Anwendungen verfügbar waren, beispielsweise die Prozesswiederverwendung, den schnellen Fehlerschutz und das gemeinsame Konfigurationssystem.  
  
 Diese Hostingoption erfordert, dass WAS korrekt konfiguriert wurde, jedoch muss keinerlei Hostcode für die Anwendung geschrieben werden. [!INCLUDE[crabout](../../../includes/crabout-md.md)] zum Konfigurieren von WAS-Hosting finden Sie unter [How to: Host a WCF Service in WAS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).  
  
## <a name="choosing-a-hosting-environment"></a>Auswählen einer Hostumgebung  
 In der folgenden Tabelle werden einige wichtige Vorteile und Szenarien im Zusammenhang mit den verschiedenen Hostingoptionen zusammengefasst.  
  
|Hostumgebung|Häufige Szenarien|Hauptvorteile und Einschränkungen|  
|-------------------------|----------------------|----------------------------------|  
|Verwaltete Anwendung ("Selbsthosting")|-Konsolenanwendungen während der Entwicklung verwendet.<br />-Rich WinForm- und [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] Clientanwendungen, die auf Dienste zugreifen.|-Flexibel.<br />-Leicht bereitzustellen.<br />-Keine unternehmenslösung für Dienste.|  
|Windows-Dienste (früher als NT-Dienste bezeichnet)|– Ein langer [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] außerhalb von IIS gehosteten Dienst.|-Prozesslebensdauer des Dienst, der vom Betriebssystem, nicht nachrichtenaktivierten gesteuert wird.<br />-Die von allen Versionen von Windows unterstützt werden.<br />-Sicheren Umgebung.|  
|IIS 5.1, [!INCLUDE[iis601](../../../includes/iis601-md.md)]|-Ausführen einer [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Dienst Seite-an-Seite mit [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Inhalt im Internet unter Verwendung des HTTP-Protokolls.|-Prozesswiederverwendung.<br />-Im Leerlauf Herunterfahren.<br />-Prozessüberwachung.<br />-Die Nachrichtenbasierte Aktivierung.<br />-Nur HTTP.|  
|Windows Process Activation Service (WAS)|-Ausführen einer [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienst ohne Installation von IIS im Internet unter Verwendung verschiedener Transportprotokolle.|-IIS ist nicht erforderlich.<br />-Prozesswiederverwendung.<br />-Im Leerlauf Herunterfahren.<br />-Prozessüberwachung.<br />-Die Nachrichtenbasierte Aktivierung.<br />-Funktioniert mit HTTP, TCP, named Pipes und MSMQ.|  
|IIS 7.0|-Ausführen einer [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Dienst mit [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Inhalt.<br />-Ausführen einer [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Diensts im Internet unter Verwendung verschiedener Transportprotokolle.|-Vorteile wurde.<br />-Integration in [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] und IIS-Inhalt.|  
  
 Die Wahl der Hostumgebung hängt von der Windows-Version ab, unter der der Dienst bereitgestellt wird, den für die Übermittlung von Nachrichten erforderlichen Transportprotokollen und der erforderlichen Art der Prozess- und Anwendungsdomänenwiederverwendung. In der folgenden Tabelle werden die Daten zu diesen Anforderungen zusammengefasst.  
  
|Hostumgebung|Plattformverfügbarkeit|Unterstützte Transportprotokolle|Prozess- und AppDomain-Wiederverwendung|  
|-------------------------|---------------------------|--------------------------|-------------------------------------|  
|Verwaltete Anwendungen ("Selbsthosting")|[!INCLUDE[wxp](../../../includes/wxp-md.md)], [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], [!INCLUDE[wv](../../../includes/wv-md.md)],<br /><br /> [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|Nein|  
|Windows-Dienste (früher als NT-Dienste bezeichnet)|[!INCLUDE[wxp](../../../includes/wxp-md.md)], [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], [!INCLUDE[wv](../../../includes/wv-md.md)],<br /><br /> [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|Nein|  
|IIS 5,1|[!INCLUDE[wxp](../../../includes/wxp-md.md)]|HTTP|Ja|  
|[!INCLUDE[iis601](../../../includes/iis601-md.md)]|[!INCLUDE[ws2003](../../../includes/ws2003-md.md)]|HTTP|Ja|  
|Windows Process Activation Service (WAS)|[!INCLUDE[wv](../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|Ja|  
  
 Sie müssen unbedingt beachten, dass die Sicherheit gefährdet wird, wenn ein Dienst oder eine Erweiterung auf einem nicht vertrauenswürdigen Host ausgeführt wird. Beachten Sie zudem, dass eine Anwendung sicherstellen muss, dass der Benutzer nicht abgemeldet wird, wenn ein <xref:System.ServiceModel.ServiceHost> mit Identitätswechsel geöffnet wird, indem beispielsweise die <xref:System.Security.Principal.WindowsIdentity> des Benutzers zwischengespeichert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Systemanforderungen](../../../docs/framework/wcf/wcf-system-requirements.md)  
 [Grundlegender Programmierlebenszyklus](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
 [Implementieren von Dienstverträgen](../../../docs/framework/wcf/implementing-service-contracts.md)  
 [How to: Host a WCF Service in IIS (Vorgehensweise: Hosten eines WCF-Diensts in IIS)](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)  
 [How to: Host a WCF Service in IIS (Vorgehensweise: Hosten eines WCF-Diensts in WAS)](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)  
 [Vorgehensweise: Hosten eines WCF-Diensts in einem verwalteten Windows-Dienst](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)  
 [Vorgehensweise Hosten eines WCF-Diensts in einer verwalteten Anwendung](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)

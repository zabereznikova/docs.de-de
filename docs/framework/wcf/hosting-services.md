---
title: Hosting-Dienste
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF]
ms.assetid: 192be927-6be2-4fda-98f0-e513c4881acc
ms.openlocfilehash: b1a0a07876e9cc111e8c5eef56f208d7bf2cb49f
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2019
ms.locfileid: "67487702"
---
# <a name="hosting-services"></a>Hosting-Dienste
Zur Aktivierung muss der Dienst in einer Laufzeitumgebung gehostet werden, die ihn erstellt und seinen Kontext sowie seine Lebensdauer steuert. Windows Communication Foundation (WCF)-Dienste können in jedem Windows-Prozess ausgeführt werden soll, Code unterstützt verwalteten.  
  
 WCF bietet ein einheitliches Programmiermodell zum Erstellen von dienstorientierten Anwendungen. Dieses Programmiermodell bleibt konsistent und ist von der Laufzeitumgebung unabhängig, in der der Dienst bereitgestellt wird. In der Praxis bedeutet das, dass der Code für Dienste relativ unabhängig von der Hostingoption ist.  
  
 Die Hostingoptionen reichen von einfachen Konsolenanwendungen bis zu Serverumgebungen, z.&#160;B. ein Windows-Dienst, der in einem Arbeitsprozess unter Internetinformationsdiensten (IIS) oder Windows Activation Service (WAS) ausgeführt wird. Entwickler wählen die Hostumgebung aus, die die Bereitstellungsanforderungen des Diensts erfüllt. Diese Anforderungen können von der Plattform, auf der die Anwendung bereitgestellt wird, dem Transportprotokoll, mit dem Nachrichten gesendet und empfangen werden müssen, dem Typ der Prozesswiederverwendung oder anderen Prozessverwaltungsfunktionen, die zur Sicherstellung adäquater Verfügbarkeit erforderlich sind, anderen Verwaltungsanforderungen oder Anforderungen bezüglich der Zuverlässigkeit abhängig sein. Im nächsten Abschnitt erhalten Sie Informationen und Hinweise zu Hostingoptionen.  
  
## <a name="hosting-options"></a>Hostingoptionen  
  
#### <a name="self-hosting-in-a-managed-application"></a>Selbsthosting in einer verwalteten Anwendung  
 WCF-Dienste können in jeder verwalteten Anwendung gehostet werden. Dies ist die flexibelste Option, da hier die wenigste Infrastruktur bereitzustellen ist. Sie betten den Code für den Dienst in den verwalteten Anwendungscode ein und erstellen und öffnen dann eine Instanz von <xref:System.ServiceModel.ServiceHost> , um den Dienst zur Verfügung zu stellen. Weitere Informationen finden Sie unter [Vorgehensweise: Hosten eines WCF-Diensts in einer verwalteten Anwendung](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).  
  
 Diese Option ermöglicht zwei gängige Szenarien: WCF-Dienste, die in konsolenanwendungen und rich Client-Anwendungen wie z. B. jene auf Grundlage von Windows Presentation Foundation (WPF) oder Windows Forms (WinForms) ausgeführt. Hosten eines WCF-Diensts in einer Konsolenanwendung eignet sich in der Regel während der Entwicklungsphase der Anwendung. Die Anwendung lässt sich dann einfach debuggen. Ablaufverfolgungsinformationen über die Anwendung lassen sich leichter ermitteln, um herauszufinden, was intern in der Anwendung vor sich geht. Zudem lässt sich die Anwendung dann einfacher an andere Speicherorte kopieren. Diese Hostingoption erleichtert auch die für rich Client-Anwendungen, z. B. WPF und WinForms-Anwendungen, für die Kommunikation mit der Außenwelt. Z. B. ein Peer-zu-Peer Zusammenarbeitsclient, der WPF für seine Benutzeroberfläche verwendet und auch hostet einen WCF-Dienst, der von anderen Clients herstellen und Informationen austauschen.  
  
#### <a name="managed-windows-services"></a>Verwaltete Windows-Dienste  
 Diese Hostingoption besteht in der Registrierung der Anwendungsdomäne (AppDomain), die einen WCF-Dienst als verwalteten Windows-Dienst (früher als NT-Dienst) hostet, sodass die Prozesslebensdauer des Diensts vom dienststeuerungs-Manager (SCM) gesteuert wird für Windows-Dienste. Wie bei der Selbsthosting-Option muss auch bei diesem Typ von Hostumgebung ein Teil des Hostingcodes Bestandteil des Anwendungscodes sein. Der Dienst wird als sowohl ein Windows-Dienst sowie eines WCF-Diensts Bestellmodul von Erben implementiert die <xref:System.ServiceProcess.ServiceBase> Klasse als auch aus einer WCF-service-Vertragsschnittstelle. Die <xref:System.ServiceModel.ServiceHost> -Instanz wird erstellt, mit einer überschriebenen <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> -Methode geöffnet und mit einer überschriebenen <xref:System.ServiceProcess.ServiceBase.OnStop> -Methode geschlossen. Außerdem muss eine Installerklasse implementiert werden, die von <xref:System.Configuration.Install.Installer> abgeleitet ist, damit das Programm mit dem Tool Installutil.exe als Windows-Dienst installiert werden kann. Weitere Informationen finden Sie unter [Vorgehensweise: Hosten eines WCF-Diensts in einem verwalteten Windows-Dienst](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md). Das Szenario, das durch die Hostingoption des verwalteten Windows Diensts aktiviert ist, die eine lang andauernde WCF-Diensts in einer sicheren Umgebung, die nicht nachrichtenaktivierten außerhalb von IIS gehostet. Die Lebensdauer des Diensts wird stattdessen vom Betriebssystem gesteuert. Diese Hostingoption ist in allen Windows-Versionen verfügbar.  
  
#### <a name="internet-information-services-iis"></a>IIS (Internet Information Services)  
 Die IIS-Hostingoption ist in ASP.NET integriert und verwendet die Funktionen, die diese Technologien bieten, die z. b. prozesswiederverwendung, im Leerlauf das Herunterfahren, prozessüberwachung und die Nachrichtenbasierte Aktivierung. Unter den Betriebssystemen [!INCLUDE[wxp](../../../includes/wxp-md.md)] und [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] ist dies die bevorzugte Lösung für das Hosten von Webdienstanwendungen, die stets verfügbar und weitgehend skalierbar sein müssen. IIS bietet zudem die integrierte Verwaltbarkeit, die Kunden von einem Serverprodukt für Unternehmen erwarten. Diese Hostingoption erfordert, dass IIS korrekt konfiguriert wurde, jedoch muss keinerlei Hostcode für die Anwendung geschrieben werden. Weitere Informationen zum Konfigurieren von IIS-hosting für einen WCF-Dienst finden Sie unter [Vorgehensweise: Hosten ein WCF-Diensts in IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).  
  
 Beachten Sie, dass von IIS gehostete Dienste nur den HTTP-Transport verwenden können. Mit der Implementierung in IIS&#160;5.1 wurden einige Einschränkungen in [!INCLUDE[wxp](../../../includes/wxp-md.md)]eingeführt. Die Nachrichtenbasierte Aktivierung für einen WCF-Dienst von IIS 5.1 auf bereitgestellten [!INCLUDE[wxp](../../../includes/wxp-md.md)] jeden anderen selbst gehosteten WCF-Dienst auf demselben Computer über Port 80 für die Kommunikation blockiert. WCF-Dienste können in der gleichen AppDomain/Application Pool/Worker Process wie andere Anwendungen, wenn Sie auf IIS 6.0 gehostet ausgeführt [!INCLUDE[ws2003](../../../includes/ws2003-md.md)]. Aber da WCF und IIS 6.0 die Kernelmodus-HTTP-Protokollstapel (HTTP.sys) verwenden, können IIS 6.0 mit anderen selbst gehosteten WCF-Diensten auf demselben Computer, im Gegensatz zu IIS 5.1 Port 80 freigeben.  
  
#### <a name="windows-process-activation-service-was"></a>Windows Process Activation Service (WAS)  
 Windows Process Activation Service (WAS) ist der neue Prozessaktivierungsmechanismus für [!INCLUDE[lserver](../../../includes/lserver-md.md)] , der auch unter [!INCLUDE[wv](../../../includes/wv-md.md)]verfügbar ist. Er behält das vertraute IIS 6.0-Prozessmodell (Anwendungspools und nachrichtenbasierte prozessaktivierung) und die Abhängigkeit von HTTP-hosting-Funktionen (wie rascher Ausfallschutz, Systemüberwachung und Wiederverwendung), aber es entfernt werden, aus der Aktivierung Architektur. IIS 7.0 nutzt WAS zur nachrichtenbasierten Aktivierung über HTTP. Weitere WCF-Komponenten stecken Sie auch in WAS-Aktivierung bereit, über die anderen Protokolle, die von WCF unterstützt, z. B. TCP, MSMQ und named Pipes. Dies ermöglicht es Anwendungen, die mit Kommunikationsprotokollen arbeiten, die IIS-Features zu nutzen, die nur für HTTP-basierte Anwendungen verfügbar waren, beispielsweise die Prozesswiederverwendung, den schnellen Fehlerschutz und das gemeinsame Konfigurationssystem.  
  
 Diese Hostingoption erfordert, dass WAS korrekt konfiguriert wurde, jedoch muss keinerlei Hostcode für die Anwendung geschrieben werden. Weitere Informationen zum Konfigurieren hostet, finden Sie unter [Vorgehensweise: Hosten eines WCF-Diensts in WAS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).  
  
## <a name="choosing-a-hosting-environment"></a>Auswählen einer Hostumgebung  
 In der folgenden Tabelle werden einige wichtige Vorteile und Szenarien im Zusammenhang mit den verschiedenen Hostingoptionen zusammengefasst.  
  
|Hostumgebung|Häufige Szenarien|Hauptvorteile und Einschränkungen|  
|-------------------------|----------------------|----------------------------------|  
|Verwaltete Anwendung ("Selbsthosting")|-Konsolenanwendungen, die während der Entwicklung verwendet.<br />-Rich WinForm und WPF-Clientanwendungen, die auf Dienste zugreifen.|-Flexibel.<br />– Einfach bereitzustellen.<br />-Keine unternehmenslösung für Dienste.|  
|Windows-Dienste (früher als NT-Dienste bezeichnet)|– Eine lang andauernde WCF-Dienst außerhalb von IIS gehostet.|-Prozesslebensdauer des Dienst, der durch das Betriebssystem, nicht nachrichtenaktivierten gesteuert wird.<br />-Der von allen Versionen von Windows unterstützt wird.<br />-Sicheren Umgebung.|  
|IIS 5.1, IIS 6.0|-Ausführen eines WCF-Diensts Seite-an-Seite mit ASP.NET-Inhalt im Internet unter Verwendung des HTTP-Protokolls.|-Prozesswiederverwendung.<br />– Im Leerlauf Herunterfahren.<br />-Prozessüberwachung.<br />– Meldungsbasierte Aktivierung.<br />– Nur für HTTP.|  
|Windows Process Activation Service (WAS)|– Zum Ausführen eines WCF-Diensts ohne Installation von IIS im Internet unter Verwendung verschiedener Transportprotokolle.|-IIS ist nicht erforderlich.<br />-Prozesswiederverwendung.<br />– Im Leerlauf Herunterfahren.<br />-Prozessüberwachung.<br />– Meldungsbasierte Aktivierung.<br />– Funktioniert mit HTTP, TCP, named Pipes und MSMQ.|  
|IIS 7.0|-Ausführen eines WCF-Diensts mit ASP.NET-Inhalt an.<br />– Zum Ausführen eines WCF-Diensts im Internet unter Verwendung verschiedener Transportprotokolle.|-Vorteile war.<br />-Integration mit ASP.NET und IIS-Inhalt.|  
  
 Die Wahl der Hostumgebung hängt von der Windows-Version ab, unter der der Dienst bereitgestellt wird, den für die Übermittlung von Nachrichten erforderlichen Transportprotokollen und der erforderlichen Art der Prozess- und Anwendungsdomänenwiederverwendung. In der folgenden Tabelle werden die Daten zu diesen Anforderungen zusammengefasst.  
  
|Hostumgebung|Plattformverfügbarkeit|Unterstützte Transportprotokolle|Prozess- und AppDomain-Wiederverwendung|  
|-------------------------|---------------------------|--------------------------|-------------------------------------|  
|Verwaltete Anwendungen ("Selbsthosting")|[!INCLUDE[wxp](../../../includes/wxp-md.md)], [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], [!INCLUDE[wv](../../../includes/wv-md.md)],<br /><br /> [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|Nein|  
|Windows-Dienste (früher als NT-Dienste bezeichnet)|[!INCLUDE[wxp](../../../includes/wxp-md.md)], [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], [!INCLUDE[wv](../../../includes/wv-md.md)],<br /><br /> [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|Nein|  
|IIS 5,1|[!INCLUDE[wxp](../../../includes/wxp-md.md)]|HTTP|Ja|  
|IIS 6.0|[!INCLUDE[ws2003](../../../includes/ws2003-md.md)]|HTTP|Ja|  
|Windows Process Activation Service (WAS)|[!INCLUDE[wv](../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|Ja|  
  
 Sie müssen unbedingt beachten, dass die Sicherheit gefährdet wird, wenn ein Dienst oder eine Erweiterung auf einem nicht vertrauenswürdigen Host ausgeführt wird. Beachten Sie zudem, dass eine Anwendung sicherstellen muss, dass der Benutzer nicht abgemeldet wird, wenn ein <xref:System.ServiceModel.ServiceHost> mit Identitätswechsel geöffnet wird, indem beispielsweise die <xref:System.Security.Principal.WindowsIdentity> des Benutzers zwischengespeichert wird.  
  
## <a name="see-also"></a>Siehe auch

- [Systemanforderungen](../../../docs/framework/wcf/wcf-system-requirements.md)
- [Grundlegender Programmierlebenszyklus](../../../docs/framework/wcf/basic-programming-lifecycle.md)
- [Implementieren von Dienstverträgen](../../../docs/framework/wcf/implementing-service-contracts.md)
- [Vorgehensweise: Hosten eines WCF-Diensts in IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
- [Vorgehensweise: Hosten eines WCF-Diensts in WAS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)
- [Vorgehensweise: Hosten eines WCF-Diensts in einem verwalteten Windows-Dienst](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)
- [Vorgehensweise: Hosten eines WCF-Diensts in einer verwalteten Anwendung](../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)

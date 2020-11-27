---
title: Hosting-Dienste
description: Erfahren Sie mehr über die Hostingoptionen für einen WCF-Dienst. Ein Dienst muss in einer Laufzeitumgebung gehostet werden, die ihn erstellt und seinen Kontext und seine Lebensdauer steuert.
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF]
ms.assetid: 192be927-6be2-4fda-98f0-e513c4881acc
ms.openlocfilehash: 41a7a3e651d234de4079455a667df670d6c7435d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294650"
---
# <a name="hosting-services"></a>Hostingdienste

Zur Aktivierung muss der Dienst in einer Laufzeitumgebung gehostet werden, die ihn erstellt und seinen Kontext sowie seine Lebensdauer steuert. Windows Communication Foundation (WCF)-Dienste können in jedem Windows-Prozess ausgeführt werden, der verwalteten Code unterstützt.

WCF stellt ein einheitliches Programmiermodell zum Entwickeln von Dienst orientierten Anwendungen bereit. Dieses Programmiermodell bleibt konsistent und ist von der Laufzeitumgebung unabhängig, in der der Dienst bereitgestellt wird. In der Praxis bedeutet das, dass der Code für Dienste relativ unabhängig von der Hostingoption ist.

Die Hostingoptionen reichen von einfachen Konsolenanwendungen bis zu Serverumgebungen, z.&#160;B. ein Windows-Dienst, der in einem Arbeitsprozess unter Internetinformationsdiensten (IIS) oder Windows Activation Service (WAS) ausgeführt wird. Entwickler wählen die Hostumgebung aus, die die Bereitstellungsanforderungen des Diensts erfüllt. Diese Anforderungen können von der Plattform, auf der die Anwendung bereitgestellt wird, dem Transportprotokoll, mit dem Nachrichten gesendet und empfangen werden müssen, dem Typ der Prozesswiederverwendung oder anderen Prozessverwaltungsfunktionen, die zur Sicherstellung adäquater Verfügbarkeit erforderlich sind, anderen Verwaltungsanforderungen oder Anforderungen bezüglich der Zuverlässigkeit abhängig sein. Im nächsten Abschnitt erhalten Sie Informationen und Hinweise zu Hostingoptionen.

## <a name="hosting-options"></a>Hostingoptionen

### <a name="self-host-in-a-managed-application"></a>Self-Host in einer verwalteten Anwendung

 WCF-Dienste können in jeder verwalteten Anwendung gehostet werden. Dies ist die flexibelste Option, da hier die wenigste Infrastruktur bereitzustellen ist. Sie betten den Code für den Dienst in den verwalteten Anwendungscode ein und erstellen und öffnen dann eine Instanz von <xref:System.ServiceModel.ServiceHost> , um den Dienst zur Verfügung zu stellen. Weitere Informationen finden Sie unter Vorgehens [Weise: Hosten eines WCF-Diensts in einer verwalteten Anwendung](how-to-host-a-wcf-service-in-a-managed-application.md).

 Diese Option ermöglicht zwei gängige Szenarien: WCF-Dienste, die in Konsolen Anwendungen und Rich Client-Anwendungen ausgeführt werden, z. b. solche, die auf Windows Presentation Foundation (WPF) oder Windows Forms (WinForms) basieren. Das Hosting eines WCF-Diensts in einer Konsolenanwendung ist in der Regel während der Entwicklungsphase der Anwendung nützlich. Die Anwendung lässt sich dann einfach debuggen. Ablaufverfolgungsinformationen über die Anwendung lassen sich leichter ermitteln, um herauszufinden, was intern in der Anwendung vor sich geht. Zudem lässt sich die Anwendung dann einfacher an andere Speicherorte kopieren. Diese Hostingoption erleichtert auch die Kommunikation von Rich Client-Anwendungen wie WPF-und WinForms-Anwendungen mit der Außenwelt. Beispielsweise ein Peer-to-Peer-Kollaborations Client, der WPF für die Benutzeroberfläche verwendet und außerdem einen WCF-Dienst hostet, der anderen Clients das Herstellen einer Verbindung mit dem Client und das Freigeben von Informationen ermöglicht.

### <a name="managed-windows-services"></a>Verwaltete Windows-Dienste

Diese Hostingoption besteht darin, die Anwendungsdomäne (AppDomain), die einen WCF-Dienst hostet, als verwalteten Windows-Dienst (früher NT-Dienst genannt) zu registrieren, sodass die Prozess Lebensdauer des Diensts vom Dienststeuerungs-Manager (Service Control Manager, SCM) für Windows-Dienste gesteuert wird. Wie bei der Selbsthosting-Option muss auch bei diesem Typ von Hostumgebung ein Teil des Hostingcodes Bestandteil des Anwendungscodes sein. Der Dienst wird sowohl als Windows-Dienst als auch als WCF-Dienst implementiert, indem er von der- <xref:System.ServiceProcess.ServiceBase> Klasse und von einer WCF-Dienstvertrags Schnittstelle geerbt wird. Die <xref:System.ServiceModel.ServiceHost> -Instanz wird erstellt, mit einer überschriebenen <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> -Methode geöffnet und mit einer überschriebenen <xref:System.ServiceProcess.ServiceBase.OnStop> -Methode geschlossen. Außerdem muss eine Installerklasse implementiert werden, die von <xref:System.Configuration.Install.Installer> abgeleitet ist, damit das Programm mit dem Tool Installutil.exe als Windows-Dienst installiert werden kann. Weitere Informationen finden Sie unter Vorgehens [Weise: Hosten eines WCF-Diensts in einem verwalteten Windows-Dienst](./feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md). Das von der verwalteten Windows-Dienst Hostingoption aktivierte Szenario besteht darin, dass ein WCF-Dienst mit langer Laufzeit, der außerhalb von IIS gehostet wird, in einer sicheren, nicht Nachrichten aktivierten Umgebung gehostet wird. Die Lebensdauer des Diensts wird stattdessen vom Betriebssystem gesteuert. Diese Hostingoption ist in allen Windows-Versionen verfügbar.

### <a name="internet-information-services-iis"></a>IIS (Internet Information Services)

Die IIS-Hostingoption ist in ASP.NET integriert und nutzt die Features, die diese Technologien bieten, wie z. b. Prozess Wiederverwendung, Leerlauf herunterfahren, Prozess Integritäts Überwachung und Nachrichten basierte Aktivierung. Unter den Betriebssystemen Windows XP und Windows Server 2003 ist dies die bevorzugte Lösung für das Hosting von Webdienst Anwendungen, die hoch verfügbar und hochgradig skalierbar sein müssen. IIS bietet zudem die integrierte Verwaltbarkeit, die Kunden von einem Serverprodukt für Unternehmen erwarten. Diese Hostingoption erfordert, dass IIS korrekt konfiguriert wurde, jedoch muss keinerlei Hostcode für die Anwendung geschrieben werden. Weitere Informationen zum Konfigurieren von IIS-Hosting für einen WCF-Dienst finden Sie unter Gewusst [wie: Hosten eines WCF-Diensts in IIS](./feature-details/how-to-host-a-wcf-service-in-iis.md).

 IIS-gehostete Dienste können nur den HTTP-Transport verwenden. Die Implementierung in IIS 5,1 hat einige Einschränkungen in Windows XP eingeführt. Durch die Nachrichten basierte Aktivierung, die von IIS 5,1 unter Windows XP für einen WCF-Dienst bereitgestellt wird, werden alle anderen selbst gehosteten WCF-Dienste auf demselben Computer daran gehindert, Port 80 für die Kommunikation zu verwenden. WCF-Dienste können in der gleichen Anwendungsdomäne/dem Anwendungs Pool bzw. Arbeitsprozess wie andere Anwendungen ausgeführt werden, wenn Sie von IIS 6,0 unter Windows Server 2003 gehostet werden. Da WCF und IIS 6,0 beide den Kernel Modus-HTTP-Stapel (HTTP.sys) verwenden, kann IIS 6,0 Port 80 für andere selbst gehostete WCF-Dienste freigeben, die auf demselben Computer ausgeführt werden, im Gegensatz zu IIS 5,1.

### <a name="windows-process-activation-service-was"></a>Windows Process Activation Service (WAS)

Der Windows-Prozess Aktivierungs Dienst (Windows Process Activation Service, was) ist der neue Prozess Aktivierungsmechanismus für Windows Server 2008, der auch unter Windows Vista verfügbar ist. Dabei werden das vertraute IIS 6,0-Prozessmodell (Anwendungs Pools und Nachrichten basierte Prozess Aktivierung) und Hostingfunktionen (z. b. der schnelle Ausfallschutz, die Systemüberwachung und Wiederverwendung) beibehalten, aber die Abhängigkeit von http aus der Aktivierungs Architektur wird entfernt. IIS 7,0 verwendet was, um die Nachrichten basierte Aktivierung über HTTP durchzuführen. Zusätzliche WCF-Komponenten werden auch in was eingebunden, um die Nachrichten basierte Aktivierung über die anderen von WCF unterstützten Protokolle bereitzustellen, wie z. b. TCP, MSMQ und Named Pipes. Dies ermöglicht es Anwendungen, die mit Kommunikationsprotokollen arbeiten, die IIS-Features zu nutzen, die nur für HTTP-basierte Anwendungen verfügbar waren, beispielsweise die Prozesswiederverwendung, den schnellen Fehlerschutz und das gemeinsame Konfigurationssystem.

 Diese Hostingoption erfordert, dass WAS korrekt konfiguriert wurde, jedoch muss keinerlei Hostcode für die Anwendung geschrieben werden. Weitere Informationen zum Konfigurieren von was-Hosting finden Sie unter Gewusst [wie: Hosten eines WCF-Diensts in was](./feature-details/how-to-host-a-wcf-service-in-was.md).

## <a name="choose-a-hosting-environment"></a>Auswählen einer Hostingumgebung

 In der folgenden Tabelle werden einige wichtige Vorteile und Szenarien im Zusammenhang mit den verschiedenen Hostingoptionen zusammengefasst.

|Hostumgebung|Häufige Szenarios|Hauptvorteile und Einschränkungen|
|-------------------------|----------------------|----------------------------------|
|Verwaltete Anwendung ("Selbsthosting")|-Konsolen Anwendungen, die während der Entwicklung verwendet werden.<br />-Umfangreiche WinForm-und WPF-Client Anwendungen, die auf Dienste zugreifen.|Flexiblen.<br />-Die Bereitstellung ist einfach.<br />-Keine Enterprise-Lösung für Dienste.|
|Windows-Dienste (früher als NT-Dienste bezeichnet)|-Ein WCF-Dienst mit langer Laufzeit, der außerhalb von IIS gehostet wird.|-Dienst Prozess Lebensdauer wird vom Betriebssystem gesteuert, nicht nach Nachrichten aktiviert.<br />-Wird von allen Versionen von Windows unterstützt.<br />-Sichere Umgebung.|
|IIS 5,1, IIS 6,0|: Parallele Ausführung eines WCF-Dienstanbieter mit ASP.net-Inhalt im Internet mithilfe des HTTP-Protokolls.|-Prozess Wiederverwendung.<br />-Leerlauf heruntergefahren.<br />-Prozess Integritäts Überwachung.<br />-Nachrichten basierte Aktivierung.<br />-Nur http.|
|Windows Process Activation Service (WAS)|-Ausführen eines WCF-diensdienstanbieter, ohne IIS im Internet unter Verwendung verschiedener Transportprotokolle zu installieren.|-IIS ist nicht erforderlich.<br />-Prozess Wiederverwendung.<br />-Leerlauf heruntergefahren.<br />-Prozess Integritäts Überwachung.<br />-Nachrichten basierte Aktivierung.<br />: Funktioniert mit http, TCP, Named Pipes und MSMQ.|
|IIS 7.0|-Ausführen eines WCF-Dienstanbieter mit ASP.net-Inhalt.<br />-Ausführen eines WCF-diensdienstanbieter mithilfe verschiedener Transportprotokolle im Internet.|-WAS-Vorteile.<br />-Integriert in ASP.net-und IIS-Inhalt.|

 Die Wahl der Hostumgebung hängt von der Windows-Version ab, unter der der Dienst bereitgestellt wird, den für die Übermittlung von Nachrichten erforderlichen Transportprotokollen und der erforderlichen Art der Prozess- und Anwendungsdomänenwiederverwendung. In der folgenden Tabelle werden die Daten zu diesen Anforderungen zusammengefasst.

|Hostumgebung|Plattformverfügbarkeit|Unterstützte Transportprotokolle|Prozess- und AppDomain-Wiederverwendung|
|-------------------------|---------------------------|--------------------------|-------------------------------------|
|Verwaltete Anwendungen ("Selbsthosting")|Windows XP, Windows Server 2003, Windows Vista,<br /><br /> Windows Server 2008|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|Nein |
|Windows-Dienste (früher als NT-Dienste bezeichnet)|Windows XP, Windows Server 2003, Windows Vista,<br /><br /> Windows Server 2008|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|Nein |
|IIS 5,1|Windows XP|HTTP|Ja|
|IIS 6.0|Windows Server 2003|HTTP|Ja|
|Windows Process Activation Service (WAS)|Windows Vista, Windows Server 2008|HTTP,<br /><br /> net.tcp,<br /><br /> net.pipe,<br /><br /> net.msmq|Ja|

 Sie müssen unbedingt beachten, dass die Sicherheit gefährdet wird, wenn ein Dienst oder eine Erweiterung auf einem nicht vertrauenswürdigen Host ausgeführt wird. Außerdem muss eine Anwendung beim Öffnen eines unter Identitätswechsel <xref:System.ServiceModel.ServiceHost> sicherstellen, dass der Benutzer nicht abgemeldet wird, z. b. durch Zwischenspeichern der <xref:System.Security.Principal.WindowsIdentity> des Benutzers.

## <a name="see-also"></a>Weitere Informationen

- [Grundlegender Programmierlebenszyklus](basic-programming-lifecycle.md)
- [Implementieren von Dienstverträgen](implementing-service-contracts.md)
- [Vorgehensweise: Hosten eines WCF-Diensts in IIS](./feature-details/how-to-host-a-wcf-service-in-iis.md)
- [Vorgehensweise: Hosten eines WCF-Diensts in WAS](./feature-details/how-to-host-a-wcf-service-in-was.md)
- [Vorgehensweise: Hosten eines WCF-Diensts in einem verwalteten Windows-Dienst](./feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)
- [Vorgehensweise: Hosten eines WCF-Diensts in einer verwalteten Anwendung](how-to-host-a-wcf-service-in-a-managed-application.md)

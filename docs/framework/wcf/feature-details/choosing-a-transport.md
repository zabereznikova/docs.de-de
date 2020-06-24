---
title: Wählen eines Transports
description: 'Erfahren Sie mehr über die Kriterien für die Auswahl der Haupt Transporte, die WCF bietet: http, TCP und Named Pipes.'
ms.date: 03/30/2017
helpviewer_keywords:
- choosing transports [WCF]
ms.assetid: b169462b-f7b6-4cf4-9fca-d306909ee8bf
ms.openlocfilehash: e1a92203de25aa399316eea91a758802768442a0
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247493"
---
# <a name="choosing-a-transport"></a>Wählen eines Transports
In diesem Thema werden die Kriterien für die Auswahl der drei Haupt Transporte erläutert, die in Windows Communication Foundation (WCF) enthalten sind: http, TCP und Named Pipes. WCF enthält auch einen Message Queueing-Transport (auch als MSMQ bezeichnet), aber in diesem Dokument werden Message Queueing nicht behandelt.  
  
 Das WCF-Programmiermodell trennt Endpunkt Vorgänge (wie in einem Dienstvertrag ausgedrückt) von dem Transportmechanismus, der zwei Endpunkte verbindet. Dies gibt Ihnen Flexibilität bei der Entscheidung, wie Sie Ihre Dienste im Netzwerk offenlegen möchten.  
  
 In WCF geben Sie an, wie Daten über ein Netzwerk zwischen Endpunkten übertragen werden sollen, indem eine *Bindung*verwendet wird, die aus einer Sequenz von *Bindungs Elementen*besteht. Ein Transport wird durch ein Transportbindungselement dargestellt, das Teil der Bindung ist. Eine Bindung enthält optionale Protokollbindungselemente, wie Sicherheit, ein erforderliches Nachrichtenencoder-Bindungselement und ein erforderliches Transportbindungselement. Bei einem Transport wird das serialisierte Formular einer Nachricht an eine andere bzw. von einer anderen Anwendung gesendet.  
  
 Wenn Sie eine Verbindung zu einem vorhandenen Client oder Server herstellen möchten, haben Sie ggf. keine Wahl, welchen Transport Sie verwenden. Allerdings können WCF-Dienste über mehrere Endpunkte zugänglich gemacht werden, die jeweils über einen anderen Transport verfügen. Wenn ein einzelner Transport für die beabsichtigten Nutzer des Dienstes nicht ausreicht, können Sie in Erwägung ziehen, den Dienst über mehrere Endpunkte hinweg offenzulegen. Clientanwendungen können dann den Endpunkt verwenden, der am besten für sie geeignet ist.  
  
 Nachdem Sie einen Transport gewählt haben, müssen Sie eine Bindung auswählen, die den Transport verwendet. Sie können eine vom System bereitgestellte Bindung auswählen (siehe vom [System bereitgestellte Bindungen](../system-provided-bindings.md)), oder Sie können eine eigene benutzerdefinierte Bindung erstellen (siehe [benutzerdefinierte Bindungen](../extending/custom-bindings.md)). Sie können auch eine eigene Bindung anlegen. Weitere Informationen finden Sie unter [Erstellen benutzerdefinierter Bindungen](../extending/creating-user-defined-bindings.md).  
  
## <a name="advantages-of-each-transport"></a>Vorteile der einzelnen Transporte  
 In diesem Abschnitt sind die Hauptgründe für die Wahl einer der drei wichtigsten Transportarten beschrieben. Er enthält auch ein ausführliches Diagramm als Hilfe bei der Auswahl.  
  
### <a name="when-to-use-http-transport"></a>Verwenden des HTTP-Transports  
 HTTP ist ein Anforderung-/Antwortprotokoll für den Austausch zwischen Clients und Servern. Diese Transportart wird am häufigsten von Webbrowserclients verwendet, die mit einem Webserver kommunizieren. Der Client sendet eine Anforderung an einen Server, der nach Anforderungsnachrichten von Clients lauscht. Wenn der Server eine Anforderung empfängt, gibt er eine Antwort zurück, die den Status der Anforderung enthält. Wenn dieser Vorgang erfolgreich ist, werden optionale Daten, z. B. eine Webseite, eine Fehlermeldung oder andere Informationen, zurückgegeben. Weitere Informationen zum HTTP-Protokoll finden Sie unter [HTTP-Hypertext Transfer Protocol](https://www.w3.org/Protocols/).  
  
 Das HTTP-Protokoll basiert nicht auf einer Verbindung. Nachdem die Antwort gesendet wurde, wird kein entsprechender Zustand beibehalten. Die Anwendung muss jeden erforderlichen Zustand beibehalten, um Transaktionen mit mehreren Seiten verarbeiten zu können.  
  
 In WCF ist die HTTP-Transport Bindung für die Interoperabilität mit veralteten nicht-WCF-Systemen optimiert. Wenn alle kommunizierenden Parteien WCF verwenden, sind die TCP-basierten oder Named Pipes-basierten Bindungen schneller. Weitere Informationen finden Sie unter <xref:System.ServiceModel.NetTcpBinding> und <xref:System.ServiceModel.NetNamedPipeBinding>.  
  
### <a name="when-to-use-the-tcp-transport"></a>Verwenden des TCP-Transports  
 TCP ist ein verbindungsbasierter, datenstromorientierter Zustellungsdienst mit End-to-End-Fehlererkennung und -behebung. *Verbindungs basiert* bedeutet, dass vor dem Austauschen von Daten eine Kommunikationssitzung zwischen Hosts eingerichtet wird. Ein Host ist ein Gerät in einem TCP/IP-Netzwerk, das über eine logische IP-Adresse verfügt.  
  
 TCP ermöglicht die zuverlässige Datenzustellung und Benutzerfreundlichkeit. TCP benachrichtigt den Absender der Paketzustellung, stellt sicher, dass Pakete auch in der Sendereihenfolge zugestellt werden, überträgt verloren gegangene Pakete neu und sorgt dafür, dass Datenpakete nicht dupliziert werden. Beachten Sie, dass diese zuverlässige Übermittlung zwischen zwei TCP/IP-Knoten gilt und nicht mit *WS-ReliableMessaging*identisch ist, was zwischen Endpunkten gilt, unabhängig davon, wie viele zwischen Knoten Sie enthalten können.  
  
 Der WCF-TCP-Transport ist für das Szenario optimiert, in dem beide Enden der Kommunikation WCF verwenden. Diese Bindung ist die schnellste WCF-Bindung für Szenarien, die die Kommunikation zwischen verschiedenen Computern einschließen. Die Vorgänge des Nachrichtenaustauschs verwenden das <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> für die optimierte Nachrichtenübertragung. TCP ermöglicht die Duplexkommunikation und kann daher verwendet werden, um Duplexverträge zu implementieren, auch wenn der Client sich hinter NAT (Network Address Translation) befindet.  
  
### <a name="when-to-use-the-named-pipe-transport"></a>Verwenden des Transports mittels benannter Pipes  
 Eine benannte Pipe ist ein Objekt im Windows-Betriebssystemkernel, zum Beispiel ein Abschnitt eines gemeinsam genutzten Speichers, den Prozesse für die Kommunikation verwenden können. Eine benannte Pipe hat einen Namen und kann für die unidirektionale Kommunikation oder Duplexkommunikation zwischen Prozessen auf einem einzelnen Computer verwendet werden.  
  
 Wenn die Kommunikation zwischen verschiedenen WCF-Anwendungen auf einem einzelnen Computer erforderlich ist und Sie jegliche Kommunikation von einem anderen Computer verhindern möchten, verwenden Sie den Named Pipes-Transport. Eine weitere Einschränkung besteht darin, dass Prozesse, die über Windows-Remotedesktop ausgeführt werden, ggf. auf die Windows-Remotedesktopsitzung beschränkt sind, wenn sie nicht über erweiterte Berechtigungen verfügen.  
  
> [!WARNING]
> Wenn der Named Pipe-Transport mit einer WeakWildcard-URL-Reservierung für mehrere in IIS gehostete Sites verwendet wird, kann der folgende Fehler auftreten: Fehler beim Aktivierungsdienst 'NetPipeActivator' des Protokolls 'net.pipe', während versucht wurde, an der Site '2' zu lauschen. Deshalb wurde das Protokoll für die Site vorübergehend deaktiviert. Weitere Informationen finden Sie in der Ausnahmemeldung. URL: WeakWildcard: net. Pipe:/ \<machine name> /Status: conflictingregistration Exception: Prozess Name: SMSvcHost-Prozess-ID: 1076 \  
  
## <a name="decision-points-for-choosing-a-transport"></a>Entscheidungspunkte für die Auswahl eines Transports  
 In der folgenden Tabelle werden allgemeine Punkte beschrieben, die für die Auswahl eines Transports von Bedeutung sind. Sie sollten alle zusätzlichen Attribute und Transporte berücksichtigen, die für Ihre Anwendung gelten. Wählen Sie die Attribute aus, die für die Anwendung wichtig sind, wählen Sie die Transporte, die sich für die Attribute eignen, und wählen Sie anschließend die Transporte aus, die am besten mit Ihrem Attributsatz funktionieren.  
  
|attribute|BESCHREIBUNG|Häufig verwendete Transporte|  
|---------------|-----------------|------------------------|  
|Diagnose|Die Diagnose ermöglicht es Ihnen, Probleme mit der Transportkonnektivität automatisch zu erkennen. Alle Transporte unterstützen die Fähigkeit, Fehlerinformationen zurückzusenden, die die Konnektivität beschreiben. WCF enthält jedoch keine Diagnosetools für die Untersuchung von Netzwerkproblemen.|Keine|  
|Hosting|Alle WCF-Endpunkte müssen innerhalb einer Anwendung gehostet werden. IIS 6,0 und frühere Versionen unterstützen nur Host Anwendungen, die den HTTP-Transport verwenden. Unter Windows Vista wird die Unterstützung für das Hosting aller WCF-Transporte, einschließlich TCP und Named Pipes, hinzugefügt. Weitere Informationen finden Sie unter [Hosting in Internetinformationsdienste](hosting-in-internet-information-services.md) und [Hosting in Windows Process Activation Service](hosting-in-windows-process-activation-service.md).|HTTP|  
|Inspektion|Die Inspektion ist die Fähigkeit, während der Übertragung Informationen aus Nachrichten zu extrahieren und zu verarbeiten. Das HTTP-Protokoll trennt Routing- und Steuerungsinformationen von den Daten, um das Erstellen von Tools zu vereinfachen, die Nachrichten untersuchen und analysieren. Transporte, die leicht zu überprüfen sind, erfordern ggf. auch weniger Verarbeitungsleistung in Netzwerkeinrichtungen. Die verwendete Sicherheitsebene wirkt sich darauf aus, ob Nachrichten überprüft werden können.|HTTP|  
|Latency|Die Wartezeit ist die Mindestmenge an Zeit, die erforderlich ist, um einen Austausch von Nachrichten durchzuführen. Alle Netzwerkvorgänge weisen je nach gewähltem Transport mehr oder weniger Wartezeit (Latenz) auf. Das Verwenden der Duplexkommunikation oder unidirektionalen Kommunikation mit einem Transport, der das systemeigene Nachrichtenaustauschmuster Anforderung/Antwort verwendet, zum Beispiel HTTP, kann zu einer längeren Wartezeit führen, da die Korrelation von Nachrichten erforderlich ist. Erwägen Sie in dieser Situation, einen Transport zu verwenden, der als systemeigenes Nachrichtenaustauschmuster Duplex verwendet, zum Beispiel TCP.|TCP, Named<br /><br /> Pipe|  
|Reach|Die Reichweite eines Transports gibt an, in welchem Umfang der Transport eine Verbindung zu anderen Systemen herstellen kann. Der Transport mittels benannter Pipes besitzt nur eine geringe Reichweite. Er kann nur eine Verbindung zu Diensten herstellen, die auf dem gleichen Computer ausgeführt werden. Die Transportarten TCP und HTTP verfügen jeweils über eine ausgezeichnete Reichweite und können auch einige NAT- und Firewallkonfigurationen durchdringen. Weitere Informationen finden Sie unter [Arbeiten mit NATs und Firewalls](working-with-nats-and-firewalls.md).|HTTP, TCP|  
|Sicherheit|Die Sicherheit ist die Fähigkeit, während der Übertragung Nachrichten zu schützen, indem die Vertraulichkeit, Integrität oder Authentifizierung sichergestellt wird. Die Vertraulichkeit schützt eine Nachricht davor, untersucht zu werden, die Integrität schützt eine Nachricht davor, geändert zu werden, und die Authentifizierung liefert zuverlässige Informationen zum Absender oder Empfänger der Nachricht.<br /><br /> WCF unterstützt die Übertragungssicherheit auf Nachrichten Ebene und auf Transport Ebene. Die Nachrichtensicherheit wird mit einem Transport verknüpft, wenn der Transport einen gepufferten Übertragungsmodus unterstützt. Die Unterstützung für die Transportsicherheit ändert sich in Abhängigkeit vom gewählten Transport. Die Transportarten HTTP, TCP und benannte Pipe verfügen in Bezug auf die Unterstützung der Transportsicherheit über eine angemessene Parität.|All|  
|Throughput|Der Durchsatz misst die Datenmenge, die in einem bestimmten Zeitraum übertragen und verarbeitet werden kann. Wie die Wartezeit auch, kann der gewählte Transport sich auf den Durchsatz für Dienstvorgänge auswirken. Die Maximierung des Durchsatzes für einen Transport erfordert sowohl die Minimierung des Mehraufwands für die Übertragung von Inhalten als auch die Reduzierung des Wartezeitraums für den Abschluss des Nachrichtenaustauschs. Sowohl der TCP-Transport als auch der Transport mittels benannter Pipes fügen dem Nachrichtentext wenig Mehraufwand hinzu und unterstützen eine systemeigene Duplexform, die die Wartezeit auf Antworten für Nachrichten reduziert.|TCP, benannte Pipe|  
|Tools|Die Tools umfassen die Unterstützung für Drittanbieteranwendungen für ein Protokoll, mit dem die Entwicklung, die Diagnose, das Hosten und andere Aktivitäten durchgeführt werden können. Entwicklungstools und Softwareanwendungen, die in Verbindung mit dem HTTP-Protokoll verwendet werden können, stellen eine besonders hohe Investition dar.|HTTP|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.WSDualHttpBinding>
- <xref:System.ServiceModel.WSFederationHttpBinding>
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
- <xref:System.ServiceModel.NetNamedPipeBinding>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- [Bindungen](bindings.md)
- [Vom System bereitgestellte Bindungen](../system-provided-bindings.md)
- [Erstellen benutzerdefinierter Bindungen](../extending/creating-user-defined-bindings.md)

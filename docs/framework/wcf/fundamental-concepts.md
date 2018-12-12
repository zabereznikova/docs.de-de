---
title: Wesentliche Windows Communication Foundation-Begriffe
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], concepts
- concepts [WCF]
- fundamentals [WCF]
- Windows Communication Foundation [WCF], concepts
ms.assetid: 3e7e0afd-7913-499d-bafb-eac7caacbc7a
ms.openlocfilehash: 9957b937dd59f82a5d1962fee33593d7a0c1b7c1
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286558"
---
# <a name="fundamental-windows-communication-foundation-concepts"></a>Wesentliche Windows Communication Foundation-Begriffe
Dieses Dokument bietet einen allgemeinen Überblick über die Windows Communication Foundation (WCF)-Architektur. Es ist dafür vorgesehen, Hauptkonzepte zu erklären und zu erläutern, wie diese zusammenpassen. Ein Tutorial zum Erstellen der einfachsten Version eines WCF-Dienst und Client finden Sie unter [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md). WCF-Programmierung finden Sie unter [Basis-WCF-Programmierung](../../../docs/framework/wcf/basic-wcf-programming.md).  
  
## <a name="wcf-fundamentals"></a>Grundlagen von WCF  
 WCF ist eine Laufzeit und einen Satz von APIs zum Erstellen von Systemen, die Nachrichten zwischen Diensten und Clients zu senden. Die gleiche Infrastruktur und die gleichen APIs werden verwendet, um Anwendungen zu erstellen, die mit anderen Anwendungen im gleichen Computersystem oder in einem System kommunizieren, das in einem anderen Unternehmen besteht und auf das über das Internet zugegriffen wird.  
  
### <a name="messaging-and-endpoints"></a>Messaging und Endpunkte  
 WCF basiert auf dem Konzept einer nachrichtenbasierten Kommunikation, und alle, die modelliert werden kann, wie eine Nachricht (z. B. eine HTTP-Anforderung oder eine Message Queuing (auch bekannt als MSMQ)-Nachricht) im Programmierungsmodell auf einheitliche Art dargestellt werden kann. Dies ermöglicht eine einheitliche API über verschiedene Transportmechanismen hinweg.  
  
 Das Modell unterscheidet zwischen *Clients*, welche sind Anwendungen, die Kommunikation initiieren und *Services*, die Anwendungen, die für Clients mit ihnen kommunizieren und darauf reagieren, die gewartet werden die Kommunikation. Eine einzelne Anwendung kann sowohl als Client als auch als Dienst fungieren. Beispiele finden Sie in [Duplexdienste](../../../docs/framework/wcf/feature-details/duplex-services.md) und [Peer-zu-Peer-Netzwerke](../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
 Nachrichten werden zwischen Endpunkten versendet. *Endpunkte* sind Orte, wo Nachrichten gesendet oder empfangen werden (oder beides), und alle Informationen, die für den Nachrichtenaustausch benötigt definieren. Ein Dienst macht einen oder mehrere Anwendungsendpunkte verfügbar (ebenso wie keinen oder mehrere Infrastrukturendpunkte), und der Client erstellt einen Endpunkt, der mit einem der Endpunkte des Diensts kompatibel ist.  
  
 Ein *Endpunkt* beschreibt in eine standardbasierte Art, in dem Nachrichten gesendet werden sollen, wie sie gesendet werden sollen und wie die Nachrichten aussehen sollte. Ein Dienst kann diese Informationen als Metadaten, die Clients, zum Generieren von entsprechenden WCF-Clients und die Kommunikation verarbeiten kann verfügbar zu machen *Stapel*.  
  
### <a name="communication-protocols"></a>Kommunikationsprotokolle  
 Eine erforderliche Element des kommunikationsstapels ist die *Transportprotokoll*. Nachrichten können über Intranets und das Internet mithilfe von allgemein gebräuchlichen Transportprotokollen, z. B. HTTP und TCP, gesendet werden. Es bestehen noch weitere Transporte, die eine Kommunikation mit Message Queuing-Anwendungen und mit Knoten in einem Peer Networking-Netz unterstützen. Weitere Transportmechanismen können über den integrierten Erweiterungspunkten von WCF hinzugefügt werden.  
  
 Ein anderes erforderliches Element des Kommunikationsstapels ist die Codierung, die angibt, wie jede Nachricht formatiert ist. WCF bietet die folgenden Codierungen:  
  
-   Textcodierung, eine interoperable Codierung.  
  
-   Message Transmission Optimization Mechanism (MTOM)-Codierung, eine interoperable Möglichkeit, unstrukturierte Binärdaten effizient an einem und von einem Dienst zu senden.  
  
-   Binäre Codierung für effiziente Übertragung.  
  
 Mehr Codierungsmechanismen (z. B. eine komprimierungscodierung) können mit den integrierten Erweiterungspunkten von WCF hinzugefügt werden.  
  
### <a name="message-patterns"></a>Messagingmuster  
 WCF unterstützt mehrere Messagingmuster, einschließlich Anforderung-Antwort, unidirektional und duplex-Kommunikation. Verschiedene Transporte unterstützen verschiedene Messagingmuster und beeinflussen so die Interaktionstypen, die sie unterstützen. Der WCF-APIs und die Laufzeit auch hilfreich zum Senden von Nachrichten sicher und zuverlässig.  
  
## <a name="wcf-terms"></a>WCF-Begriffe  
 Andere Konzepte und Begriffe, die in der WCF-Dokumentation verwendeten gehören die folgenden.  
  
 message  
 Eine eigenständige Dateneinheit, die aus mehreren Teilen bestehen kann, unter anderem aus Text und Headern.  
  
 service  
 Ein Konstrukt, das einen oder mehrere Endpunkte verfügbar macht, wobei jeder Endpunkt wiederum einen oder mehrere Dienstvorgänge verfügbar macht.  
  
 Endpunkt (endpoint)  
 Ein Konstrukt, von dem Nachrichten gesendet oder empfangen werden (oder beides). Es umfasst einen Speicherort (eine Adresse), der definiert, in denen Nachrichten, eine Spezifikation des Kommunikationsmechanismus (einer Bindung) gesendet werden können, die beschreibt, wie die Nachrichten gesendet werden sollen, und eine Definition für eine Gruppe von Nachrichten, die gesendet oder empfangen werden können (oder beides) an Speicherort (einen Dienstvertrag), die beschreibt, welche Nachricht gesendet werden kann.  
  
 Ein WCF-Dienst wird allgemein als eine Auflistung von Endpunkten verfügbar gemacht.  
  
 Anwendungsendpunkt (application endpoint)  
 Ein von der Anwendung verfügbar gemachter Endpunkt, der einem Dienstvertrag entspricht, der von der Anwendung implementiert wurde.  
  
 Infrastrukturendpunkt  
 Ein Endpunkt, der von der Infrastruktur verfügbar gemacht wird, um Funktionalitäten zu erleichtern, die vom Dienst benötigt oder bereitgestellt werden, der sich nicht auf einen Dienstvertrag bezieht. Ein Dienst könnte z. B. einen Infrastrukturendpunkt aufweisen, der Metadateninformationen bereitstellt.  
  
 Adresse  
 Gibt den Speicherort an, an dem Nachrichten empfangen werden. Sie wird als ein Uniform Resource Identifier (URI) angegeben. Der URI-Schemateil benennt den Transportmechanismus, der zum Erreichen der Adresse verwendet wird, z.&#160;B. HTTP und TCP. Der hierarchische Teil des URI enthält einen eindeutigen Ort, dessen Format vom Transportmechanismus abhängt.  
  
 Die Endpunktadresse ermöglicht es, für jeden Endpunkt in einem Dienst eindeutige Endpunktadressen zu erstellen oder unter bestimmten Voraussetzungen eine Adresse für mehrere Endpunkte zu verwenden. Im folgenden Beispiel wird veranschaulicht, wie eine Adresse das HTTPS-Protokoll mit einem nicht standardmäßigen Anschluss verwendet:  
  
```  
HTTPS://cohowinery:8005/ServiceModelSamples/CalculatorService  
```  
  
 Bindung  
 Definiert, wie ein Endpunkt mit der Umgebung kommuniziert. Sie besteht aus einer Reihe von Komponenten namens "Bindungselemente", die als Kommunikationsinfrastruktur aufeinander "gestapelt" werden. Eine Bindung definiert zumindest das Transportprotokoll (z.&#160;B. HTTP oder TCP) und die verwendete Codierung (z.&#160;B. Text oder binär). Eine Bindung kann Bindungselemente enthalten, die Details wie die Sicherheitsmechanismen zum Schützen von Nachrichten oder das von einem Endpunkt verwendete Nachrichtenmuster angeben. Weitere Informationen finden Sie unter [Configuring Services](../../../docs/framework/wcf/configuring-services.md).  
  
 Bindungselement (binding element)  
 Stellt einen bestimmten Teil der Bindung dar, z. B. einen Transport, eine Codierung, eine Implementierung eines Protokolls auf Infrastrukturebene (z. B. WS-ReliableMessaging) oder eine andere Komponente des Kommunikationsstapels.  
  
 Verhalten  
 Eine Komponente, die verschiedene Laufzeitaspekte eines Diensts, eines Endpunkts, eines bestimmten Vorgangs oder eines Clients steuert. Verhalten werden gemäß ihrem Umfang gruppiert: allgemeine Verhalten, die alle Endpunkte global beeinflussen, Dienstverhalten, die nur dienstbezogene Aspekte beeinflussen, Endpunktverhalten, die nur endpunktbezogene Eigenschaften beeinflussen, und Verhalten auf Vorgangsebene, die bestimmte Vorgänge beeinflussen. Eines der Dienstverhalten ist beispielsweise die Drosselung, die festlegt, wie ein Dienst reagiert, wenn zu viele Nachrichten seine Abwicklungskapazitäten zu überlasten drohen. Ein Endpunktverhalten steuert wiederum nur Aspekte, die für Endpunkte relevant sind, u. a. wie und wo eine Sicherheitsanmeldeinformation zu finden ist.  
  
 Vom System bereitgestellte Bindungen (system-provided bindings)  
 WCF bietet einige vom System bereitgestellte Bindungen. Dies sind Auflistungen von Bindungselementen, die für bestimmte Szenarien optimiert werden. <xref:System.ServiceModel.WSHttpBinding> ist beispielsweise für die Interoperabilität mit Diensten vorgesehen, die verschiedene WS-*-Spezifikationen implementieren. Diese vordefinierten Bindungen sparen Zeit, da sie nur diejenigen Optionen bereitstellen, die auf das spezifische Szenario korrekt angewendet werden können. Wenn eine vordefinierte Bindung die Anforderungen nicht erfüllt, können Sie eine eigene benutzerdefinierte Bindung erstellen.  
  
 Konfiguration gegen Codierung  
 Eine Anwendung kann entweder über die Codierung, über die Konfiguration oder über eine Kombination aus beidem gesteuert werden. Die Konfiguration bietet den Vorteil, dass auch andere Personen als der Entwickler (z.&#160;B. ein Netzwerkadministrator) die Client- und die Dienstparameter festlegen können, nachdem der Code geschrieben wurde, ohne dass eine neue Kompilierung erforderlich wäre. Die Konfiguration ermöglicht nicht nur das Festlegen von Werten wie Endpunktadressen, sondern auch eine weitere Steuerung durch die Möglichkeit, Endpunkte, Bindungen und Verhalten hinzuzufügen. Die Codierung ermöglicht es dem Entwickler, die genaue Kontrolle über alle Komponenten des Diensts oder Clients zu behalten, und alle Einstellungen, die über die Konfiguration gemacht werden, können überprüft und bei Bedarf vom Code aufgehoben werden.  
  
 Dienstvorgang  
 Ein Ablauf, der im Code eines Diensts definiert ist und der die Funktionalität für einen Vorgang implementiert. Dieser Vorgang wird anderen Clients in Form von Methoden auf einem WCF-Client verfügbar gemacht. Diese Methode kann einen Wert zurückgeben und eine optionale Anzahl an Argumenten übernehmen, oder sie kann keine Argumente übernehmen und keine Antwort zurückgeben. Beispielsweise kann ein Vorgang, der als ein einfaches "Hallo" fungiert, als Benachrichtigung über die Präsenz eines Clients und zum Starten einer Reihe von Vorgängen verwendet werden.  
  
 Dienstvertrag (service contract)  
 Verknüpft mehrere verwandte Vorgänge zu einer einzigen Funktionseinheit. Der Vertrag kann Einstellungen auf Dienstebene definieren, z.&#160;B. den Namespace des Diensts, einen entsprechenden Rückrufvertrag und andere derartige Einstellungen. In den meisten Fällen wird der Vertrag definiert, indem eine Schnittstelle in der gewünschten Programmiersprache erstellt wird und das Attribut <xref:System.ServiceModel.ServiceContractAttribute> auf die Schnittstelle angewendet wird. Der tatsächliche Dienstcode ergibt sich aus der Implementierung der Schnittstelle.  
  
 Vorgangsvertrag (operation contract)  
 Ein Vorgangsvertrag definiert die Parameter und den Rückgabetyp eines Vorgangs. Beim Erstellen einer Schnittstelle, die den Dienstvertrag definiert, wird ein Vorgangsvertrag angegeben, indem das Attribut <xref:System.ServiceModel.OperationContractAttribute> auf jede Methodendefinition angewendet wird, die Teil des Vertrags ist. Die Vorgänge können so gestaltet werden, dass sie eine einzelne Nachricht annehmen und eine einzelne Nachricht zurückgeben oder dass sie einen Typensatz annehmen und einen Typ zurückgeben. Im letzteren Fall bestimmt das System das Format der Nachrichten, die für diesen Vorgang ausgetauscht werden müssen.  
  
 Nachrichtenvertrag  
 Beschreibt das Format einer Nachricht. Er erklärt beispielsweise, ob Nachrichtenelemente in Header oder in den Text gehören, welches Sicherheitsniveau auf welche Elemente der Nachricht angewendet werden soll usw.  
  
 Fehlervertrag (fault contract)  
 Kann einem Dienstvorgang zugeordnet werden, um Fehler anzumerken, die dem Anrufer zurückgegeben werden können. Einem Vorgang können keine oder mehrere Fehler zugeordnet werden. Diese Fehler sind SOAP-Fehler, die als Ausnahmen im Programmiermodell erstellt werden.  
  
 Datenvertrag  
 Die Beschreibungen in Metadaten der Datentypen, die von einem Dienst verwendet werden. Dies ermöglicht die Interoperation mit dem Dienst. Die Datentypen können in einem beliebigen Teil der Nachricht verwendet werden, z. B. als Parameter oder Rückgabetypen. Wenn der Dienst nur einfache Typen verwendet, ist es nicht erforderlich, unbedingt Datenverträge zu verwenden.  
  
 Hosting  
 Ein Dienst muss in einem Prozess gehostet werden. Ein *Host* ist eine Anwendung, die die Lebensdauer des Diensts kontrolliert. Dienste können selbst gehostet werden oder durch einen vorhandenen Hostingprozess verwaltet werden.  
  
 Lokal gehosteter Dienst  
 Ein Dienst, der innerhalb einer vom Entwickler erstellten Prozessanwendung ausgeführt wird. Der Entwickler kontrolliert seine Lebensdauer, legt die Eigenschaften des Diensts fest, öffnet den Dienst (wodurch dieser in einen Überwachungsmodus versetzt wird) und schließt den Dienst.  
  
 Hostingprozess  
 Eine zum Hosten von Diensten entwickelte Anwendung. Dazu gehören Internetinformationsdienste (IIS), Windows Activation Services (WAS) und Windows-Dienste. In diesen gehosteten Szenarien kontrolliert der Host die Lebensdauer des Diensts. Mit IIS kann beispielsweise ein virtuelles Verzeichnis eingerichtet werden, das die Assembly- und die Konfigurationsdatei des Diensts enthält. Wenn eine Nachricht empfangen wird, startet IIS den Dienst und kontrolliert seine Lebensdauer.  
  
 Instanziierung  
 Ein Dienst verfügt über ein Instanziierungsmodell. Es gibt drei Instanziierungsmodelle: "einzeln", bei dem ein einzelnes CLR-Objekt alle Clients bedient; "pro Anruf", bei dem ein neues CLR-Objekt erstellt wird, um jeden Client-Anruf abzuarbeiten; und "pro Sitzung", bei dem ein Satz von CLR-Objekten erstellt wird – einer für jede einzelne Sitzung. Die Wahl des Instanziierungsmodells hängt von den Anwendungsanforderungen und dem erwarteten Nutzungsmuster des Diensts ab.  
  
 Clientanwendung (client application)  
 Ein Programm, das Nachrichten mit einem oder mehreren Endpunkten austauscht. Die Clientanwendung beginnt mit der Erstellung einer Instanz eines WCF-Clients und dem Aufrufen von Methoden des WCF-Clients. Es sollte beachtet werden, dass eine einzelne Anwendung sowohl ein Client als auch ein Dienst sein kann.  
  
 Kanal (channel)  
 Ein konkrete Implementierung eines Bindungselements. Die Bindung stellt die Konfiguration dar, und der Kanal ist die Implementierung, die mit dieser Konfiguration verknüpft ist. Deshalb ist jedem Bindungselement ein Kanal zugeordnet. Kanäle werden übereinander gestapelt, um die konkrete Implementierung der Bindung zu erstellen: den Kanalstapel.  
  
 WCF-Client (WCF client)  
 Ein Clientanwendungskonstrukt, das die Dienstvorgänge als Methoden verfügbar macht (in der gewünschten [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]-Programmiersprache, u. a. Visual Basic oder Visual C#). Jede Anwendung kann einen WCF-Client hosten, einschließlich einer Anwendung, die einen Dienst hostet. Deshalb ist es möglich, einen Dienst zu erstellen, der WCF-Clients anderer Dienste einschließt.  
  
 Ein WCF-Client kann automatisch generiert werden, mithilfe der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) und verweisen auf einen ausgeführten Dienst, der Metadaten veröffentlicht.  
  
 Metadaten  
 In einem Dienst werden von Metadaten die Merkmale des Diensts beschrieben, die eine externe Entität zur Kommunikation mit dem Dienst verstehen muss. Metadaten kann genutzt werden, indem die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) zum Generieren einer WCF-Client und eine dazugehörige Konfiguration, die eine Clientanwendung zur Interaktion mit dem Dienst verwenden können.  
  
 Zu den vom Dienst verfügbar gemachten Metadaten gehören XML-Schemadokumente, die den Datenvertrag des Diensts definieren, und WSDL-Dokumente, die die Methoden des Diensts beschreiben.  
  
 Bei Aktivierung werden die Metadaten für den Dienst automatisch von WCF erstellt, indem der Dienst und seine Endpunkte überprüft werden. Zum Veröffentlichen von Metadaten von einem Dienst aus müssen Sie das Metadatenverhalten explizit aktivieren.  
  
 Sicherheit  
 In WCF gehören Vertraulichkeit (Verschlüsselung von Nachrichten zum Verhindern von Lauschangriffen), Integrität (Erkennung von Manipulation der Nachricht), (das bedeutet, dass für die Validierung von Servern und Clients)-Authentifizierung und Autorisierung (Kontrolle des Zugriffs auf Ressourcen). Diese Funktionen werden entweder durch die Nutzung vorhandener Sicherheitsmechanismen wie TLS über HTTP (auch als "HTTPS" bekannt) oder durch die Implementierung von verschiedenen WS-*-Sicherheitsspezifikationen geboten.  
  
 Transportsicherheitsmodus  
 Legt fest, dass Vertraulichkeit, Integrität und Authentifizierung über die Transportschichtmechanismen (wie HTTPS) gewährleistet werden. Bei Nutzung eines Transports wie HTTPS hat dieser Modus den Vorteil, dass er effizient und aufgrund seiner weiten Verbreitung im Internet gut verständlich ist. Der Nachteil ist, dass diese Art von Sicherheit auf jeden Hop im Kommunikationspfad einzeln angewendet wird, was die Kommunikation anfällig für einen Man-In-The-Middle-Angriff (MITM-Angriff, Janusangriff) macht.  
  
 Nachrichtensicherheitsmodus  
 Gibt an, dass Sicherheit durch die Implementierung einer oder mehrerer der Sicherheitsspezifikationen bereitgestellt wird, wie z. B. die Spezifikation, mit dem Namen [Web Services Security: SOAP-Nachrichtensicherheit](https://go.microsoft.com/fwlink/?LinkId=94684). Jede Nachricht enthält die erforderlichen Mechanismen, um während ihrer Übertragung Sicherheit zu gewährleisten, und um den Empfängern die Möglichkeit zu bieten, Manipulationen zu erkennen und die Nachrichten zu entschlüsseln. So ist die Sicherheit in jeder einzelnen Nachricht integriert, sodass End-to-End-Sicherheit über mehrere Hops gewährleistet ist. Da Sicherheitsinformationen Teil der Nachricht ist, es ist auch möglich, mehrere Arten von Anmeldeinformationen in die Nachricht aufzunehmen (diese werden als bezeichnet *Ansprüche*). Dieser Ansatz hat außerdem den Vorteil, dass die Nachricht sicher über jeden Transport übermittelt werden kann, u.&#160;a. auch über mehrere Transporte zwischen Ursprungs- und Zielort. Der Nachteil dieses Ansatzes ist die Komplexität der eingesetzten kryptografischen Mechanismen, die zu Leistungsbeeinträchtigungen führen.  
  
 Modus "Transport mit Nachrichtenanmeldeinformationen"  
 Gibt die Verwendung der Transportschicht an, um Vertraulichkeit, Authentifizierung und Integrität der Nachrichten sicherzustellen, während jede der Nachrichten mehrere Anmeldeinformationen (Ansprüche) enthalten kann, die von den Empfängern der Nachricht benötigt werden.  
  
 WS-*  
 Kurzform für die ständig steigende Zahl von Web Service (WS)-Spezifikationen wie WS-Sicherheit, WS-ReliableMessaging usw., die in WCF implementiert sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Was ist die Windows Communication Foundation?](../../../docs/framework/wcf/whats-wcf.md)  
 [Windows Communication Foundation-Architektur](../../../docs/framework/wcf/architecture.md)  
 [Sicherheitsarchitektur](https://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)

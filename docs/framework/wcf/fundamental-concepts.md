---
title: Wesentliche Windows Communication Foundation-Begriffe
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], concepts
- concepts [WCF]
- fundamentals [WCF]
- Windows Communication Foundation [WCF], concepts
ms.assetid: 3e7e0afd-7913-499d-bafb-eac7caacbc7a
ms.openlocfilehash: 360479a2ba17c4542d61a737856d23992296e276
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802316"
---
# <a name="fundamental-windows-communication-foundation-concepts"></a>Wesentliche Windows Communication Foundation-Begriffe

Dieses Dokument bietet einen Überblick über die Windows Communication Foundation (WCF)-Architektur. Es ist dafür vorgesehen, Hauptkonzepte zu erklären und zu erläutern, wie diese zusammenpassen. Ein Tutorial zum Erstellen der einfachsten Version eines WCF-Dienstanbieter und-Clients finden Sie im [Tutorial zu](getting-started-tutorial.md)den ersten Schritten. Informationen zur WCF-Programmierung finden Sie unter [grundlegende WCF-Programmierung](basic-wcf-programming.md).

## <a name="wcf-fundamentals"></a>Grundlagen von WCF

WCF ist eine Laufzeit und ein Satz von APIs zum Erstellen von Systemen, die Nachrichten zwischen Diensten und Clients senden. Die gleiche Infrastruktur und die gleichen APIs werden verwendet, um Anwendungen zu erstellen, die mit anderen Anwendungen im gleichen Computersystem oder in einem System kommunizieren, das in einem anderen Unternehmen besteht und auf das über das Internet zugegriffen wird.

### <a name="messaging-and-endpoints"></a>Messaging und Endpunkte

WCF basiert auf dem Konzept der Nachrichten basierten Kommunikation, und alle Elemente, die als Nachricht modelliert werden können (z. b. eine HTTP-Anforderung oder eine Message Queuing (auch bekannt als MSMQ-Nachricht), können im Programmiermodell auf einheitliche Weise dargestellt werden. Dies ermöglicht eine einheitliche API über verschiedene Transportmechanismen hinweg.

Das Modell unterscheidet zwischen _Clients_, bei denen es sich um Anwendungen handelt, von denen die Kommunikation initiiert wird, und von _Diensten_, bei denen es sich um Anwendungen handelt, die auf die Kommunikation zwischen Clients und deren Reaktion warten Eine einzelne Anwendung kann sowohl als Client als auch als Dienst fungieren. Beispiele hierzu finden Sie unter [Duplex Dienste](./feature-details/duplex-services.md) und [Peer-to-Peer-Netzwerke](./feature-details/peer-to-peer-networking.md).

Nachrichten werden zwischen Endpunkten versendet. _Endpunkte_ sind Orte, an denen Nachrichten gesendet oder empfangen werden (oder beides), und Sie definieren alle Informationen, die für den Nachrichtenaustausch benötigt werden. Ein Dienst macht einen oder mehrere Anwendungsendpunkte verfügbar (ebenso wie keinen oder mehrere Infrastrukturendpunkte), und der Client erstellt einen Endpunkt, der mit einem der Endpunkte des Diensts kompatibel ist.

Ein _Endpunkt_ beschreibt auf eine Standard basierte Weise, an die Nachrichten gesendet werden sollen, wie Sie gesendet werden sollen und wie die Nachrichten aussehen sollten. Ein Dienst kann diese Informationen als Metadaten verfügbar machen, die Clients verarbeiten können, um geeignete WCF-Clients und Kommunikations _Stapel_zu generieren.

### <a name="communication-protocols"></a>Kommunikationsprotokolle

Ein erforderliches Element des Kommunikations Stapels ist das _Transportprotokoll_. Nachrichten können über Intranets und das Internet mithilfe von allgemein gebräuchlichen Transportprotokollen, z. B. HTTP und TCP, gesendet werden. Es bestehen noch weitere Transporte, die eine Kommunikation mit Message Queuing-Anwendungen und mit Knoten in einem Peer Networking-Netz unterstützen. Weitere Transportmechanismen können mit den integrierten Erweiterungs Punkten von WCF hinzugefügt werden.

Ein anderes erforderliches Element des Kommunikationsstapels ist die Codierung, die angibt, wie jede Nachricht formatiert ist. WCF stellt die folgenden Codierungen bereit:

- Textcodierung, eine interoperable Codierung.

- Message Transmission Optimization Mechanism (MTOM)-Codierung, eine interoperable Möglichkeit, unstrukturierte Binärdaten effizient an einem und von einem Dienst zu senden.

- Binäre Codierung für effiziente Übertragung.

Weitere Codierungs Mechanismen (z. b. eine Komprimierungs Codierung) können mit den integrierten Erweiterungs Punkten von WCF hinzugefügt werden.

### <a name="message-patterns"></a>Messagingmuster

WCF unterstützt mehrere Messaging Muster, einschließlich Anforderungs-/Antwort-, unidirektionaler und Duplex Kommunikation. Verschiedene Transporte unterstützen verschiedene Messagingmuster und beeinflussen so die Interaktionstypen, die sie unterstützen. Die WCF-APIs und-Laufzeit helfen Ihnen auch, Nachrichten sicher und zuverlässig zu senden.

## <a name="wcf-terms"></a>WCF-Begriffe

Weitere Konzepte und Begriffe, die in der WCF-Dokumentation verwendet werden, umfassen Folgendes:

**Meldung**  
 Eine eigenständige Dateneinheit, die aus mehreren Teilen bestehen kann, unter anderem aus Text und Headern.

**Dienst**  
 Ein Konstrukt, das einen oder mehrere Endpunkte verfügbar macht, wobei jeder Endpunkt wiederum einen oder mehrere Dienstvorgänge verfügbar macht.

**Endpunkt**  
 Ein Konstrukt, von dem Nachrichten gesendet oder empfangen werden (oder beides). Er umfasst einen Speicherort (eine Adresse), der definiert, wohin die Nachrichten gesendet werden können, eine Spezifikation des Kommunikationsmechanismus (eine Bindung), der beschreibt, wie Nachrichten gesendet werden sollen, sowie eine Definition für eine Reihe von Nachrichten, die an dieser Stelle gesendet oder empfangen werden können (oder beides). Speicherort (ein Dienstvertrag), der beschreibt, welche Nachricht gesendet werden kann.

Ein WCF-Dienst wird allgemein als eine Auflistung von Endpunkten verfügbar gemacht.

**Anwendungs Endpunkt**  
 Ein von der Anwendung verfügbar gemachter Endpunkt, der einem Dienstvertrag entspricht, der von der Anwendung implementiert wurde.

**Infrastruktur Endpunkt**  
 Ein Endpunkt, der von der Infrastruktur verfügbar gemacht wird, um Funktionalitäten zu erleichtern, die vom Dienst benötigt oder bereitgestellt werden, der sich nicht auf einen Dienstvertrag bezieht. Ein Dienst könnte z. B. einen Infrastrukturendpunkt aufweisen, der Metadateninformationen bereitstellt.

**Address**  
 Gibt den Speicherort an, an dem Nachrichten empfangen werden. Sie wird als ein Uniform Resource Identifier (URI) angegeben. Der URI-Schemateil benennt den Transportmechanismus, der zum Erreichen der Adresse verwendet wird, z.&#160;B. HTTP und TCP. Der hierarchische Teil des URI enthält einen eindeutigen Ort, dessen Format vom Transportmechanismus abhängt.

Die Endpunktadresse ermöglicht es, für jeden Endpunkt in einem Dienst eindeutige Endpunktadressen zu erstellen oder unter bestimmten Voraussetzungen eine Adresse für mehrere Endpunkte zu verwenden. Im folgenden Beispiel wird veranschaulicht, wie eine Adresse das HTTPS-Protokoll mit einem nicht standardmäßigen Anschluss verwendet:

```http
HTTPS://cohowinery:8005/ServiceModelSamples/CalculatorService
```

**Bindung**  
 Definiert, wie ein Endpunkt mit der Umgebung kommuniziert. Sie besteht aus einer Reihe von Komponenten namens "Bindungselemente", die als Kommunikationsinfrastruktur aufeinander "gestapelt" werden. Eine Bindung definiert zumindest das Transportprotokoll (z.&#160;B. HTTP oder TCP) und die verwendete Codierung (z.&#160;B. Text oder binär). Eine Bindung kann Bindungselemente enthalten, die Details wie die Sicherheitsmechanismen zum Schützen von Nachrichten oder das von einem Endpunkt verwendete Nachrichtenmuster angeben. Weitere Informationen finden Sie unter [Konfigurieren von Diensten](configuring-services.md).

**Binding-Element**  
 Stellt einen bestimmten Teil der Bindung dar, z. B. einen Transport, eine Codierung, eine Implementierung eines Protokolls auf Infrastrukturebene (z. B. WS-ReliableMessaging) oder eine andere Komponente des Kommunikationsstapels.

**Verhalten**  
 Eine Komponente, die verschiedene Laufzeitaspekte eines Diensts, eines Endpunkts, eines bestimmten Vorgangs oder eines Clients steuert. Verhalten werden gemäß ihrem Umfang gruppiert: allgemeine Verhalten, die alle Endpunkte global beeinflussen, Dienstverhalten, die nur dienstbezogene Aspekte beeinflussen, Endpunktverhalten, die nur endpunktbezogene Eigenschaften beeinflussen, und Verhalten auf Vorgangsebene, die bestimmte Vorgänge beeinflussen. Eines der Dienstverhalten ist beispielsweise die Drosselung, die festlegt, wie ein Dienst reagiert, wenn zu viele Nachrichten seine Abwicklungskapazitäten zu überlasten drohen. Ein Endpunktverhalten steuert wiederum nur Aspekte, die für Endpunkte relevant sind, u. a. wie und wo eine Sicherheitsanmeldeinformation zu finden ist.

**Vom System bereitgestellte Bindungen**  
 WCF bietet einige vom System bereitgestellte Bindungen. Dies sind Auflistungen von Bindungselementen, die für bestimmte Szenarien optimiert werden. Beispielsweise ist der <xref:System.ServiceModel.WSHttpBinding> für die Interoperabilität mit Diensten vorgesehen, die verschiedene WS-\* Spezifikationen implementieren. Diese vordefinierten Bindungen sparen Zeit, da sie nur diejenigen Optionen bereitstellen, die auf das spezifische Szenario korrekt angewendet werden können. Wenn eine vordefinierte Bindung die Anforderungen nicht erfüllt, können Sie eine eigene benutzerdefinierte Bindung erstellen.

**Konfiguration und Codierung**  
 Eine Anwendung kann entweder über die Codierung, über die Konfiguration oder über eine Kombination aus beidem gesteuert werden. Die Konfiguration bietet den Vorteil, dass auch andere Personen als der Entwickler (z.&#160;B. ein Netzwerkadministrator) die Client- und die Dienstparameter festlegen können, nachdem der Code geschrieben wurde, ohne dass eine neue Kompilierung erforderlich wäre. Die Konfiguration ermöglicht nicht nur das Festlegen von Werten wie Endpunktadressen, sondern auch eine weitere Steuerung durch die Möglichkeit, Endpunkte, Bindungen und Verhalten hinzuzufügen. Die Codierung ermöglicht es dem Entwickler, die genaue Kontrolle über alle Komponenten des Diensts oder Clients zu behalten, und alle Einstellungen, die über die Konfiguration gemacht werden, können überprüft und bei Bedarf vom Code aufgehoben werden.

**Dienst Vorgang**  
 Ein Ablauf, der im Code eines Diensts definiert ist und der die Funktionalität für einen Vorgang implementiert. Dieser Vorgang wird anderen Clients in Form von Methoden auf einem WCF-Client verfügbar gemacht. Diese Methode kann einen Wert zurückgeben und eine optionale Anzahl an Argumenten übernehmen, oder sie kann keine Argumente übernehmen und keine Antwort zurückgeben. Beispielsweise kann ein Vorgang, der als ein einfaches "Hallo" fungiert, als Benachrichtigung über die Präsenz eines Clients und zum Starten einer Reihe von Vorgängen verwendet werden.

**Dienstvertrag**  
 Verknüpft mehrere verwandte Vorgänge zu einer einzigen Funktionseinheit. Der Vertrag kann Einstellungen auf Dienstebene definieren, z.&#160;B. den Namespace des Diensts, einen entsprechenden Rückrufvertrag und andere derartige Einstellungen. In den meisten Fällen wird der Vertrag definiert, indem eine Schnittstelle in der gewünschten Programmiersprache erstellt wird und das Attribut <xref:System.ServiceModel.ServiceContractAttribute> auf die Schnittstelle angewendet wird. Der tatsächliche Dienstcode ergibt sich aus der Implementierung der Schnittstelle.

**Vorgangs Vertrag**  
 Ein Vorgangsvertrag definiert die Parameter und den Rückgabetyp eines Vorgangs. Beim Erstellen einer Schnittstelle, die den Dienstvertrag definiert, wird ein Vorgangsvertrag angegeben, indem das Attribut <xref:System.ServiceModel.OperationContractAttribute> auf jede Methodendefinition angewendet wird, die Teil des Vertrags ist. Die Vorgänge können so gestaltet werden, dass sie eine einzelne Nachricht annehmen und eine einzelne Nachricht zurückgeben oder dass sie einen Typensatz annehmen und einen Typ zurückgeben. Im letzteren Fall bestimmt das System das Format der Nachrichten, die für diesen Vorgang ausgetauscht werden müssen.

**Nachrichten Vertrag**  
 Beschreibt das Format einer Nachricht. Er erklärt beispielsweise, ob Nachrichtenelemente in Header oder in den Text gehören, welches Sicherheitsniveau auf welche Elemente der Nachricht angewendet werden soll usw.

**Fehler Vertrag**  
 Kann einem Dienstvorgang zugeordnet werden, um Fehler anzumerken, die dem Anrufer zurückgegeben werden können. Einem Vorgang können keine oder mehrere Fehler zugeordnet werden. Diese Fehler sind SOAP-Fehler, die als Ausnahmen im Programmiermodell erstellt werden.

**Datenvertrag**  
 Die Beschreibungen in Metadaten der Datentypen, die von einem Dienst verwendet werden. Dies ermöglicht die Interoperation mit dem Dienst. Die Datentypen können in einem beliebigen Teil der Nachricht verwendet werden, z. B. als Parameter oder Rückgabetypen. Wenn der Dienst nur einfache Typen verwendet, ist es nicht erforderlich, unbedingt Datenverträge zu verwenden.

**Hosting**  
 Ein Dienst muss in einem Prozess gehostet werden. Ein _Host_ ist eine Anwendung, die die Lebensdauer des Diensts steuert. Dienste können selbst gehostet werden oder durch einen vorhandenen Hostingprozess verwaltet werden.

**Selbstgeh ostete Dienste**  
 Ein Dienst, der innerhalb einer vom Entwickler erstellten Prozessanwendung ausgeführt wird. Der Entwickler kontrolliert seine Lebensdauer, legt die Eigenschaften des Diensts fest, öffnet den Dienst (wodurch dieser in einen Überwachungsmodus versetzt wird) und schließt den Dienst.

**Hostingprozess**  
 Eine zum Hosten von Diensten entwickelte Anwendung. Dazu gehören Internetinformationsdienste (IIS), Windows Activation Services (WAS) und Windows-Dienste. In diesen gehosteten Szenarien kontrolliert der Host die Lebensdauer des Diensts. Mit IIS kann beispielsweise ein virtuelles Verzeichnis eingerichtet werden, das die Assembly- und die Konfigurationsdatei des Diensts enthält. Wenn eine Nachricht empfangen wird, startet IIS den Dienst und kontrolliert seine Lebensdauer.

**Instanziierung**  
 Ein Dienst verfügt über ein Instanziierungsmodell. Es gibt drei Instanziierungsmodelle: "einzeln", bei dem ein einzelnes CLR-Objekt alle Clients bedient; "pro Anruf", bei dem ein neues CLR-Objekt erstellt wird, um jeden Client-Anruf abzuarbeiten; und "pro Sitzung", bei dem ein Satz von CLR-Objekten erstellt wird – einer für jede einzelne Sitzung. Die Wahl des Instanziierungsmodells hängt von den Anwendungsanforderungen und dem erwarteten Nutzungsmuster des Diensts ab.

**Client Anwendung**  
 Ein Programm, das Nachrichten mit einem oder mehreren Endpunkten austauscht. Die Clientanwendung beginnt mit der Erstellung einer Instanz eines WCF-Clients und dem Aufrufen von Methoden des WCF-Clients. Es sollte beachtet werden, dass eine einzelne Anwendung sowohl ein Client als auch ein Dienst sein kann.

**Kanal**  
 Ein konkrete Implementierung eines Bindungselements. Die Bindung stellt die Konfiguration dar, und der Kanal ist die Implementierung, die mit dieser Konfiguration verknüpft ist. Deshalb ist jedem Bindungselement ein Kanal zugeordnet. Kanäle werden übereinander gestapelt, um die konkrete Implementierung der Bindung zu erstellen: den Kanalstapel.

**WCF-Client**  
 Ein Client Anwendungs Konstrukt, das die Dienst Vorgänge als Methoden verfügbar macht (in der .NET Framework Programmiersprache Ihrer Wahl, z. b. Visual Basic C#oder Visual). Jede Anwendung kann einen WCF-Client hosten, einschließlich einer Anwendung, die einen Dienst hostet. Deshalb ist es möglich, einen Dienst zu erstellen, der WCF-Clients anderer Dienste einschließt.

Ein WCF-Client kann automatisch mit dem [Service Model Metadata Utility-Tool (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) generiert und auf einen laufenden Dienst verwiesen werden, der Metadaten veröffentlicht.

**Metadaten**  
 In einem Dienst werden von Metadaten die Merkmale des Diensts beschrieben, die eine externe Entität zur Kommunikation mit dem Dienst verstehen muss. Metadaten können vom [Service Model Metadata Utility-Tool (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) genutzt werden, um einen WCF-Client und eine begleitende Konfiguration zu generieren, die eine Client Anwendung für die Interaktion mit dem Dienst verwenden kann.

Zu den vom Dienst verfügbar gemachten Metadaten gehören XML-Schemadokumente, die den Datenvertrag des Diensts definieren, und WSDL-Dokumente, die die Methoden des Diensts beschreiben.

Bei Aktivierung werden die Metadaten für den Dienst automatisch von WCF erstellt, indem der Dienst und seine Endpunkte überprüft werden. Zum Veröffentlichen von Metadaten von einem Dienst aus müssen Sie das Metadatenverhalten explizit aktivieren.

**Sicherheit**  
 In WCF enthält Vertraulichkeit (Verschlüsselung von Nachrichten zum Verhindern von lausch Angriffen), Integrität (die Mittel für die Erkennung von Manipulationen bei der Nachricht), Authentifizierung (die Methode zur Validierung von Servern und Clients) und Autorisierung (Kontrolle des Zugriffs auf Ressourcen). Diese Funktionen werden entweder durch die Nutzung vorhandener Sicherheitsmechanismen (z. b. TLS über HTTP (auch als HTTPS bezeichnet) oder durch Implementieren einer oder mehrerer der verschiedenen WS-\*-Sicherheitsspezifikationen bereitgestellt.

**Transport Sicherheitsmodus**  
 Legt fest, dass Vertraulichkeit, Integrität und Authentifizierung über die Transportschichtmechanismen (wie HTTPS) gewährleistet werden. Bei Nutzung eines Transports wie HTTPS hat dieser Modus den Vorteil, dass er effizient und aufgrund seiner weiten Verbreitung im Internet gut verständlich ist. Der Nachteil ist, dass diese Art von Sicherheit auf jeden Hop im Kommunikationspfad einzeln angewendet wird, was die Kommunikation anfällig für einen Man-In-The-Middle-Angriff (MITM-Angriff, Janusangriff) macht.

**Nachrichten Sicherheitsmodus**  
 Gibt an, dass die Sicherheit bereitgestellt wird, indem eine oder mehrere Sicherheitsspezifikationen implementiert werden, z. b. die Spezifikation mit dem Namen [Webdienstesicherheit: SOAP-Nachrichten Sicherheit](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf). Jede Nachricht enthält die erforderlichen Mechanismen, um während ihrer Übertragung Sicherheit zu gewährleisten, und um den Empfängern die Möglichkeit zu bieten, Manipulationen zu erkennen und die Nachrichten zu entschlüsseln. So ist die Sicherheit in jeder einzelnen Nachricht integriert, sodass End-to-End-Sicherheit über mehrere Hops gewährleistet ist. Da Sicherheitsinformationen Teil der Nachricht werden, ist es auch möglich, mehrere Arten von Anmelde Informationen mit der Nachricht aufzunehmen (diese werden als _Ansprüche_bezeichnet). Dieser Ansatz hat außerdem den Vorteil, dass die Nachricht sicher über jeden Transport übermittelt werden kann, u.&#160;a. auch über mehrere Transporte zwischen Ursprungs- und Zielort. Der Nachteil dieses Ansatzes ist die Komplexität der eingesetzten kryptografischen Mechanismen, die zu Leistungsbeeinträchtigungen führen.

**Transport mit Nachrichten Anmelde Informationen-Sicherheitsmodus**  
 Gibt die Verwendung der Transportschicht an, um Vertraulichkeit, Authentifizierung und Integrität der Nachrichten sicherzustellen, während jede der Nachrichten mehrere Anmeldeinformationen (Ansprüche) enthalten kann, die von den Empfängern der Nachricht benötigt werden.

**WS-\***  
 Kurzform für die ständig steigende Zahl von Web Service (WS)-Spezifikationen wie WS-Sicherheit, WS-ReliableMessaging usw., die in WCF implementiert sind.

## <a name="see-also"></a>Siehe auch

- [Was ist die Windows Communication Foundation?](whats-wcf.md)
- [Windows Communication Foundation-Architektur](architecture.md)

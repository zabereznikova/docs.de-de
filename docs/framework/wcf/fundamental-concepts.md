---
title: "Wesentliche Windows Communication Foundation-Begriffe | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Konzepte [WCF]"
  - "Grundlagen [WCF]"
  - "WCF [WCF], Konzepte"
  - "Windows Communication Foundation [WCF], Konzepte"
ms.assetid: 3e7e0afd-7913-499d-bafb-eac7caacbc7a
caps.latest.revision: 39
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 39
---
# Wesentliche Windows Communication Foundation-Begriffe
Dieses Dokument enthält eine Ansicht über die [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Architektur auf hoher Ebene.Es ist dafür vorgesehen, Hauptkonzepte zu erklären und zu erläutern, wie diese zusammenpassen.Ein Lernprogramm zum Erstellen der einfachsten Version eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensts und \-Clients finden Sie im [Lernprogramm 'Erste Schritte'](../../../docs/framework/wcf/getting-started-tutorial.md).Um mehr über die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Programmierung zu erfahren, lesen Sie [Basis\-WCF\-Programmierung](../../../docs/framework/wcf/basic-wcf-programming.md).  
  
## Grundlagen von WCF  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ist eine Laufzeit und ein Satz von APIs zum Erstellen von Systemen, die Nachrichten zwischen Diensten und Clients versenden.Die gleiche Infrastruktur und die gleichen APIs werden verwendet, um Anwendungen zu erstellen, die mit anderen Anwendungen im gleichen Computersystem oder in einem System kommunizieren, das in einem anderen Unternehmen besteht und auf das über das Internet zugegriffen wird.  
  
### Messaging und Endpunkte  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] basiert auf dem Konzept einer nachrichtenbasierten Kommunikation, und alle Objekte, die als Nachricht aufgebaut werden können \(z. B. eine HTTP\-Anfrage oder eine Message Queuing \(MSQM\)\-Nachricht\), können im Programmierungsmodell auf einheitliche Art dargestellt werden.Dies ermöglicht eine einheitliche API über verschiedene Transportmechanismen hinweg.  
  
 Das Modell unterscheidet zwischen *Clients*, also Anwendungen, die die Kommunikation initiieren, und *Diensten*, also Anwendungen, die auf die Kommunikation von Clients warten und darauf reagieren.Eine einzelne Anwendung kann sowohl als Client als auch als Dienst fungieren.Beispiele finden Sie unter [Duplexdienste](../../../docs/framework/wcf/feature-details/duplex-services.md) und [Peer\-to\-Peer\-Netzwerke](../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
 Nachrichten werden zwischen Endpunkten versendet.*Endpunkte* sind Orte, an denen Nachrichten empfangen oder gesendet werden \(oder beides\), und die alle Informationen definieren, die für den Nachrichtenaustausch benötigt werden.Ein Dienst macht einen oder mehrere Anwendungsendpunkte verfügbar \(ebenso wie keinen oder mehrere Infrastrukturendpunkte\), und der Client erstellt einen Endpunkt, der mit einem der Endpunkte des Diensts kompatibel ist.  
  
 Ein *Endpunkt* beschreibt auf eine standardbasierte Art, wo Nachrichten gesendet werden sollen, wie sie gesendet werden sollen und wie die Nachrichten aussehen sollen.Ein Dienst kann diese Informationen als Metadaten verfügbar machen, die Clients verarbeiten können, um entsprechende [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clients und Kommunikations*stapel* zu erstellen.  
  
### Kommunikationsprotokolle  
 Ein erforderliches Element des Kommunikationsstapels ist das *Transportprotokoll*.Nachrichten können über Intranets und das Internet mithilfe von allgemein gebräuchlichen Transportprotokollen, z. B. HTTP und TCP, gesendet werden.Es bestehen noch weitere Transporte, die eine Kommunikation mit Message Queuing\-Anwendungen und mit Knoten in einem Peer Networking\-Netz unterstützen.Weitere Transportmechanismen können über die integrierten Erweiterungspunkte von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] hinzugefügt werden.  
  
 Ein anderes erforderliches Element des Kommunikationsstapels ist die Codierung, die angibt, wie jede Nachricht formatiert ist.[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] stellt die folgenden Codierungen bereit:  
  
-   Textcodierung, eine interoperable Codierung.  
  
-   Message Transmission Optimization Mechanism \(MTOM\)\-Codierung, eine interoperable Möglichkeit, unstrukturierte Binärdaten effizient an einem und von einem Dienst zu senden.  
  
-   Binäre Codierung für effiziente Übertragung.  
  
 Mehr Codierungsmechanismen \(z. B. eine Komprimierungscodierung\) können mit den integrierten Erweiterungspunkten von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] hinzugefügt werden.  
  
### Messagingmuster  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] unterstützt mehrere Messagingmuster, einschließlich Anforderung\-Antwort\-, unidirektionale, und Duplexkommunikation.Verschiedene Transporte unterstützen verschiedene Messagingmuster und beeinflussen so die Interaktionstypen, die sie unterstützen.Die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-APIs und die \-Laufzeit helfen Ihnen auch, Nachrichten sicher und zuverlässig zu senden.  
  
## WCF\-Begriffe  
 Folgende andere Konzepte und Begriffe werden in der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dokumentation verwendet:  
  
 Nachricht  
 Eine eigenständige Dateneinheit, die aus mehreren Teilen bestehen kann, unter anderem aus Text und Headern.  
  
 Dienst  
 Ein Konstrukt, das einen oder mehrere Endpunkte verfügbar macht, wobei jeder Endpunkt wiederum einen oder mehrere Dienstvorgänge verfügbar macht.  
  
 Endpunkt  
 Ein Konstrukt, von dem Nachrichten gesendet oder empfangen werden \(oder beides\).Er besteht aus einem Speicherort \(einer Adresse\), mit dem definiert wird, wohin die Nachrichten gesendet werden können, einer Spezifikation des Kommunikationsmechanismus \(einer Bindung\), die beschreibt, wie die Nachrichten gesendet werden sollen, einer Definition eines Satzes von Nachrichten, die an diesen Ort gesendet oder dort empfangen werden können \(oder beides\) und aus einem Dienstvertrag, der beschreibt, welche Nachricht gesendet werden kann.  
  
 Ein [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst wird als Sammlung von Endpunkten verfügbar gemacht.  
  
 Anwendungsendpunkt  
 Ein von der Anwendung verfügbar gemachter Endpunkt, der einem Dienstvertrag entspricht, der von der Anwendung implementiert wurde.  
  
 Infrastrukturendpunkt  
 Ein Endpunkt, der von der Infrastruktur verfügbar gemacht wird, um Funktionalitäten zu erleichtern, die vom Dienst benötigt oder bereitgestellt werden, der sich nicht auf einen Dienstvertrag bezieht.Ein Dienst könnte z. B. einen Infrastrukturendpunkt aufweisen, der Metadateninformationen bereitstellt.  
  
 Adresse  
 Gibt den Speicherort an, an dem Nachrichten empfangen werden.Sie wird als ein Uniform Resource Identifier \(URI\) angegeben.Der URI\-Schemateil benennt den Transportmechanismus, der zum Erreichen der Adresse verwendet wird, z. B. HTTP und TCP.Der hierarchische Teil des URI enthält einen eindeutigen Ort, dessen Format vom Transportmechanismus abhängt.  
  
 Die Endpunktadresse ermöglicht es, für jeden Endpunkt in einem Dienst eindeutige Endpunktadressen zu erstellen oder unter bestimmten Voraussetzungen eine Adresse für mehrere Endpunkte zu verwenden.Im folgenden Beispiel wird veranschaulicht, wie von einer Adresse das HTTPS\-Protokoll mit einem nicht standardmäßigen Anschluss verwendet wird:  
  
```  
HTTPS://cohowinery:8005/ServiceModelSamples/CalculatorService  
```  
  
 Bindung  
 Definiert, wie ein Endpunkt mit der Umgebung kommuniziert.Sie besteht aus einer Reihe von Komponenten, den Bindungselementen, die als Kommunikationsinfrastruktur aufeinander "gestapelt" werden.Eine Bindung definiert zumindest das Transportprotokoll \(z. B. HTTP oder TCP\) und die verwendete Codierung \(z. B. Text oder binär\).Eine Bindung kann Bindungselemente enthalten, die Details wie die Sicherheitsmechanismen zum Schützen von Nachrichten oder das von einem Endpunkt verwendete Nachrichtenmuster angeben.Weitere Informationen finden Sie unter [Konfigurieren von Diensten](../../../docs/framework/wcf/configuring-services.md).  
  
 Bindungselement  
 Stellt einen bestimmten Teil der Bindung dar, z. B. einen Transport, eine Codierung, eine Implementierung eines Protokolls auf Infrastrukturebene \(z. B. WS\-ReliableMessaging\) oder eine andere Komponente des Kommunikationsstapels.  
  
 Verhalten  
 Eine Komponente, die verschiedene Laufzeitaspekte eines Diensts, eines Endpunkts, eines bestimmten Vorgangs oder eines Clients steuert.Verhalten werden gemäß ihrem Umfangs gruppiert: allgemeine Verhalten, die alle Endpunkte global beeinflussen; Dienstverhalten, die nur dienstbezogene Aspekte beeinflussen; Endpunktverhalten, die nur Endpunkt\-bezogene Eigenschaften beeinflussen; und Verhalten auf Vorgangsebene, die bestimmte Vorgänge beeinflussen.Eines der Dienstverhalten ist beispielsweise die Drosselung, die festlegt, wie ein Dienst reagiert, wenn zu viele Nachrichten seine Abwicklungskapazitäten zu überlasten drohen.Ein Endpunktverhalten steuert wiederum nur Aspekte, die für Endpunkte relevant sind, u. a. wie und wo eine Sicherheitsanmeldeinformation zu finden ist.  
  
 Vom System bereitgestellte Bindungen  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] bietet einige vom System bereitgestellte Bindungen.Dies sind Sammlungen von Bindungselementen, die für bestimmte Szenarien optimiert werden.<xref:System.ServiceModel.WSHttpBinding> ist beispielsweise für die Interoperabilität mit Diensten vorgesehen, die verschiedene WS\-\*\-Spezifikationen implementieren.Diese vordefinierten Bindungen sparen Zeit, da sie nur diejenigen Optionen bereitstellen, die auf das spezifische Szenario korrekt angewendet werden können.Wenn eine vordefinierte Bindung die Anforderungen nicht erfüllt, können Sie eine eigene benutzerdefinierte Bindung erstellen.  
  
 Konfiguration gegen Codierung  
 Eine Anwendung kann entweder über Codierung, Konfiguration oder eine Mischung aus beidem gesteuert werden.Die Konfiguration bietet den Vorteil, dass auch andere Personen als der Entwickler \(z. B. ein Netzwerkadministrator\) die Client\- und Dienstparameter einstellen können, nachdem der Code geschrieben wurde, ohne dass eine neue Kompilierung erforderlich wäre.Die Konfiguration ermöglicht nicht nur das Festlegen von Werten wie Endpunktadressen, sondern auch eine weitere Steuerung durch die Möglichkeit, Endpunkte, Bindungen und Verhalten hinzuzufügen.Die Codierung ermöglicht dem Entwickler, die genaue Kontrolle über alle Komponenten des Diensts oder Clients zu behalten, und alle Einstellungen, die über die Konfiguration gemacht werden, können überprüft und bei Bedarf vom Code aufgehoben werden.  
  
 Dienstvorgang  
 Ein Ablauf, der im Code eines Diensts definiert ist und der die Funktionalität für einen Vorgang implementiert.Dieser Vorgang wird anderen Clients auf einem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Client als Methode verfügbar gemacht.Diese Methode kann einen Wert zurückgeben und eine optionale Anzahl an Argumenten übernehmen, oder sie kann keine Argumente übernehmen und keine Antwort zurückgeben.Beispielsweise kann ein Vorgang, der als ein einfaches "Hallo" fungiert, als Benachrichtigung über die Präsenz eines Clients und zum Starten einer Reihe von Vorgängen verwendet werden.  
  
 Dienstvertrag  
 Verknüpft mehrere verwandte Vorgänge zu einer einzigen Funktionseinheit.Der Vertrag kann Einstellungen auf Dienstebene definieren, z. B. den Namespace des Diensts, einen entsprechenden Rückrufvertrag und andere derartige Einstellungen.In den meisten Fällen wird der Vertrag definiert, indem eine Schnittstelle in der gewünschten Programmiersprache erstellt wird und das Attribut <xref:System.ServiceModel.ServiceContractAttribute> auf die Schnittstelle angewendet wird.Der tatsächliche Dienstcode ergibt sich aus der Implementierung der Schnittstelle.  
  
 Vorgangsvertrag  
 Ein Vorgangsvertrag definiert die Parameter und den Rückgabetyp eines Vorgangs.Beim Erstellen einer Schnittstelle, die den Dienstvertrag definiert, wird ein Vorgangsvertrag angegeben, indem das Attribut <xref:System.ServiceModel.OperationContractAttribute> auf jede Methodendefinition angewendet wird, die Teil des Vertrags ist.Die Vorgänge können so gestaltet werden, dass sie eine einzelne Nachricht annehmen und eine einzelne Nachricht zurückgeben, oder dass sie einen Typensatz annehmen und einen Typ zurückgeben.Im letzteren Fall bestimmt das System das Format der Nachrichten, die für diesen Vorgang ausgetauscht werden müssen.  
  
 Nachrichtenvertrag  
 Beschreibt das Format einer Nachricht.Er legt beispielsweise fest, ob Nachrichtenelemente in Header oder in den Text gehören, welches Sicherheitsniveau auf welche Elemente der Nachricht angewendet werden soll usw.  
  
 Fehlervertrag  
 Kann einem Dienstvorgang zugeordnet werden, um Fehler anzumerken, die dem Anrufer zurückgegeben werden können.Einem Vorgang können keine oder mehrere Fehler zugeordnet werden.Diese Fehler sind SOAP\-Fehler, die als Ausnahmen im Programmiermodell erstellt werden.  
  
 Datenvertrag  
 Die Beschreibungen in Metadaten der Datentypen, die von einem Dienst verwendet werden.Dies ermöglicht die Interoperation mit dem Dienst.Die Datentypen können in einem beliebigen Teil der Nachricht verwendet werden, z. B. als Parameter oder Rückgabetypen.Wenn der Dienst nur einfache Typen verwendet, ist es nicht erforderlich, unbedingt Datenverträge zu verwenden.  
  
 Hosting  
 Ein Dienst muss in einem Prozess gehostet werden.Ein *Host* ist eine Anwendung, die die Lebensdauer des Diensts kontrolliert.Dienste können selbst gehostet oder von einem vorhandenen Hostingprozess verwaltet werden.  
  
 Selbst gehosteter Dienst  
 Ein Dienst, der innerhalb einer vom Entwickler erstellten Prozessanwendung ausgeführt wird.Der Entwickler kontrolliert seine Lebensdauer, legt die Eigenschaften des Diensts fest, öffnet den Dienst \(wodurch dieser in einen Überwachungsmodus versetzt wird\) und schließt den Dienst.  
  
 Hostingprozess  
 Eine zum Hosten von Diensten entwickelte Anwendung.Dazu gehören Internetinformationsdienste \(IIS\), Windows Activation Services \(WAS\) und Windows\-Dienste.In diesen gehosteten Szenarien kontrolliert der Host die Lebensdauer des Diensts.Mit IIS kann beispielsweise ein virtuelles Verzeichnis eingerichtet werden, das die Assembly\- und die Konfigurationsdatei des Diensts enthält.Wenn eine Nachricht empfangen wird, startet IIS den Dienst und kontrolliert seine Lebensdauer.  
  
 Instanziierung  
 Ein Dienst verfügt über ein Instanziierungsmodell.Es gibt drei Instanziierungsmodelle: "einzeln", bei dem ein einzelnes CLR\-Objekt alle Clients bedient; "pro Anruf", bei dem ein neues CLR\-Objekt erstellt wird, um jeden Client\-Anruf abzuarbeiten; und "pro Sitzung", bei dem ein Satz von CLR\-Objekten erstellt wird – einer für jede einzelne Sitzung.Die Wahl des Instanziierungsmodells hängt von den Anwendungsanforderungen und dem erwarteten Nutzungsmuster des Diensts ab.  
  
 Clientanwendung  
 Ein Programm, das Nachrichten mit einem oder mehreren Endpunkten austauscht.Die Clientanwendung beginnt mit der Erstellung einer Instanz eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clients und dem Aufrufen von Methoden des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clients.Wichtig: Eine einzelne Anwendung kann sowohl Client als auch Dienst sein.  
  
 Kanal  
 Ein konkrete Implementierung eines Bindungselements.Die Bindung stellt die Konfiguration dar, und der Kanal ist die Implementierung, die mit dieser Konfiguration verknüpft ist.Deshalb ist jedem Bindungselement ein Kanal zugeordnet.Kanäle werden übereinander gestapelt, um die konkrete Implementierung der Bindung zu erstellen: den Kanalstapel.  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Client  
 Ein Clientanwendungskonstrukt, das die Dienstvorgänge als Methoden verfügbar macht \(in der gewünschten [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]\-Programmiersprache, u. a. Visual Basic oder Visual C\#\).Jede Anwendung kann einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Client hosten, einschließlich einer Anwendung, die einen Dienst hostet.Deshalb ist es möglich, einen Dienst zu erstellen, der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clients anderer Dienste einschließt.  
  
 Ein [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Client kann automatisch über das [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) erstellt werden und auf einen ausgeführten Dienst verweisen, der Metadaten veröffentlicht.  
  
 Metadaten  
 In einem Dienst werden von Metadaten die Merkmale des Diensts beschrieben, die eine externe Entität zur Kommunikation mit dem Dienst verstehen muss.Metadaten können über das [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) verarbeitet werden, um einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Client und eine dazugehörige Konfiguration zu erstellen, die eine Clientanwendung zur Interaktion mit dem Dienst nutzen kann.  
  
 Zu den vom Dienst verfügbar gemachten Metadaten gehören XML\-Schemadokumente, die den Datenvertrag des Diensts definieren, und WSDL\-Dokumente, die die Methoden des Diensts beschreiben.  
  
 Bei Aktivierung werden die Metadaten für den Dienst automatisch von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] erstellt, indem der Dienst und seine Endpunkte überprüft werden.Zum Veröffentlichen von Metadaten von einem Dienst aus müssen Sie das Metadatenverhalten explizit aktivieren.  
  
 Sicherheit  
 In [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] gehören zur Sicherheit Vertraulichkeit \(Verschlüsselung von Nachrichten zum Verhindern von Lauschangriffen\), Integrität \(Erkennung manipulierter Nachrichten\), Authentifizierung \(Validierung von Servern und Clients\) und Autorisierung \(Kontrolle des Zugriffs auf Ressourcen\).Diese Funktionen werden entweder durch die Nutzung vorhandener Sicherheitsmechanismen wie TLS über HTTP \(auch als "HTTPS" bekannt\) oder durch die Implementierung von verschiedenen WS\-\*\-Sicherheitsspezifikationen geboten.  
  
 Transportsicherheitsmodus  
 Legt fest, dass Vertraulichkeit, Integrität und Authentifizierung über die Transportschichtmechanismen \(wie HTTPS\) gewährleistet werden.Bei Nutzung eines Transports wie HTTPS hat dieser Modus den Vorteil, dass er effizient und aufgrund seiner weiten Verbreitung im Internet gut verständlich ist.Der Nachteil ist, dass diese Art von Sicherheit auf jeden Hop im Kommunikationspfad einzeln angewendet wird, was die Kommunikation anfällig für einen Man\-In\-The\-Middle\-Angriff \(MITM\-Angriff, Janusangriff\) macht.  
  
 Nachrichtensicherheitsmodus  
 Gibt an, dass die Sicherheit durch die Implementierung mindestens einer Sicherheitsspezifikation gewährleistet wird, z. B. die [Webdienstsicherheit: SOAP\-Nachrichtensicherheit](http://go.microsoft.com/fwlink/?LinkId=94684)\-Spezifikation.Jede Nachricht enthält die erforderlichen Mechanismen, um die Sicherheit während ihrer Übertragung zu gewährleisten und um den Empfängern die Möglichkeit zu bieten, Manipulationen zu erkennen und die Nachrichten zu entschlüsseln.So ist die Sicherheit in jeder einzelnen Nachricht integriert, sodass End\-to\-End\-Sicherheit über mehrere Hops gewährleistet ist.Da Sicherheitsinformationen Teil der Nachricht werden, ist es außerdem möglich, mehrere Arten von Anmeldeinformationen in die Nachricht aufzunehmen \(diese werden als *Ansprüche* bezeichnet\).Dieser Ansatz hat außerdem den Vorteil, dass die Nachricht sicher über jeden Transport übermittelt werden kann, u. a. auch über mehrere Transporte zwischen Ursprungs\- und Zielort.Der Nachteil dieses Ansatzes ist die Komplexität der eingesetzten kryptografischen Mechanismen, die zu Leistungsbeeinträchtigungen führen.  
  
 Modus "Transport mit Nachrichtenanmeldeinformationen"  
 Gibt die Verwendung der Transportschicht an, um Vertraulichkeit, Authentifizierung und Integrität der Nachrichten sicherzustellen, während jede der Nachrichten mehrere Anmeldeinformationen \(Ansprüche\) enthalten kann, die von den Empfängern der Nachricht benötigt werden.  
  
 WS\-\*  
 Kurzform für die ständig steigende Zahl von Web Service \(WS\)\-Spezifikationen wie WS\-Sicherheit, WS\-ReliableMessaging usw., die in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] implementiert sind.  
  
## Siehe auch  
 [Was ist die Windows Communication Foundation?](../../../docs/framework/wcf/whats-wcf.md)   
 [Windows Communication Foundation\-Architektur](../../../docs/framework/wcf/architecture.md)   
 [Security Architecture](http://msdn.microsoft.com/de-de/16593476-d36a-408d-808c-ae6fd483e28f)
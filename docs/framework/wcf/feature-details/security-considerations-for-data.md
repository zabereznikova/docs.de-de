---
title: Sicherheitsüberlegungen zu Daten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a7eb98da-4a93-4692-8b59-9d670c79ffb2
ms.openlocfilehash: 8cb7ee2ea2418602d944c3c08cec2b9279dca3b9
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601061"
---
# <a name="security-considerations-for-data"></a>Sicherheitsüberlegungen zu Daten

Beim Umgang mit Daten in Windows Communication Foundation (WCF) müssen Sie eine Reihe von Bedrohungs Kategorien in Erwägung gezogen. In der folgenden Tabelle werden die wichtigsten Bedrohungskategorien der Datenverarbeitung aufgeführt. WCF bietet Tools, mit denen diese Bedrohungen minimiert werden können.

Ein Denial-of-Service-Vorgang beim Empfang nicht vertrauenswürdiger Daten kann dazu führen, dass die Empfängerseite auf eine unverhältnismäßig große Menge verschiedener Ressourcen wie Arbeitsspeicher, Threads, verfügbare Verbindungen oder Prozessor Zyklen zugreifen kann, indem lange Berechnungen durchgeführt werden. Ein Denial-of-Service-Angriff führt möglicherweise zum Absturz des Servers, wodurch er keine Nachrichten von anderen, legitimen Clients verarbeiten kann.

Eingehende nicht vertrauenswürdige Daten mit böswilliger Codeausführung bewirken, dass die empfangende Seite Code ausführen kann, der nicht beabsichtigt war.

Die Offenlegung von Informationen durch den Remote Angreifer zwingt die empfangende Partei, auf Ihre Anforderungen so zu reagieren, dass mehr Informationen als beabsichtigt offengelegt werden.

## <a name="user-provided-code-and-code-access-security"></a>Vom Benutzer bereitgestellter Code und Codezugriffssicherheit

An mehreren Stellen in der Windows Communication Foundation (WCF)-Infrastruktur wird Code ausgeführt, der vom Benutzer bereitgestellt wird. Die Serialisierungs-Engine <xref:System.Runtime.Serialization.DataContractSerializer> z. B. kann vom Benutzer bereitgestellte `set` - und `get` -Eigenschaftenaccessoren aufrufen. Von der WCF-Kanal Infrastruktur können auch vom Benutzer bereitgestellte abgeleitete Klassen der-Klasse aufgerufen werden <xref:System.ServiceModel.Channels.Message> .

Der Autor des Codes muss sicherstellen, dass kein Sicherheitsrisiko entsteht. Angenommen, Sie erstellen einen Datenvertragstyp mit einer Datenmembereigenschaft vom Typ Integer und ordnen in der Implementierung des `set` -Accessors basierend auf dem Eigenschaftswert ein Array zu. In diesem Fall setzen Sie den Server der Gefahr eines Denial-of-Service-Angriffs aus, wenn eine böswillige Nachricht einen extrem langen Wert für diesen Datenmember enthält. Vermeiden Sie in der Regel Zuordnungen, die auf eingehenden Daten oder langwierigen Verarbeitungen im Benutzercode basieren (insbesondere, wenn die langwierige Verarbeitung durch wenige eingehende Daten verursacht werden kann). Berücksichtigen Sie bei der Sicherheitsanalyse von Benutzercode auch alle möglichen Schwachstellen (d. h. alle Codeverzweigungen, an denen Ausnahmen ausgelöst werden).

Der Code, der sich innerhalb der Dienstimplementierung für die einzelnen Vorgänge befindet, ist das letzte Beispiel für Benutzercode. Für die Sicherheit Ihrer Dienstimplementierung sind Sie verantwortlich. Es kann leicht passieren, dass versehentlich unsichere Vorgänge implementiert werden, die das Risiko von Denial-of-Service-Angriffen mit sich bringen. Stellen Sie sich z.&#160;B. einen Vorgang vor, der anhand einer Zeichenfolge aus einer Datenbank eine Liste der Kunden zurückgibt, deren Name mit dieser Zeichenfolge beginnt. Wenn Sie mit großen Datenbanken arbeiten und die übergebene Zeichenfolge besteht nur aus einem einzelnen Buchstaben, ist die Nachricht, die der Code zu erstellen versucht, möglicherweise größer als der verfügbare Arbeitspeicher. Somit schlägt der gesamte Dienst fehl. (Ein <xref:System.OutOfMemoryException> kann im .NET Framework nicht wieder hergestellt werden und führt immer zu einer Beendigung der Anwendung.)

Stellen Sie sicher, dass die verschiedenen Erweiterbarkeitspunkte keinen schädlichen Code enthalten. Dies ist besonders dann relevant, wenn er unter teilweiser Vertrauenswürdigkeit ausgeführt wird, und mit Typen arbeitet, die in nicht voll vertrauenswürdigen Assemblys deklariert sind, oder Komponenten erstellt, die von teilweise vertrauenswürdigem Code verwendet werden. Weitere Informationen finden Sie unter "Bedrohungen durch teilweise vertrauenswürdigen Code" in einem späteren Abschnitt.

Beachten Sie, dass bei Ausführung unter teilweiser Vertrauenswürdigkeit die Infrastruktur der Datenvertragsserialisierung nur eine beschränkte Teilmenge des Datenvertragsprogrammiermodells unterstützt &#8211; beispielsweise werden private Datenmember oder Typen, die das <xref:System.SerializableAttribute> -Attribut verwenden, nicht unterstützt. Weitere Informationen finden Sie unter [teilweise Vertrauens](partial-trust.md)Würdigkeit.

## <a name="avoiding-unintentional-information-disclosure"></a>Vermeiden einer unbeabsichtigten Offenlegung von Informationen

Spielt beim Entwerfen serialisierbarer Typen der Sicherheitsgedanke eine Rolle, ist eine mögliche Offenlegung von Informationen von besonderem Belang.

Beachten Sie die folgenden Punkte:

- Das Programmiermodell <xref:System.Runtime.Serialization.DataContractSerializer> lässt das Offenlegen von privaten und internen Daten außerhalb des Typs oder der Assembly während der Serialisierung zu. Darüber hinaus kann die Form eines Typs während des Schemaexports offengelegt werden. Stellen Sie sicher, dass Sie das Serialisierungskonzept des Typs verstehen. Wenn Sie nichts offenlegen möchten, deaktivieren Sie dementsprechend die Serialisierung (z. B. bei einem Datenvertrag, indem Sie das <xref:System.Runtime.Serialization.DataMemberAttribute> -Attribut nicht anwenden).

- Denken Sie daran, dass derselbe Typ je nach verwendetem Serialisierungsprogramm mehrere Serialisierungskonzepte umfassen kann. Ein Typ macht möglicherweise eine Reihe von Daten zugänglich, wenn er mit <xref:System.Runtime.Serialization.DataContractSerializer> verwendet wird und mit <xref:System.Xml.Serialization.XmlSerializer>eine andere Reihe von Daten. Wird versehentlich das falsche Serialisierungsprogramm verwendet, könnten Informationen in die falschen Hände gelangen.

- Wenn Sie <xref:System.Xml.Serialization.XmlSerializer> im RPC/encoded-Modus des Legacy-Remoteprozeduraufrufs verwenden, legen Sie vielleicht unbeabsichtigt die Form des Objektdiagramms der Absenderseite für die Empfängerseite offen.

## <a name="preventing-denial-of-service-attacks"></a>Verhindern von Denial-of-Service-Angriffen

### <a name="quotas"></a>Kontingente

Wenn die Empfängerseite dazu veranlasst wird, eine erhebliche Arbeitsspeichermenge zuzuordnen, kann es sich dabei um einen Denial-of-Service-Angriff handeln. Dieser Abschnitt behandelt zwar vorwiegend Probleme des Arbeitsspeicherverbrauchs, der durch großen Nachrichten verursacht wird, es können jedoch auch andere Angriffe stattfinden. Nachrichten können beispielsweise eine außergewöhnlich lange Verarbeitungsdauer beanspruchen.

Denial-of-Service-Angriffe werden häufig mithilfe von Kontingenten abgeschwächt. Beim Überschreiten eines Kontingents wird in der Regel eine <xref:System.ServiceModel.QuotaExceededException> -Ausnahme ausgelöst. Ohne Kontingent kann eine böswillige Nachricht den gesamten verfügbaren Arbeitsspeicher belegen und eine <xref:System.OutOfMemoryException> -Ausnahme auslösen, oder es werden alle verfügbaren Stapel verbraucht, was zu einer <xref:System.StackOverflowException>führt.

Das Problem eines überschrittenen Kontingents ist behebbar. Wenn dabei ein Dienst aktiv ist, wird die aktuell verarbeitete Nachricht verworfen, der Dienst wird weiterhin ausgeführt und verarbeitet weitere Nachrichten. Die Szenarios "nicht genügend Arbeitsspeicher" und "Stapelüberlauf" sind jedoch an einer beliebigen Stelle im .NET Framework nicht wiederherstellbar. der Dienst wird beendet, wenn diese Ausnahmen auftreten.

Kontingente in WCF umfassen keine vorab Zuordnung. Ist beispielsweise das <xref:System.ServiceModel.Channels.TransportBindingElement.MaxReceivedMessageSize%2A> -Kontingent (das für verschiedene Klassen verwendet wir) auf 128 KB festgelegt, heißt das nicht, dass automatisch jeder Nachricht 128 KB zugeordnet werden. Die tatsächliche zugeordnete Menge hängt von der tatsächlichen Größe der eingehenden Nachricht ab.

Auf der Transportebene ist eine Vielzahl von Kontingenten verfügbar. Dabei handelt es sich um Kontingente, die vom jeweils verwendeten Transportkanal (HTTP, TCP usw.) eingesetzt werden. Einige dieser Kontingente werden in diesem Thema erläutert, eine ausführliche Beschreibung finden Sie jedoch unter [Transport Quotas](transport-quotas.md).

### <a name="hashtable-vulnerability"></a>Sicherheitsrisiko bei Hashtabellen

Wenn Datenverträge Hashtabellen oder Auflistungen enthalten, besteht ein Sicherheitsrisiko. Das Problem tritt auf, wenn in eine Hashtabelle eine große Anzahl von Werten eingefügt wird und eine große Anzahl dieser Werte den gleichen Hashwert generiert. Dies kann als DoS-Angriff genutzt werden.  Dieses Sicherheitsrisiko kann durch Festlegen des MaxReceivedMessageSize-Bindungs Kontingents verringert werden. Wenn dieses Kontingent festgelegt wird, um solche Angriffe zu verhindern, ist Sorgfalt geboten. Mit dem Kontingent wird die Größe der WCF-Nachricht begrenzt. Verwenden Sie außerdem in den Datenverträgen keine Hashtabellen oder Auflistungen.

## <a name="limiting-memory-consumption-without-streaming"></a>Einschränken des Arbeitsspeicherverbrauch ohne Streaming

Das Sicherheitsmodell zu großen Nachrichten hängt davon ab, ob Streaming verwendet wird. In einem einfachen Fall ohne Streaming werden Nachrichten im Arbeitsspeicher gepuffert. Verwenden Sie hier zur Abwehr großer Nachrichten das <xref:System.ServiceModel.Channels.TransportBindingElement.MaxReceivedMessageSize%2A> -Kontingent für <xref:System.ServiceModel.Channels.TransportBindingElement> oder für die vom System bereitgestellten Bindungen, und schränken Sie damit die maximal verarbeitete Nachrichtengröße ein. Beachten Sie, dass ein Dienst mehrere Nachrichten gleichzeitig verarbeiten kann, die sich dann alle im Arbeitsspeicher befinden. Verwenden Sie die Drosselungsfunktion, um diese Bedrohung zu verringern.

Beachten Sie auch, dass `MaxReceivedMessageSize` keine Obergrenze für den Arbeitsspeicherverbrauch der einzelnen Nachrichten festlegt, sondern den Verbrauch auf eine konstante Größe beschränkt. Angenommen, `MaxReceivedMessageSize` ist auf 1&#160;MB festgelegt. Wenn dann eine 1-MB-Nachricht eingeht und anschließend deserialisiert wird, ist weiterer Arbeitsspeicher zur Aufnahme des deserialisierten Objektdiagramms erforderlich. Folglich liegt der insgesamt benötigte Arbeitsspeicher bei gut über 1&#160;MB. Vermeiden Sie deshalb, serialisierbare Typen zu erstellen, die bei nur wenigen eingehenden Daten einen erheblichen Arbeitsspeicherverbrauch verursachen. Beispielsweise kann ein Datenvertrag "mycontract" mit 50 optionalen Datenmember-Feldern und zusätzlichen 100 Private-Feldern mit der XML-Konstruktion "" instanziiert werden \<MyContract/> . Bei diesem XML-Konstrukt wird Arbeitsspeicher für 150&#160;Felder belegt. Datenmember sind standardmäßig optional. Das Problem wird verschärft, wenn ein solcher Typ Teil eines Arrays ist.

`MaxReceivedMessageSize` allein reicht nicht aus, um alle Denial-of-Service-Angriffe zu verhindern. Das Deserialisierungsprogramm kann z.&#160;B. von einer eingehenden Nachricht gezwungen werden, ein tief geschachteltes Objektdiagramm (ein Objekt, das ein anderes Objekt enthält, das wiederum ein Objekt enthält usw.) zu deserialisieren. Sowohl <xref:System.Runtime.Serialization.DataContractSerializer> als auch <xref:System.Xml.Serialization.XmlSerializer> rufen zum Deserialisieren solcher Diagramme Methoden in einer geschachtelte Weise auf. Eine tiefe Schachtelung von Methodenaufrufen kann zu einer nicht behebbaren <xref:System.StackOverflowException>führen. Diese Gefahr verringert sich, wenn das <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement.MaxDepth%2A> -Kontingent die Schachtelungstiefe von XML einschränkt (wie im Abschnitt "Sicheres Verwenden von XML" weiter unten in diesem Thema erläutert wird).

`MaxReceivedMessageSize` festzulegen, ist bei der Verwendung einer binären XML-Codierung besonders wichtig. Die Verwendung einer binären Codierung ähnelt in gewisser Weise einer Komprimierung: eine kleine Gruppe von Bytes in der eingehenden Nachricht kann eine große Menge von Daten darstellen. Deshalb kann selbst eine Nachricht, die im Rahmen des `MaxReceivedMessageSize` -Limits liegt, in erweiterter Form wesentlich mehr Arbeitsspeicher beanspruchen. Um diese speziellen Risiken durch XML zu verringern, müssen alle XML-Readerkontingente richtig festgelegt werden (siehe "Sicheres Verwenden von XML" weiter unten in diesem Thema).

## <a name="limiting-memory-consumption-with-streaming"></a>Einschränken des Arbeitsspeicherverbrauch mit Streaming

Beim Streaming verwenden Sie zum Schutz vor Denial-of-Service-Angriffen möglicherweise eine niedrige `MaxReceivedMessageSize` -Einstellung. Mit Streaming sind komplexere Szenarien möglich. Ein Dateiuploaddienst akzeptiert z. B. Dateien, die größer sind als der gesamte verfügbare Arbeitsspeicher. Legen Sie in diesem Fall `MaxReceivedMessageSize` auf einen extrem hohen Wert fest, da voraussichtlich fast keine Daten im Arbeitsspeicher gepuffert werden und die Nachricht per Streaming direkt auf die Festplatte übertragen wird. Wenn eine böswillige Nachricht in diesem Fall in der Folge erzwingen kann, dass WCF Daten puffert, werden Sie `MaxReceivedMessageSize` nicht mehr von der Nachricht geschützt, die auf den gesamten verfügbaren Arbeitsspeicher zugreift.

Um diese Bedrohung zu mindern, sind bestimmte Kontingent Einstellungen für verschiedene WCF-Datenverarbeitungs Komponenten vorhanden, die die Pufferung einschränken. Am wichtigsten ist hierbei die `MaxBufferSize` -Eigenschaft für verschiedene Transportbindungselemente und Standardbindungen. Berücksichtigen Sie beim Streaming die maximale Arbeitsspeichermenge, die Sie für einzelne Nachrichten zuordnen möchten, wenn Sie dieses Kontingent festlegen. Wie bei `MaxReceivedMessageSize`wird mit dieser Einstellung kein absolutes Maximum für den Arbeitsspeicherverbrauch festgelegt, sondern der Verbrauch wird auf eine konstante Größe beschränkt. Denken Sie auch hier wie bei `MaxReceivedMessageSize`an die Möglichkeit, dass mehrere Nachrichten gleichzeitig verarbeitet werden.

### <a name="maxbuffersize-details"></a>Näheres zu MaxBufferSize

Die- `MaxBufferSize` Eigenschaft schränkt die Massen Pufferung von WCF ein. Beispielsweise puffert WCF immer SOAP-Header und SOAP-Fehler sowie alle MIME-Teile, die sich in einer MTOM-Nachricht (Message Transmission Optimization Mechanism) nicht in der natürlichen Lesefolge befinden. Diese Einstellung schränkt die Menge der gepufferten Daten in all diesen Fällen ein.

WCF erreicht dies, indem der- `MaxBufferSize` Wert an die verschiedenen Komponenten übergeben wird, die möglicherweise gepuffert werden. Beispielsweise akzeptieren einige <xref:System.ServiceModel.Channels.Message.CreateMessage%2A> -Überladungen der <xref:System.ServiceModel.Channels.Message> -Klasse den `maxSizeOfHeaders` -Parameter. WCF übergibt den `MaxBufferSize` Wert an diesen Parameter, um die Größe der SOAP-Header Pufferung einzuschränken. Bei einer direkten Verwendung der <xref:System.ServiceModel.Channels.Message> -Klasse ist es wichtig, diesen Parameter festzulegen. Im Allgemeinen ist es bei der Verwendung einer Komponente in WCF, die Kontingent Parameter annimmt, wichtig, die Auswirkungen dieser Parameter auf die Sicherheit zu verstehen und diese korrekt festzulegen.

Auch der MTOM-Nachrichtenencoder verfügt über eine `MaxBufferSize` -Einstellung. Bei der Verwendung von Standardbindungen wird hierfür automatisch der `MaxBufferSize` -Wert der Transportebene festgelegt. Wenn jedoch mit dem Bindungselement des MTOM-Nachrichtenencoders eine benutzerdefinierte Bindung erstellt wird, ist es wichtig, die `MaxBufferSize` -Eigenschaft beim Verwenden von Streaming auf einen sicheren Wert festzulegen.

## <a name="xml-based-streaming-attacks"></a>XML-basierte Streamingangriffe

`MaxBufferSize`allein reicht nicht aus, um sicherzustellen, dass WCF nicht in die Pufferung gezwungen werden kann, wenn ein Streaming erwartet wird. Beispielsweise Puffern die WCF-XML-Reader immer das gesamte Starttag des XML-Elements, wenn mit dem Lesen eines neuen Elements begonnen wird. Das dient der ordnungsgemäßen Verarbeitung von Namespaces und Attributen. Wenn `MaxReceivedMessageSize` hoch konfiguriert wird (z. B. um eine umfangreiches Streaming direkt auf die Festplatte zu ermöglichen), könnte eine böswillige Nachricht erstellt werden, in der der gesamte Nachrichtentext aus einem großen Starttag für XML-Elemente besteht. Der Versuch, dieses Starttag zu lesen, führt zu einer <xref:System.OutOfMemoryException>. Dies ist einer von vielen möglichen XML-basierten Denial-of-Service-Angriffen, die mithilfe von XML-Readerkontingenten vermieden werden können, die im Abschnitt "Sicheres Verwenden von XML" weiter unten in diesem Thema erläutert werden. Beim Streaming ist es besonders wichtig, alle diese Kontingente festzulegen.

### <a name="mixing-streaming-and-buffering-programming-models"></a>Kombinieren von Streaming- und Pufferprogrammiermodellen

Viele mögliche Angriffe ergeben sich aus kombinierten Streaming- und anderen Programmiermodellen im gleichen Dienst. Angenommen, ein Dienst umfasst zwei Vorgänge: ein Vorgang verwendet einen <xref:System.IO.Stream> und ein anderer ein Array eines benutzerdefinierten Typs. `MaxReceivedMessageSize` wird außerdem auf einen großen Wert festgelegt, damit der erste Vorgang große Streams verarbeiten kann. Leider bedeutet das, dass große Nachrichten nun auch an den zweiten Vorgang gesendet werden können und dass das Deserialisierungsprogramm Daten als Array im Arbeitsspeicher puffert, bevor der Vorgang aufgerufen wird. Das stellt einen potenzieller Denial-of-Service-Angriff dar: das `MaxBufferSize` -Kontingent schränkt die Größe des Nachrichtentextes, womit das Deserialisierungsprogramm arbeitet, nicht ein.

Vermeiden Sie es deshalb, auf Streams basierende Vorgänge mit anderen Vorgängen im selben Vertrag zu kombinieren. Sollte eine Kombination der beiden Programmiermodelle zwingend erforderlich sein, treffen Sie die folgenden Vorkehrungen:

- Deaktivieren Sie die <xref:System.Runtime.Serialization.IExtensibleDataObject> -Funktion, indem Sie die <xref:System.ServiceModel.ServiceBehaviorAttribute.IgnoreExtensionDataObject%2A> -Eigenschaft von <xref:System.ServiceModel.ServiceBehaviorAttribute> auf `true`festlegen. Dadurch stellen Sie sicher, dass nur Member deserialisiert werden, die zum Vertrag gehören.

- Legen Sie die <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A> -Eigenschaft von <xref:System.Runtime.Serialization.DataContractSerializer> auf einen sicheren Wert fest. Dieses Kontingent ist auch für das <xref:System.ServiceModel.ServiceBehaviorAttribute> -Attribut oder die Konfiguration verfügbar. Mit diesem Kontingent wird Anzahl der Objekte eingeschränkt, die in einer Deserialisierungsfolge deserialisiert werden. In der Regel wird jeder Vorgangsparameter oder jeder Nachrichtentextteil in einem Nachrichtenvertrag in einer Folge deserialisiert. Beim Deserialisieren von Arrays wird jeder Arrayeintrag als separates Objekt betrachtet.

- Legen Sie alle XML-Readerkontingente auf sichere Werte fest. Achten Sie auf <xref:System.Xml.XmlDictionaryReaderQuotas.MaxDepth%2A>, <xref:System.Xml.XmlDictionaryReaderQuotas.MaxStringContentLength%2A>und <xref:System.Xml.XmlDictionaryReaderQuotas.MaxArrayLength%2A> , und vermeiden Sie Zeichenfolgen in anderen als Streamingvorgängen.

- Überprüfen Sie die Liste der bekannten Typen und denken Sie daran, dass jeder davon jederzeit instanziiert werden kann (siehe "Verhindern des Ladens unbeabsichtigter Typen" weiter unten in diesem Thema).

- Verwenden Sie keine Typen, die die <xref:System.Xml.Serialization.IXmlSerializable> -Schnittstelle implementieren und eine große Datenmenge puffern. Fügen Sie keine Typen dieser Art der Liste der bekannten Typen hinzu.

- Verwenden Sie kein <xref:System.Xml.XmlElement>und keine <xref:System.Xml.XmlNode> -Arrays, <xref:System.Byte> -Arrays oder Typen, die <xref:System.Runtime.Serialization.ISerializable> in einem Vertrag implementieren.

- Verwenden Sie kein <xref:System.Xml.XmlElement>und keine <xref:System.Xml.XmlNode> -Arrays, <xref:System.Byte> -Arrays oder Typen, die <xref:System.Runtime.Serialization.ISerializable> in der Liste der bekannten Typen implementieren.

Die vorangehenden Vorkehrungen sind relevant, wenn der Vorgang ohne Streaming <xref:System.Runtime.Serialization.DataContractSerializer>verwendet. Kombinieren Sie niemals Streaming- und andere Programmiermodelle im selben Dienst, wenn Sie <xref:System.Xml.Serialization.XmlSerializer>verwenden, denn der Schutz von <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.MaxItemsInObjectGraph%2A> -Kontingenten ist dabei nicht vorhanden.

### <a name="slow-stream-attacks"></a>Angriffe durch langsame Streams

Eine Kategorie von Denial-of-Service-Angriffen beim Streaming wirkt sich nicht auf den Arbeitsspeicherverbrauch aus. Stattdessen konzentriert sich der Angriff auf das langsame Senden oder Empfangen von Daten. Während auf das Senden oder Empfang der Daten gewartet wird, erschöpfen sich die Ressourcen wie Threads und die verfügbaren Verbindungen. Dieser Fall kann als Ergebnis eines böswilligen Angriffs oder durch einen legitimen Absender/Empfänger bei einer langsamen Netzwerkverbindung entstehen.

Legen Sie die Transporttimeouts richtig fest, um diese Angriffe zu verhindern. Weitere Informationen finden Sie unter [Transport Kontingente](transport-quotas.md). Verwenden Sie `Read` `Write` beim Arbeiten mit Streams in WCF niemals synchrone or-Vorgänge.

## <a name="using-xml-safely"></a>Sicheres Verwenden von XML

> [!NOTE]
> Obwohl dieser Abschnitt XML behandelt, gelten die Informationen auch für JSON-Dokumente (JavaScript Objekt Notation). Die Kontingente funktionieren auf ähnliche Weise und verwenden [Mapping Between JSON and XML](mapping-between-json-and-xml.md).

### <a name="secure-xml-readers"></a>Sichere XML-Reader

Das XML-Infoset bildet die Basis der gesamten Nachrichtenverarbeitung in WCF. Das Akzeptieren von XML-Daten aus einer nicht vertrauenswürdigen Quelle ermöglicht eine Reihe von Denial-of-Service-Angriffen, die verhindert werden müssen. WCF bietet spezielle, sichere XML-Reader. Diese Leser werden automatisch erstellt, wenn eine der Standard Codierungen in WCF verwendet wird (Text, Binär oder MTOM).

Einige der Sicherheitsfunktionen dieser Reader sind immer aktiv. Die Reader verarbeiten z. B. keine Dokumenttypdefinitionen (DTDs), die eine mögliche Quelle von Denial-of-Service-Angriffen darstellen und niemals in rechtmäßigen SOAP-Nachrichten auftreten sollten. Zu weiteren Sicherheitsfunktionen gehören Readerkontingente, die konfiguriert werden müssen. Im folgenden Abschnitt werden diese Kontingente beschrieben.

Wenn Sie direkt mit XML-Readern arbeiten (z. b. beim Schreiben eines eigenen benutzerdefinierten Encoders oder beim direkten Arbeiten mit der- <xref:System.ServiceModel.Channels.Message> Klasse), verwenden Sie immer die sicheren WCF-Reader, wenn die Möglichkeit besteht, mit nicht vertrauenswürdigen Daten zu arbeiten. Erstellen Sie die sicheren Reader, indem Sie eine der Überladungen der statischen Factorymethode von <xref:System.Xml.XmlDictionaryReader.CreateTextReader%2A>, <xref:System.Xml.XmlDictionaryReader.CreateBinaryReader%2A>oder <xref:System.Xml.XmlDictionaryReader.CreateMtomReader%2A> für die <xref:System.Xml.XmlDictionaryReader> -Klasse aufrufen. Geben Sie beim Erstellen eines Readers sichere Kontingentwerte an. Rufen Sie nicht die Überladungen der `Create` -Methode auf. Diese erstellen keinen WCF-Reader. Stattdessen wird ein Reader erstellt, der nicht durch die in diesem Abschnitt beschriebenen Sicherheitsfunktionen geschützt ist.

### <a name="reader-quotas"></a>Readerkontingente

Die sicheren XML-Reader verfügen über fünf konfigurierbare Kontingente. Diese werden in der Regel mithilfe der `ReaderQuotas` -Eigenschaft für das Codierungsbindungselement oder die Standardbindungen konfiguriert oder mithilfe eines <xref:System.Xml.XmlDictionaryReaderQuotas> -Objekts, das beim Erstellen eines Readers übergeben wird.

#### <a name="maxbytesperread"></a>MaxBytesPerRead

Dieses Kontingent beschränkt die Anzahl der Bytes, die in einem einzelnen `Read` -Vorgang beim Lesen des Starttags des Elements und seiner Attribute gelesen werden können. (In Fällen ohne Streaming wird der Elementname selbst nicht in die Berechnung des Kontingents einbezogen.) <xref:System.Xml.XmlDictionaryReaderQuotas.MaxBytesPerRead%2A> ist aus den folgenden Gründen wichtig:

- Der Elementname und dessen Attribute werden immer im Arbeitsspeicher gepuffert, wenn sie gelesen werden. Deshalb ist es wichtig, dass dieses Kontingent im Streamingmodus richtig festgelegt wird, um bei einem erwarteten Streaming eine übermäßige Pufferung zu vermeiden. Informationen zum tatsächlichen Pufferumfang finden Sie unten in den Ausführungen zum `MaxDepth` -Kontingent.

- Bei zu vielen XML-Attributen kann die Verarbeitungszeit übermäßig lange dauern, da die Attributnamen auf Eindeutigkeit überprüft werden müssen. `MaxBytesPerRead` mindert dieses Risiko.

#### <a name="maxdepth"></a>MaxDepth

Diese Kontingent schränkt die maximale Schachtelungstiefe von XML-Elementen ein. Das Dokument "" hat beispielsweise eine Schachtelungs \<A> \<B> \<C/> \</B> \</A> Tiefe von drei. <xref:System.Xml.XmlDictionaryReaderQuotas.MaxDepth%2A> ist aus den folgenden Gründen wichtig:

- `MaxDepth` interagiert mit `MaxBytesPerRead`: Der Reader behält stets Daten für das aktuelle Element und alle seiner übergeordneten Elemente im Arbeitsspeicher, weshalb der maximale Arbeitsspeicherverbrauch proportional zum Produkt aus diesen beiden Einstellungen ist.

- Wenn Sie ein tief geschachteltes Objektdiagramm deserialisieren, ist das Deserialisierungsprogramm gezwungen, auf den gesamten Stapel zuzugreifen und eine nicht behebbare <xref:System.StackOverflowException>auszulösen. Ein direkter Zusammenhang besteht zwischen der XML-Schachtelung und der Objektschachtelung sowohl für <xref:System.Runtime.Serialization.DataContractSerializer> als auch für <xref:System.Xml.Serialization.XmlSerializer>. Verwenden Sie `MaxDepth` , um diese Bedrohung zu verringern.

#### <a name="maxnametablecharcount"></a>MaxNameTableCharCount

Dieses Kontingent schränkt die Größe der *Nametable*des Readers ein. Die Nametable enthält bestimmte Zeichenfolgen (z. B. Namespaces and Präfixe), die beim Verarbeiten von XML-Dokumenten auftreten. Diese Zeichenfolgen werden im Arbeitsspeicher gepuffert. Legen Sie deshalb dieses Kontingent fest, um eine übermäßige Pufferung bei einem erwarteten Streaming zu verhindern.

#### <a name="maxstringcontentlength"></a>MaxStringContentLength

Dieses Kontingent schränkt die maximale Größe der Zeichenfolgen ein, die vom XML-Reader zurückgegeben werden. Der Arbeitsspeicherverbrauch im XML-Reader selbst wird mit diesem Kontingent nicht eingeschränkt, jedoch in der Komponente, die den Reader verwendet. Wenn <xref:System.Runtime.Serialization.DataContractSerializer> z.&#160;B. einen Reader verwendet, der mit <xref:System.Xml.XmlDictionaryReaderQuotas.MaxStringContentLength%2A>gesichert ist, werden keine Zeichenfolgen deserialisiert, deren Größe dieses Kontingent überschreitet. Wird die <xref:System.Xml.XmlDictionaryReader> -Klasse direkt verwendet, beachten nicht alle Methoden dieses Kontingent, sondern nur die Methoden, die speziell für das Lesen dieser Zeichenfolgen entworfen wurden, z.&#160;B. die <xref:System.Xml.XmlDictionaryReader.ReadContentAsString%2A> -Methode. Die <xref:System.Xml.XmlReader.Value%2A> -Eigenschaft für den Reader wird von diesem Kontingent nicht beeinflusst. Sie sollte deshalb nicht verwendet werden, wenn der Schutz benötigt wird, den dieses Kontingent bietet.

#### <a name="maxarraylength"></a>MaxArrayLength

Dieses Kontingent schränkt die maximale Größe eines Arrays von Primitiven ein, einschließlich Bytearrays, die vom XML-Reader zurückgegeben werden. Der Arbeitsspeicherverbrauch im XML-Reader selbst wird mit diesem Kontingent nicht eingeschränkt, jedoch in der Komponente, die den Reader verwendet. Wenn <xref:System.Runtime.Serialization.DataContractSerializer> z.&#160;B. einen Reader verwendet, der mit <xref:System.Xml.XmlDictionaryReaderQuotas.MaxArrayLength%2A>gesichert ist, werden keine Bytearrays deserialisiert, deren Größe dieses Kontingent überschreitet. Sollen Streaming- und Pufferprogrammiermodelle in einem einzelnen Vertrag kombiniert werden, ist es wichtig, dieses Kontingent festzulegen. Denken Sie daran, dass bei einer direkten Verwendung der <xref:System.Xml.XmlDictionaryReader> -Klasse nur die Methoden dieses Kontingent beachten, die speziell zum Lesen von Arrays beliebiger Größe von bestimmten primitiven Typen entworfen wurden, wie z.&#160;B. <xref:System.Xml.XmlDictionaryReader.ReadInt32Array%2A>.

## <a name="threats-specific-to-the-binary-encoding"></a>Spezielle Bedrohungen bei der binären Codierung

Die binäre XML-Codierung, die von WCF unterstützt wird, Bein *haltet eine Funktion* für Eine große Zeichenfolge kann mit wenigen Bytes codiert werden. Das ermöglicht eine erhebliche Leistungsverbesserung, bringt jedoch neue Angriffsflächen für Denial-of-Service-Bedrohungen mit sich, die abgewehrt werden müssen.

Es gibt zwei Arten von Wörterbüchern: *statisch* und *dynamisch*. Das statische Wörterbuch besteht aus eine integrierten Liste langer Zeichenfolgen, die mithilfe eines kurzen Codes in der binären Codierung dargestellt werden können. Diese Zeichenfolgenliste steht beim Erstellen des Readers fest und kann nicht geändert werden. Keine der Zeichen folgen im statischen Wörterbuch, die von WCF standardmäßig verwendet werden, ist ausreichend groß, um eine ernste Denial-of-Service-Bedrohung darzustellen, obwohl Sie möglicherweise weiterhin in einem Angriff auf die Wörterbuch Erweiterung verwendet werden. Seien Sie in komplexen Szenarien, in denen Sie ein eigenes statisches Wörterbuch bereitstellen, mit dem Einbringen langer Wörterbuchzeichenfolgen vorsichtig.

Die Funktion dynamischer Wörterbücher ermöglicht es Nachrichten, eigene Zeichenfolgen zu definieren und kurzen Codes zuzuordnen. Diese Zeichenfolgen-Code-Zuordnungen bleiben während der gesamten Kommunikationssitzung im Arbeitsspeicher. Auf diese Weise müssen anschließende Nachrichten die Zeichenfolgen nicht erneut senden und können bereits definierte Codes nutzen. Die Länge dieser Zeichenfolgen ist beliebig, weshalb sie eine ernstere Bedrohung darstellen als die Zeichenfolgen im statischen Wörterbuch.

Die erste Bedrohung, die es zu verringern gilt, ist die Möglichkeit eines zu großen dynamischen Wörterbuchs (die Zeichenfolgen-Code-Zuordnung). Dieses Wörterbuch kann im Verlauf mehrerer Nachrichten anwachsen. Das `MaxReceivedMessageSize` -Kontingent bietet somit keinen Schutz, da es sich gesondert auf die einzelnen Nachrichten bezieht. Deshalb gibt es eine gesonderte <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.MaxSessionSize%2A> -Eigenschaft für <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> , die die Größe des Wörterbuchs einschränkt.

Im Gegensatz zu den meisten anderen Kontingenten wird dieses Kontingent auch beim Schreiben von Nachrichten angewendet. Wird es beim Lesen einer Nachricht überschritten, wird wie üblich die `QuotaExceededException` ausgelöst. Wenn es beim Schreiben einer Nachricht überschritten wird, werden alle Zeichenfolgen, die das Überschreiten des Kontingents verursachen, ohne Einbeziehung der Funktion für dynamische Wörterbücher so geschrieben, wie sie sind.

### <a name="dictionary-expansion-threats"></a>Bedrohungen durch Wörterbucherweiterungen

Wörterbucherweiterungen stellen eine wichtige Kategorie von Angriffen binärer Natur dar. Eine kleine Nachricht in binärer Form kann sich in vollständig erweiterter Textform in eine extrem große Nachricht verwandeln, wenn die Wörterbuchzeichenfolgenfunktion umfassend angewendet wird. Der Erweiterungsfaktor für Zeichenfolgen des dynamischen Wörterbuchs wird durch das <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.MaxSessionSize%2A> -Kontingent eingeschränkt, da keine Zeichenfolge des Wörterbuchs die maximale Größe des gesamten dynamischen Wörterbuchs überschreitet.

Die Eigenschaften <xref:System.Xml.XmlDictionaryReaderQuotas.MaxNameTableCharCount%2A>, `MaxStringContentLength`und `MaxArrayLength` schränken nur den Arbeitsspeicherverbrauch ein. In der Regel sind sie zur Abwehr von Bedrohungen in Szenarien ohne Streaming nicht erforderlich, da der Arbeitsspeicherverbrauch bereits durch `MaxReceivedMessageSize`eingeschränkt wird. `MaxReceivedMessageSize` berechnet jedoch die Bytes vor der Erweiterung. Bei der Verwendung der binären Codierung könnte der Arbeitsspeicherverbrauch `MaxReceivedMessageSize`überschreiten und würde lediglich durch den Faktor von <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.MaxSessionSize%2A>eingeschränkt werden. Aus diesem Grund ist es wichtig, stets alle Kontingente des Readers festzulegen (insbesondere <xref:System.Xml.XmlDictionaryReaderQuotas.MaxStringContentLength%2A>), wenn die binäre Codierung verwendet wird.

Wird die binäre Codierung in Verbindung mit <xref:System.Runtime.Serialization.DataContractSerializer>verwendet, kann die `IExtensibleDataObject` -Schnittstelle für einen Angriff durch eine Erweiterung des Wörterbuchs missbraucht werden. Diese Schnittstelle stellt im Wesentlichen unbegrenzten Speicher für beliebige Daten bereit, die nicht zum Vertrag gehören. Wenn Kontingente nicht so niedrig festgelegt werden können, dass `MaxSessionSize` multipliziert mit `MaxReceivedMessageSize` kein Problem darstellt, deaktivieren Sie die `IExtensibleDataObject` -Funktion bei der Verwendung der binären Codierung. Legen Sie die `IgnoreExtensionDataObject` -Eigenschaft für das `true` -Attribute auf `ServiceBehaviorAttribute` fest. Als Alternative können Sie auch darauf verzichten, die `IExtensibleDataObject` -Schnittstelle zu implementieren. Weitere Informationen finden Sie unter [Aufwärtskompatible Datenverträge](forward-compatible-data-contracts.md).

### <a name="quotas-summary"></a>Zusammenfassung der Kontingente

In der folgenden Tabelle werden die Hinweise zu den Kontingenten zusammengefasst.

|Bedingung|Wichtige Kontingente|
|---------------|-----------------------------|
|Kein Streaming oder Streaming von kleinen Nachrichten, Text oder MTOM-Codierung|`MaxReceivedMessageSize`, `MaxBytesPerRead` und `MaxDepth`|
|Kein Streaming oder Streaming von kleinen Nachrichten und binäre Codierung|`MaxReceivedMessageSize`, `MaxSessionSize`und alle `ReaderQuotas`|
|Streaming von großen Nachrichten, Text oder MTOM-Codierung|`MaxBufferSize` und alle `ReaderQuotas`|
|Streaming von großen Nachrichten und binäre Codierung|`MaxBufferSize`, `MaxSessionSize`und alle `ReaderQuotas`|

- Timeouts auf Transportebene müssen immer festgelegt werden, und beim Streaming dürfen niemals synchrone Lese-/Schreibvorgänge verwendet werden, unabhängig davon, ob große oder kleine Nachrichten übertragen werden.

- Wenn Sie sich über ein Kontingent nicht klar sind, legen Sie besser einen sicheren Wert fest, statt gar keinen.

## <a name="preventing-malicious-code-execution"></a>Verhindern der Ausführung von schädlichem Code

Bei den folgenden allgemeinen Bedrohungskategorien kann Code ausführt werden und ein unerwünschtes Ergebnis eintreten:

- Das Deserialisierungsprogramm lädt einen schädlichen, unsicheren oder sicherheitsrelevanten Typ.

- Eine eingehende Nachricht veranlasst das Deserialisierungsprogramm, eine Instanz eines normalerweise sicheren Typs so zu erstellen, dass er unerwünschte Folgen hat.

In den folgenden Abschnitten werden diese Bedrohungskategorien näher erläutert.

## <a name="datacontractserializer"></a>DataContractSerializer

(Sicherheitsinformationen zu finden Sie in <xref:System.Xml.Serialization.XmlSerializer> der entsprechenden Dokumentation.) Das Sicherheitsmodell für <xref:System.Xml.Serialization.XmlSerializer> ähnelt dem von <xref:System.Runtime.Serialization.DataContractSerializer> und unterscheidet sich größtenteils in den Details. Beispielsweise wird das <xref:System.Xml.Serialization.XmlIncludeAttribute> -Attribut für die Inklusion von Typen verwendet statt des <xref:System.Runtime.Serialization.KnownTypeAttribute> -Attributs. Einige Bedrohungen, die sich speziell auf <xref:System.Xml.Serialization.XmlSerializer> beziehen, werden jedoch weiter unten in diesem Thema erläutert.

### <a name="preventing-unintended-types-from-being-loaded"></a>Verhindern des Ladens unerwünschter Typen

Das Laden unerwünschter Typen kann schwerwiegende Folgen haben, unabhängig davon, ob der Typ schädlich ist oder nur sicherheitsrelevante Nebeneffekte aufweist. Ein Typ kann Sicherheitslücken verursachen, sicherheitsrelevante Aktionen in seinem Konstruktor oder dem Klassenkonstruktor ausführen, eine große Menge Arbeitsspeicher belegen, was Denial-of-Service-Angriffe vereinfacht, oder nicht behebbare Ausnahmen auslösen. Typen können Klassenkonstruktoren besitzen, die beim Laden des Typs vor dem Erstellen von Instanzen sofort ausgeführt werden. Aus diesen Gründen ist es wichtig, die Reihe der Typen zu steuern, die das Deserialisierungsprogramm laden kann.

<xref:System.Runtime.Serialization.DataContractSerializer> führt die Desialisierung mit einer losen Verknüpfung durch. Es werden keine Namen von CRL-Typen (Common Language Runtime) oder von Assemblys in den eingehenden Daten gelesen. Das ist mit dem Verhalten von <xref:System.Xml.Serialization.XmlSerializer>vergleichbar, unterscheidet sich jedoch vom Verhalten von <xref:System.Runtime.Serialization.NetDataContractSerializer>, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>und von <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>. Die lose Verknüpfung bietet eine gewisse Sicherheit, da Remoteangreifer das Laden eines beliebigen Typs nicht veranlassen können, indem sie diesen Typ einfach in der Nachricht benennen.

<xref:System.Runtime.Serialization.DataContractSerializer> darf stets einen Typ laden, der in Übereinstimmung mit dem Vertrag gerade erwartet wird. Wenn z. B. ein Datenvertrag einen Datenmember vom Typ `Customer`enthält, darf <xref:System.Runtime.Serialization.DataContractSerializer> den `Customer` -Typ beim Deserialisieren dieses Datenmembers laden.

Darüber hinaus unterstützt <xref:System.Runtime.Serialization.DataContractSerializer> Polymorphie. Ein Datenmember kann als <xref:System.Object>deklariert werden, die eingehenden Daten können jedoch eine `Customer` -Instanz enthalten. Das ist nur möglich, wenn der `Customer` -Typ für das Deserialisierungsprogramm anhand einer der folgenden Mechanismen "bekannt" gemacht wurde:

- <xref:System.Runtime.Serialization.KnownTypeAttribute> -Attribut wird auf einen Typ angewendet.

- `KnownTypeAttribute` -Attribut gibt eine Methode an, die eine Liste mit Typen zurückgibt.

- `ServiceKnownTypeAttribute` -Attribut.

- `KnownTypes` -Konfigurationsabschnitt.

- Eine Liste bekannter Typen wird bei direkter Verwendung des Serialisierungsprogramm während der Erstellung explizit an <xref:System.Runtime.Serialization.DataContractSerializer> übergeben.

Jede dieser Mechanismen erhöht die Angriffsfläche, da sie die Anzahl der Typen erhöhen, die das Deserialisierungsprogramm laden kann. Überprüfen Sie diese Mechanismen und stellen Sie sicher, dass der Liste der bekannten Typen keine unerwünschten Typen hinzugefügt werden.

Sobald sich ein bekannter Typ im Bereich befindet, kann er jederzeit geladen und Instanzen des Typs erstellt werden, selbst wenn der Vertag dessen Verwendung an sich verbietet. Angenommen, der Typ "MyDangerousType" wird über einen dieser Mechanismen der Liste der bekannten Typen hinzugefügt. Dies bedeutet Folgendes:

- `MyDangerousType` wird geladen und sein Klassenkonstruktor wird ausgeführt.

- Auch wenn nur ein Datenvertrag mit einem Zeichenfolgendatenmember deserialisiert wird, kann eine böswillige Nachricht dazu führen, dass eine Instanz von `MyDangerousType` erstellt wird. Code in `MyDangerousType`, z. B. ein Eigenschaftensetter, wird möglicherweise ausgeführt. Anschließend versucht das Deserialisierungsprogramm diese Instanz dem Zeichenfolgendatenmember zuzuordnen, schlägt fehl und löst eine Ausnahme aus.

Wenn Sie eine Methode schreiben, die eine Liste bekannter Typen zurückgibt, oder wenn Sie eine Liste direkt an den <xref:System.Runtime.Serialization.DataContractSerializer> -Konstruktor übergeben, stellen Sie sicher, dass der Code zum Erstellen der Liste sicher ist und nur vertrauenswürdige Daten heranzieht.

Wenn Sie bekannte Typen in Konfiguration angeben, stellen Sie sicher, dass die Konfigurationsdatei sicher ist. Verwenden Sie stets starke Namen in der Konfiguration, indem Sie den öffentlichen Schlüssel der signierten Assembly angeben, in der sich der Typ befindet. Geben Sie jedoch nicht die Version des zu ladenden Typs an. Das Typladeprogramm wählt die neueste Version wenn möglich automatisch aus. Die Angabe einer bestimmten Version in der Konfiguration birgt folgendes Risiko: Falls ein Typ eine Sicherheitslücke aufweist, die eine spätere Version möglicherweise beseitigt, wird trotzdem die gefährdete Version geladen, da sie in der Konfiguration ausdrücklich angegeben ist.

Zu viele bekannte Typen haben eine weitere Konsequenz: <xref:System.Runtime.Serialization.DataContractSerializer> erstellt einen Cache mit Serialisierungs-/Deserialisierungscode in der Anwendungsdomäne. Dabei erhält jeder zu serialisierende und zu deserialisierende Typ einen Eintrag. Dieser Cache wird nie gelöscht, solange die Anwendungsdomäne ausgeführt wird. Folglich kann ein Angreifer, dem die Verwendung vieler bekannter Typen in einer Anwendung bekannt ist, die Deserialisierung all dieser Typen veranlassen, wodurch der Cache außerordentlich viel Arbeitsspeicher verbraucht.

### <a name="preventing-types-from-being-in-an-unintended-state"></a>Verhindern eines unerwünschter Zustands der Typen

Ein Typ besitzt möglicherweise interne Konsistenzeinschränkungen, die beachtet werden müssen. Diese Einschränkungen dürfen bei der Deserialisierung nicht außer Kraft gesetzt werden.

Im folgenden Beispiel wird der Zustand einer Luftschleuse in einer Raumsonde dargestellt. Dabei gilt die Einschränkung, dass beide Türen nicht gleichzeitig geöffnet werden können.

[!code-csharp[DataContractAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/datacontractattribute/cs/overview.cs#3)]
[!code-vb[DataContractAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datacontractattribute/vb/overview.vb#3)]

Ein Angreifer kann folgende böswillige Nachricht senden, um die Einschränkungen zu umgehen und das Objekt in einen ungültigen Zustand zu versetzen, der unerwünschte und unvorhersehbare Folgen haben kann.

```xml
<SpaceStationAirlock>
    <innerDoorOpen>true</innerDoorOpen>
    <outerDoorOpen>true</outerDoorOpen>
</SpaceStationAirlock>
```

Diese Situation ist vermeidbar, wenn folgenden Punkte beachtet werden:

- Wenn <xref:System.Runtime.Serialization.DataContractSerializer> Klassen deserialisiert, werden in den meisten Fällen keine Konstruktoren ausgeführt. Verlassen Sie sich deshalb nicht darauf, dass der Konstruktor Zustände verwaltet.

- Verwenden Sie Rückrufe, um sicherzustellen, dass sich das Objekt in einem gültigen Zustand befindet. Der mit dem <xref:System.Runtime.Serialization.OnDeserializedAttribute> -Attribut gekennzeichnete Rückruf ist besonders hilfreich, wenn er nach Abschluss der Deserialisierung ausgeführt wird und den Gesamtzustand überprüfen und korrigieren kann. Weitere Informationen finden Sie unter [Versions tolerante Serialisierungsrückrufe](version-tolerant-serialization-callbacks.md).

- Entwerfen Sie Datenvertragstypen nicht nach einer bestimmten Reihenfolge, in der Eigenschaftensetter aufgerufen werden müssen.

- Seien Sie vorsichtig, wenn Sie ältere Typen verwenden, die mit dem <xref:System.SerializableAttribute> -Attribut gekennzeichnet sind. Viele davon wurden entwickelt, um mit .NET Framework Remoting für die Verwendung mit vertrauenswürdigen Daten zu arbeiten. Bei der Entwicklung vorhandener Typen, die mit diesem Attribut gekennzeichnet sind, spielte die Sicherheit möglicherweise keine Rolle.

- Verlassen Sie sich nicht darauf, dass die <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> -Eigenschaft des <xref:System.Runtime.Serialization.DataMemberAttribute> -Attributs das Vorhandensein von Daten in einem sicheren Zustand garantiert. Deren Status könnte auch `null`, `zero`oder `invalid`lauten.

- Vertrauen Sie niemals einem Objektdiagramm, das von einer nicht vertrauenswürdigen Datenquelle deserialisiert wurde, ohne es zuerst zu überprüfen. Zwar kann sich jedes einzelne Objekt in einem konsistenten Zustand befinden, das Objektdiagramm insgesamt vielleicht jedoch nicht. Außerdem kann es sein, dass selbst bei deaktiviertem Objektdiagramm-Beibehaltungsmodus das deserialisierte Diagramm in einem Zirkelverweis noch mehrere Verweise auf das selbe Objekt aufweist. Weitere Informationen finden Sie unter [Serialisierung und Deserialisierung](serialization-and-deserialization.md).

### <a name="using-the-netdatacontractserializer-securely"></a>Sicheres Verwenden von NetDataContractSerializer

ph x="1" /&gt; ist eine Serialisierungs-Engine, das eng verknüpfte Typen verwendet. Das ist mit <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> und <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>vergleichbar. Das heißt, es bestimmt, welcher Typ instanziiert werden soll, indem er die .NET Framework Assembly und den Typnamen aus den eingehenden Daten liest. Obwohl es Teil von WCF ist, gibt es keine Möglichkeit, diese Serialisierungs-Engine zu überspringen. benutzerdefinierter Code muss geschrieben werden. Der `NetDataContractSerializer` wird hauptsächlich zur Erleichterung der Migration von .NET Framework Remoting zu WCF bereitgestellt. Weitere Informationen finden Sie im entsprechenden Abschnitt unter [Serialisierung und Deserialisierung](serialization-and-deserialization.md).

Da die Nachricht selbst möglicherweise alle ladbaren Typen angibt, ist der <xref:System.Runtime.Serialization.NetDataContractSerializer> -Mechanismus grundsätzlich unsicher und sollte nur mit vertrauenswürdigen Daten verwendet werden. Sie können den Mechanismus sichern, indem Sie einen sicheren, Typen einschränkenden Typbinder schreiben, der nur das Laden sicherer Typen zulässt (mithilfe der <xref:System.Runtime.Serialization.NetDataContractSerializer.Binder%2A> -Eigenschaft).

Selbst wenn das Modul mit vertrauenswürdigen Daten arbeitet, geben die eingehenden Daten möglicherweise den zu ladenden Typ nur ungenau an, insbesondere, wenn die <xref:System.Runtime.Serialization.NetDataContractSerializer.AssemblyFormat%2A> -Eigenschaft auf <xref:System.Runtime.Serialization.Formatters.FormatterAssemblyStyle.Simple>festgelegt ist. Jeder, der Zugriff auf das Verzeichnis der Anwendung oder den globalen Assemblycache besitzt, kann den vorhandenen zu ladenden Typ durch einen schädlichen Typ ersetzen. Stellen Sie stets sicher, dass das Verzeichnis der Anwendung und der globale Anwendungscache gesichert sind, indem Sie die Berechtigungen richtig festlegen.

Im Allgemeinen gilt: Wenn Sie teilweise vertrauenswürdigem Code erlauben, auf Ihre `NetDataContractSerializer` -Instanz zuzugreifen oder auf andere Weise den Ersatzselektor (<xref:System.Runtime.Serialization.ISurrogateSelector>) bzw. den Serialisierungsbinder (<xref:System.Runtime.Serialization.SerializationBinder>) zu steuern, kann er möglicherweise einen großen Teil des Serialisierungs-/Deserialisierungsprozesses steuern. Er kann beispielsweise beliebige Typen einfügen, was zur Offenlegung von Informationen führt, oder das sich ergebende Objektdiagramm und die serialisierten Daten manipulieren bzw. einen Überlauf des resultierenden serialisierten Streams herbeiführen.

Ein weiteres Sicherheitsproblem bei `NetDataContractSerializer` stellen Denial-of-Service-Angriffe dar, nicht die Gefahr durch das Ausführen von schädlichem Code. Legen Sie bei der Verwendung von `NetDataContractSerializer`das <xref:System.Runtime.Serialization.NetDataContractSerializer.MaxItemsInObjectGraph%2A> -Kontingent immer auf einen sicheren Wert fest. Eine kleine böswillige Nachricht kann leicht erstellt werden, die ein Array von Objekten zuordnet, deren Größe nur durch dieses Kontingent eingeschränkt werden kann.

### <a name="xmlserializer-specific-threats"></a>Spezielle Bedrohungen bei XmlSerializer

Das <xref:System.Xml.Serialization.XmlSerializer> -Sicherheitsmodell ähnelt dem von <xref:System.Runtime.Serialization.DataContractSerializer>. Einige Bedrohungen sind jedoch speziell bei <xref:System.Xml.Serialization.XmlSerializer>relevant.

<xref:System.Xml.Serialization.XmlSerializer> generiert zur Laufzeit *Serialisierungsassemblys* mit Code, der die eigentliche Serialisierung und Deserialisierung ausführt. Diese Assemblys werden in einem temporären Dateiverzeichnis erstellt. Wenn ein anderer Prozess oder Benutzer Zugriffrechte für dieses Verzeichnis besitzt, kann er den Serialisierungs-/Deserialisierungscode mit beliebigem Code überschreiben. <xref:System.Xml.Serialization.XmlSerializer> führt dann diesen Code mit dessen Sicherheitskontext anstelle des Serialisierungs-/Deserialisierungscode aus. Stellen Sie sicher, dass die Berechtigungen für das temporäre Dateiverzeichnis richtig festgelegt sind, um dieses Szenario zu verhindern.

<xref:System.Xml.Serialization.XmlSerializer> besitzt außerdem einen Modus, in dem Serialisierungsassemblys nicht zur Laufzeit generiert werden, sondern bereits generierte Serialisierungsassemblys verwendet werden. Dieser Modus wird immer dann ausgelöst, wenn <xref:System.Xml.Serialization.XmlSerializer> eine geeignete Serialisierungsassembly findet. <xref:System.Xml.Serialization.XmlSerializer> überprüft, ob die Serialisierungsassembly mit demselben Schlüssel signiert wurde wie die Assembly, die die zu serialisierenden Typen enthält. Dies dient als Schutz vor schädlichen Assemblys, die als Serialisierungsassemblys getarnt sind. Wenn die Assembly mit den serialisierbaren Typen jedoch nicht signiert ist, kann <xref:System.Xml.Serialization.XmlSerializer> diese Überprüfung nicht ausführen und verwendet eine beliebige Assembly mit dem richtigen Namen. Auf diese Weise kann schädlicher Code ausgeführt werden. Signieren Sie stets die Assemblys, die die serialisierbaren Typen enthalten, oder schränken Sie den Zugriff auf das Verzeichnis der Anwendung und den globalen Assemblycache stark ein, um das Eindringen von schädlichen Assemblys zu verhindern.

<xref:System.Xml.Serialization.XmlSerializer> kann einem Denial-of-Service-Angriff ausgesetzt sein. <xref:System.Xml.Serialization.XmlSerializer> verfügt über kein `MaxItemsInObjectGraph` -Kontingent (wie es bei <xref:System.Runtime.Serialization.DataContractSerializer>vorhanden ist). Deshalb wird eine beliebige Anzahl von Objekten deserialisiert, die nur durch die Nachrichtengröße eingeschränkt wird.

### <a name="partial-trust-threats"></a>Bedrohungen durch teilweise vertrauenswürdigen Code

Berücksichtigen Sie beim Ausführen von teilweise vertrauenswürdigem Code die folgenden Überlegungen zu den damit verbundenen Bedrohungen. Zu diesen Bedrohungen gehören enthaltener schädlicher Code ebenso wie schädlicher Code in Verbindung mit anderen Angriffsszenarien (z.&#160;B. teilweise vertrauenswürdiger Code, der eine bestimmte Zeichenfolge enthält und diese anschließend deserialisiert).

- Bestätigen Sie bei der Verwendung irgendwelcher Serialisierungskomponenten niemals im Voraus Berechtigungen, selbst wenn die gesamte Serialisierung innerhalb des Assertionsbereichs stattfindet und nur vertrauenswürdige Daten oder Objekte behandelt werden. Eine solche Vorgehensweise könnte zu Sicherheitslücken führen.

- In Fällen, in denen teilweise vertrauenswürdiger Code entweder über Erweiterungspunkte (Ersatzzeichen), über zu serialisierende Typen oder über andere Mittel den Serialisierungsprozess bestimmt, kann dieser teilweise vertrauenswürdige Code bewirken, dass das Serialisierungsprogramm eine große Datenmenge in den serialisierten Stream ausgibt, was einen Denial-of-Service (DoS) beim Empfänger dieses Streams bewirken kann. Wenn Sie Daten serialisieren, die für ein Ziel bestimmt sind, das für DoS-Angriffe anfällig ist, dann serialisieren Sie keine teilweise vertrauenswürdigen Typen und lassen Sie nicht zu, dass teilweise vertrauenswürdiger Code die Serialisierung irgendwie steuert.

- Wenn Sie teilweise vertrauenswürdigen Code Zugriff auf die- <xref:System.Runtime.Serialization.DataContractSerializer> Instanz gewähren oder die Ersatz Zeichen für den [Datenvertrag](../extending/data-contract-surrogates.md)anderweitig steuern, kann der Serialisierungs-/Deserialisierungsprozess viel Kontrolle über den Prozess der Serialisierung/Deserialisierung haben. Er kann beispielsweise beliebige Typen einfügen, was zur Offenlegung von Informationen führt, oder das sich ergebende Objektdiagramm und die serialisierten Daten manipulieren bzw. einen Überlauf des resultierenden serialisierten Streams herbeiführen. Eine entsprechende <xref:System.Runtime.Serialization.NetDataContractSerializer> -Bedrohung wird im Abschnitt "Sicheres Verwenden von NetDataContractSerializer" beschrieben.

- Wenn das <xref:System.Runtime.Serialization.DataContractAttribute> -Attribut auf einen Typ angewendet wird (oder der Typ als <xref:System.SerializableAttribute> gekennzeichnet wird, ohne <xref:System.Runtime.Serialization.ISerializable>zu sein), kann das Deserialisierungsprogramm eine Instanz eines solchen Typs selbst dann erstellen, wenn alle Konstruktoren durch Aufrufe nicht öffentlich und/oder geschützt sind.

- Vertrauen Sie niemals dem Ergebnis der Deserialisierung, es sei denn , die Daten können als vertrauenswürdig eingestuft werden und Sie sind sicher, dass alle bekannten Typen vertrauenswürdige Typen sind. Beachten Sie, dass bei Ausführung unter teilweiser Vertrauenswürdigkeit bekannte Typen nicht aus der Anwendungskonfigurationsdatei, sondern aus der Computerkonfigurationsdatei geladen werden.

- Wenn Sie eine <xref:System.Runtime.Serialization.DataContractSerializer> -Instanz mit einem Ersatzselektor übergeben, der im teilweise vertrauenswürdigen Modus hinzugefügt wurde, kann der Code alle änderbaren Einstellungen dieses Ersatzselektors ändern.

- Wenn ein XML-Reader (oder die enthaltenen Daten) auf teilweise vertrauenswürdigem Code basiert, dann betrachten Sie das resultierende deserialisierte Objekt als nicht vertrauenswürdige Daten.

- Der Umstand, dass der <xref:System.Runtime.Serialization.ExtensionDataObject> -Typ keine öffentlichen Member besitzt, bedeutet nicht, dass die darin enthaltenen Daten sicher sind. Wenn Sie z.&#160;B. eine Deserialisierung aus einer privilegierten Datenquelle in ein Objekt ausführen, in dem sich einige Daten befinden, und dieses Objekt anschließend an teilweise vertrauenswürdigen Code übergeben, kann dieser Code die Daten in `ExtensionDataObject` lesen, indem er das Objekt serialisiert. Legen Sie bei einer Deserialisierung aus einer privilegierten Datenquelle in ein Objekt, das später an teilweise vertrauenswürdigen Code übergeben wird, wenn möglich die <xref:System.Runtime.Serialization.DataContractSerializer.IgnoreExtensionDataObject%2A> -Einstellung auf `true` fest.

- <xref:System.Runtime.Serialization.DataContractSerializer> und <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> unterstützen die Serialisierung von privaten, geschützten, internen und öffentlichen Membern mit vollständiger Vertrauenswürdigkeit. Bei teilweiser Vertrauenswürdigkeit können jedoch nur öffentliche Member serialisiert werden. Wenn eine Anwendung versucht, einen nicht öffentlichen Member zu serialisieren, wird eine <xref:System.Security.SecurityException> ausgelöst.

    Verwenden Sie das <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> -Assemblyattribut, um zuzulassen, dass interne oder geschützte interne Member serialisiert werden können. Dieses Attribut ermöglicht es einer Assembly zu deklarieren, dass eigene interne Member in anderen Assemblys sichtbar sein sollen. In diesem Fall deklariert eine Assembly, deren interne Member serialisiert werden sollen, dass ihre internen Member für System.Runtime.Serialization.dll sichtbar sein sollen.

    Der Vorteil dieser Vorgehensweise besteht darin, dass kein Codegenerierungspfad mit erweiterten Berechtigungen erforderlich ist.

    Gleichzeitig sind jedoch zwei gravierende Nachteile zu beachten.

    Der erste Nachteil besteht darin, dass die Opt-In-Eigenschaft des <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> -Attributs assemblyweit festgelegt ist. Das heißt, Sie können nicht angeben, dass nur die internen Member einer bestimmten Klasse serialisiert werden sollen. Natürlich können Sie immer noch festlegen, dass ein bestimmter interner Member nicht serialisiert werden soll, indem Sie dem betreffenden Member einfach kein <xref:System.Runtime.Serialization.DataMemberAttribute> -Attribut hinzufügen. Ebenso können Entwickler angeben, dass ein Member intern und nicht privat oder geschützt ist, wobei jedoch geringe Nachteile in Bezug auf die Sichtbarkeit zu erwarten sind.

    Der zweite Nachteil besteht darin, dass nach wie vor keine privaten und geschützten Member unterstützt werden.

    Betrachten Sie das folgende Programm, das die Verwendung des <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> -Attributs bei teilweiser Vertrauenswürdigkeit veranschaulicht:

    [!code-csharp[CDF_WCF_SecurityConsiderationsForData#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/cdf_wcf_securityconsiderationsfordata/cs/program.cs#1)]

    Im obigen Beispiel entspricht `PermissionsHelper.InternetZone` dem <xref:System.Security.PermissionSet> für teilweise Vertrauenswürdigkeit. Nun, ohne das- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Attribut, schlägt die Anwendung fehl und löst einen aus, der <xref:System.Security.SecurityException> angibt, dass nicht öffentliche Member bei teilweiser Vertrauenswürdigkeit nicht serialisiert werden können.

    Wenn jedoch der Quelldatei die folgende Zeile hinzugefügt wird, wird das Programm erfolgreich ausgeführt.

    [!code-csharp[CDF_WCF_SecurityConsiderationsForData#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/cdf_wcf_securityconsiderationsfordata/cs/program.cs#2)]

## <a name="other-state-management-concerns"></a>Weitere Überlegungen zur Zustandsverwaltung

Es gibt noch einige Überlegungen zur Verwaltung von Objektzuständen, die erwähnt werden sollten:

- Bei der Verwendung eines auf Streams basierenden Programmiermodells mit einem Streamingtransport findet die Verarbeitung der Nachricht statt, sobald sie eingeht. Der Absender der Nachricht kann den Sendevorgang in der Mitte des Streams abbrechen, wodurch Ihr Code einen unvorhersehbaren Zustand annimmt, falls mehr Inhalt erwartet wurde. Verlassen Sie sich im Allgemeinen nicht darauf, dass Streams abgeschlossen werden, und führen Sie keine Arbeiten in einem streambasierten Vorgang aus, für die im Fall eines abgebrochenen Streams kein Rollback erfolgen kann. Das gilt auch für den Fall, dass eine Nachricht nach dem Streamingtext falsch formatiert ist (es fehlt z. B. ein Endtag für den SOAP-Umschlag oder es ist ein zweiter Nachrichtentext vorhanden).

- Mit der `IExtensibleDataObject` -Funktion werden möglicherweise vertrauliche Daten ausgegeben. Wenn Sie Daten aus einer nicht vertrauenswürdigen Quelle in Datenverträgen mit `IExtensibleObjectData` zulassen und später über einen sicheren Kanal neu ausgeben, in dem Nachrichten signiert sind, bürgen Sie womöglich für völlig unbekannte Daten. Darüber hinaus sind vielleicht die gesendeten Daten insgesamt ungültig, wenn Sie sowohl die bekannten als auch die unbekannten Teile der Daten in Betracht ziehen. Vermeiden Sie diese Situation, indem Sie entweder die Eigenschaft der Erweiterungsdaten selektiv auf `null` festlegen oder indem Sie selektiv die `IExtensibleObjectData` -Funktion deaktivieren.

## <a name="schema-import"></a>Schemaimport

Normalerweise wird ein Schema zum Generieren von Typen nur zur Entwurfszeit importiert, beispielsweise, wenn Sie mit dem [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) eine Clientklasse für einen Webdienst generieren. In komplexeren Szenarien jedoch verarbeiten Sie ein Schema vielleicht auch zur Laufzeit. Seien Sie sich jedoch bewusst, dass dabei das Risiko von Denial-of-Service-Angriffen besteht. Bei einigen Schemas dauert das Importieren sehr lange. Verwenden Sie in solchen Szenarien niemals die Schemaimportkomponente von <xref:System.Xml.Serialization.XmlSerializer> , falls Schemas von einer nicht vertrauenswürdigen Quelle stammen könnten.

## <a name="threats-specific-to-aspnet-ajax-integration"></a>Spezielle Bedrohungen bei der ASP.NET AJAX-Integration

Wenn der Benutzer <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> oder implementiert <xref:System.ServiceModel.Description.WebHttpBehavior> , macht WCF einen Endpunkt verfügbar, der sowohl XML-als auch JSON-Nachrichten akzeptieren kann. Es gibt jedoch nur einen Satz von Readerkontingenten, der sowohl vom XML-Reader als auch von JSON-Reader verwendet wird. Einige Kontingenteinstellungen sind möglicherweise für einen Reader geeignet, aber zu groß für den anderen.

Mit der Implementierung von `WebScriptEnablingBehavior`hat der Benutzer die Möglichkeit, beim Endpunkt einen JavaScript-Proxy verfügbar zu machen. Die folgenden Sicherheitsprobleme müssen beachtet werden:

- Informationen über den Dienst (Vorgangsnamen, Parameternamen usw.) können abgerufen werden, indem der JavaScript-Proxy überprüft wird.

- Wird der JavaScript-Endpunkt verwendet, bleiben möglicherweise vertrauliche und private Informationen im Webbrowsercache des Clients gespeichert.

## <a name="a-note-on-components"></a>Hinweis zu Komponenten

WCF ist ein flexibles und anpassbares System. Die meisten Inhalte dieses Themas konzentrieren sich auf die gängigsten WCF-Verwendungs Szenarien. Es ist jedoch möglich, Komponenten, die WCF bereitstellt, auf viele verschiedene Arten zu verfassen. Deshalb sollten Sie wissen, welche Auswirkung die Verwendung der einzelnen Komponenten auf die Sicherheit hat. Dies gilt insbesondere für:

- Wenn XML-Reader notwendig sind, verwenden Sie nur die Reader der <xref:System.Xml.XmlDictionaryReader> -Klasse. Sichere Reader werden mit den Methoden <xref:System.Xml.XmlDictionaryReader.CreateTextReader%2A>, <xref:System.Xml.XmlDictionaryReader.CreateBinaryReader%2A>oder <xref:System.Xml.XmlDictionaryReader.CreateMtomReader%2A> erstellt. Verwenden Sie nicht die <xref:System.Xml.XmlReader.Create%2A> -Methode. Konfigurieren Sie die Reader immer mit sicheren Kontingenten. Die serialisierungsengines in WCF sind nur dann sicher, wenn Sie mit sicheren XML-Lesern von WCF verwendet werden.

- Wenn Sie potenziell nicht vertrauenswürdige Daten mit <xref:System.Runtime.Serialization.DataContractSerializer> deserialisieren, legen Sie immer die <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A> -Eigenschaft fest.

- Legen Sie beim Erstellen einer Nachricht den `maxSizeOfHeaders` -Parameter fest, falls `MaxReceivedMessageSize` keinen ausreichenden Schutz bietet.

- Wenn Sie einen Encoder erstellen, konfigurieren Sie stets die relevanten Kontingente, z. B. `MaxSessionSize` und `MaxBufferSize`.

- Legen Sie bei Verwendung eines XPath-Nachrichtenfilters <xref:System.ServiceModel.Dispatcher.XPathMessageFilter.NodeQuota%2A> fest, um die Menge der XML-Knoten einzuschränken, die der Filter durchläuft. Verwenden Sie keine XPath-Ausdrücke, deren Berechnung lange dauert, ohne dass viele Knoten durchlaufen werden.

- Machen Sie sich generell bei der Verwendung einer Komponente, die ein Kontingent akzeptiert, mit dessen Auswirkung auf die Sicherheit vertraut, und legen Sie einen sicheren Wert dafür fest.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Xml.XmlDictionaryReader>
- <xref:System.Xml.Serialization.XmlSerializer>
- [Bekannte Typen in Datenverträgen](data-contract-known-types.md)

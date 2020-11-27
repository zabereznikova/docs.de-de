---
title: Benutzerdefinierte Encoder
ms.date: 03/30/2017
ms.assetid: fa0e1d7f-af36-4bf4-aac9-cd4eab95bc4f
ms.openlocfilehash: c2ad0c947afd293d0923faa3e9d914b6911ce941
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254778"
---
# <a name="custom-encoders"></a>Benutzerdefinierte Encoder

In diesem Thema wird das Erstellen benutzerdefinierter Encoder behandelt.  
  
 In Windows Communication Foundation (WCF) verwenden Sie eine *Bindung* , um anzugeben, wie Daten über ein Netzwerk zwischen Endpunkten übertragen werden sollen. Eine Bindung besteht aus einer Sequenz von *Bindungs Elementen*. Eine Bindung enthält optionale Protokoll Bindungs Elemente, wie z. b. Sicherheit, ein erforderliches *Nachrichten Encoder* -Bindungs Element und ein erforderliches Transport Bindungs Element. Ein Nachrichtenencoder wird von einem Nachrichtencodierungs-Bindungselement dargestellt. In WCF sind drei Nachrichten Encoder enthalten: Binary, Message Transmission Optimization Mechanism (MTOM) und Text.  
  
 Ein Bindungselement für die Nachrichtencodierung dient zum Serialisieren einer ausgehenden <xref:System.ServiceModel.Channels.Message>. Anschließend wird die Nachricht an den Transport übergeben, oder die serialisierte Form einer Nachricht wird vom Transport empfangen und an die Protokollebene übergeben. Ist die Protokollebene nicht vorhanden, erfolgt die Übergabe an die Anwendung.  
  
 <xref:System.ServiceModel.Channels.Message>-Instanzen werden von Nachrichtenencodern in und aus Übertragungsdarstellungen transformiert. Obgleich Encoder als Elemente beschrieben werden, die der Transportebene des Kanalstapels übergeordnet sind, befinden sie sich eigentlich auf der Transportebene. Von Transporten (beispielsweise HTTP) wird die Nachricht gemäß den Anforderungen des Transportstandards formatiert. Die Encoder (beispielsweise Text-XML) dienen lediglich zum Codieren der Nachricht.  
  
 Beim Herstellen einer Verbindung mit einem vorhandenen Client oder Server muss möglicherweise eine bestimmte Nachrichtencodierung verwendet werden. Allerdings können WCF-Dienste über mehrere Endpunkte zugänglich gemacht werden, von denen jeder über einen anderen Nachrichten Encoder verfügt. Wenn ein einzelner Encoder nicht für alle Zielbenutzer des Diensts ausreicht, können Sie den Dienst über mehrere Endpunkte hinweg verfügbar machen. Somit kann von Clientanwendungen der optimale Endpunkt gewählt werden. Die Verwendung mehrerer Endpunkte ermöglicht es Ihnen, die Vorteile anderer Nachrichtencodierungen mit anderen Bindungselementen zu kombinieren.  
  
## <a name="system-provided-encoders"></a>Vom System bereitgestellte Encoder  

 WCF bietet mehrere vom System bereitgestellte Bindungen, die für die gängigsten Anwendungsszenarien konzipiert sind. In jeder dieser Bindungen wird ein Transport mit einem Nachrichtenencoder und anderen Optionen (beispielsweise Sicherheit) kombiniert. In diesem Thema wird beschrieben, wie `Text` `Binary` `MTOM` Sie die in WCF enthaltenen Nachrichten Encoder, und erweitern oder einen eigenen benutzerdefinierten Encoder erstellen. Der Textnachrichtenencoder unterstützt sowohl reine XML-Codierung als auch SOAP-Codierungen. Der reine XML-Codierungsmodus des Textnachrichtenencoders wird als POX-Encoder ("Plain Old XML") bezeichnet, um ihn von der textbasierten SOAP-Codierung zu unterscheiden.  
  
 Weitere Informationen zu den Kombinationen von Bindungs Elementen, die von den vom System bereitgestellten Bindungen bereitgestellt werden, finden Sie im entsprechenden Abschnitt unter [Auswählen eines Transports](../feature-details/choosing-a-transport.md).  
  
## <a name="how-to-work-with-system-provided-encoders"></a>Arbeiten mit vom System bereitgestellten Encodern  

 Das Hinzufügen einer Codierung zu einem Bindungselement erfolgt mithilfe einer von <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> abgeleiteten Klasse.  
  
 WCF stellt die folgenden Typen von Bindungs Elementen bereit, die von der- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> Klasse abgeleitet werden, die Text-, Binär-und MTOM-Codierung (Message Transmission Optimization Mechanism) bereitstellen kann:  
  
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>: Der am wenigsten effiziente Encoder für XML-Nachrichten, der jedoch das höchste Maß an Interoperabilität bietet. Text-XML kann in der Regel von Webdiensten oder Webdienstclients interpretiert werden. Das Übermitteln umfangreicher Blöcke binärer Daten in Textform ist jedoch wenig effizient.  
  
- Die <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>-Klasse stellt das Bindungselement dar, von dem die Zeichencodierung und die für binäre XML-Nachrichten verwendete Nachrichtenversion angegeben werden. Dies ist die effizienteste der Codierungsoptionen, aber die am wenigsten interoperabel, da Sie nur von WCF-Endpunkten unterstützt wird.  
  
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>: Stellt das Bindungselement dar, von dem die Zeichencodierung und die für eine Meldung mit MTOM-Codierung (Message Transmission Optimization Mechanism) verwendete Nachrichtenversion angegeben werden. MTOM ist eine effiziente Technologie zum Übertragen von Binärdaten in WCF-Nachrichten. Der MTOM-Encoder versucht, einen Ausgleich zwischen Effizienz und Interoperabilität zu erschaffen. Die MTOM-Verschlüsselung überträgt die meisten XML-Daten in Textform, optimiert aber große Binärdatenblöcke durch Übertragung ohne Textkonvertierung.  
  
 Vom Bindungselement wird eine Binär-, MTOM- oder Text-<xref:System.ServiceModel.Channels.MessageEncoderFactory> erstellt. Von der Factory wird eine <xref:System.ServiceModel.Channels.MessageEncoderFactory>-Binär-, MTOM- oder Textinstanz erstellt. Üblicherweise ist lediglich eine einzelne Instanz vorhanden. Bei Verwendung von Sitzungen kann jedoch für jede Sitzung ein anderer Encoder bereitgestellt werden. Vom Binärencoder wird diese Möglichkeit zum Koordinieren dynamischer Wörterbücher genutzt (siehe XML-Infrastruktur).  
  
 Die Methoden <xref:System.ServiceModel.Channels.MessageEncoder.ReadMessage%2A> und <xref:System.ServiceModel.Channels.MessageEncoder.WriteMessage%2A> bilden den Kern der Encoder. Sie dienen zum Lesen einer Nachricht aus einem Stream oder aus einem <xref:System.Byte>-Array. Bytearrays werden verwendet, wenn der Transport im Puffermodus betrieben wird. Nachrichten werden stets in Streams geschrieben. Muss die Nachricht gepuffert werden, wird hierzu ein Stream bereitgestellt.  
  
 Die restlichen Member arbeiten mit Supportinhalten, Medientypen und <xref:System.ServiceModel.Channels.MessageEncoder.MessageVersion%2A>. Die Encodermethoden werden vom Transport aufgerufen, um zu testen, ob die eingehende Nachricht damit decodiert werden kann, oder um festzustellen, ob die ausgehende Nachricht für diesen Encoder geeignet ist.  
  
 Mit jeder der drei Encoderimplementierungen werden Eigenschaften hinzugefügt, die für die jeweilige Codierung benötigt werden. Darüber hinaus sind sie vollständig konfigurierbar. Von den Encodern werden überdies Readerkontingente mit sicheren Standardeinstellungen verfügbar gemacht. Informationen zu Kontingenten finden Sie im Thema zur XML-Infrastruktur.  
  
## <a name="features-of-system-provided-encoders"></a>Funktionen der vom System bereitgestellten Encoder  

 Die vom System bereitgestellten Encoder verfügen über eine Reihe von Funktionen.  
  
### <a name="pooling"></a>Pooling  

 Für jede der Encoderimplementierungen wird versucht, ein Höchstmaß an Pooling zu erzielen. Eine geeignete Vorgehensweise zum Verbessern der Leistung verwalteten Codes besteht im Verringern der Speicherbelegung. Für das Pooling wird von den Implementierungen die `SynchronizedPool`-Klasse verwendet. Die C#-Datei enthält eine Beschreibung der zusätzlichen, von dieser Klasse verwendeten Optimierungen.  
  
 Die Instanzen <xref:System.Xml.XmlDictionaryReader> und <xref:System.Xml.XmlDictionaryWriter> werden in einem Pool zusammengefasst und neu initialisiert, um eine Neuzuordnung von Instanzen für jede Nachricht zu unterbinden. Bei einem Reader wird dieser mithilfe eines `OnClose`-Rückrufs zurückgefordert, wenn `Close()` aufgerufen wird. Vom Encoder werden auch einige Nachrichtenzustandsobjekte wiederverwendet, die bei der Nachrichtenerstellung verwendet wurden. Die Größe dieser Pools kann über die Eigenschaften `MaxReadPoolSize` und `MaxWritePoolSize` für jede der drei von <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> abgeleiteten Klassen konfiguriert werden.  
  
### <a name="binary-encoding"></a>Binärcodierung  

 Werden bei der Binärcodierung Sitzungen verwendet, muss die dynamische Wörterbuchzeichenfolge an den Empfänger der Nachricht übermittelt werden. Hierzu werden der Nachricht die dynamischen Wörterbuchzeichenfolgen als Präfix hinzugefügt. Vom Empfänger werden die Zeichenfolgen entfernt und der Sitzung hinzugefügt. Anschließend wird die Nachricht verarbeitet. Für die ordnungsgemäße Übergabe der Wörterbuchzeichenfolgen muss der Transport gepuffert werden.  
  
 Die Zeichenfolgen werden der Meldung mithilfe einer internen `AddSessionInformationToMessage`-Methode angehängt. Mit dieser Methode werden die Zeichenfolgen dem Nachrichtenanfang als UTF-8 hinzugefügt. Davor wird als Präfix die Länge der Zeichenfolgen eingefügt. Der gesamte Wörterbuchheader wird daraufhin mit einem Präfix versehen, das die Datenlänge enthält. Der umgekehrte Vorgang erfolgt mittels einer internen `ExtractSessionInformationFromMessage`-Methode.  
  
 Zusätzlich zum Verarbeiten dynamischer Wörterbuchschlüssel erfolgt der Empfang sitzungsbasierter Meldungen auf eindeutige Weise. Anstatt einen Reader über das Dokument zu erstellen und dieses anschließend zu verarbeiten, wird der binäre Stream bei der Binärcodierung mithilfe der internen `MessagePatterns`-Klasse zerlegt. Die Idee ist, dass die meisten Nachrichten über einen bestimmten Satz von Headern verfügen, die bei der Generierung durch WCF in einer bestimmten Reihenfolge angezeigt werden. Die Nachricht wird vom Mustersystem auf Basis der jeweiligen Erwartung zerlegt. Ist der Vorgang erfolgreich, wird ohne XML-Analyse ein <xref:System.ServiceModel.Channels.MessageHeaders>-Objekt erstellt. Andernfalls wird wieder die Standardmethode verwendet.  
  
### <a name="mtom-encoding"></a>MTOM-Codierung  

 Die <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>-Klasse verfügt über eine zusätzliche Konfigurationseigenschaft mit der Bezeichnung <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement.MaxBufferSize%2A>. Hierdurch wird eine Obergrenze für die Menge der Daten festgelegt, die beim Lesen einer Nachricht gepuffert werden dürfen. Das XML Information Set (Infoset) sowie andere MIME-Teile müssen möglicherweise gepuffert werden, um MIME-Teile wieder zu einer einzelnen Nachricht zusammenzufügen.  
  
 Für das ordnungsgemäße Funktionieren mit HTTP werden vom internen MTOM-Nachrichtenencoder einige interne APIs für `GetContentType` (ebenfalls intern) und `WriteMessage` bereitgestellt. Letzteres Element ist öffentlich und kann außer Kraft gesetzt werden. Damit sichergestellt ist, dass die Werte in den HTTP-Headern mit den Werten in den MIME-Headern übereinstimmen, ist ein höheres Kommunikationsaufkommen erforderlich.  
  
 Intern verwendet der MTOM-Nachrichten Encoder WCF-Text Reader und ähnelt dem Text Encoder. Der Hauptunterschied besteht darin, dass vom MTOM-Nachrichtenencoder große Binärcodeabschnitte (oder "Binary Large Objects", so genannte BLOBs) optimiert werden, indem sie vor dem Einbetten in die Nachrichtenbytes nicht in eine Base-64-Codierung umgewandelt werden. Stattdessen bleiben diese BLOBs extrahiert und werden als MIME-Anhänge referenziert.  
  
## <a name="writing-your-own-encoder"></a>Schreiben eigener Encoder  

 Zum Implementieren eines eigenen Nachrichtenencoders müssen benutzerdefinierte Implementierungen der folgenden abstrakten Basisklassen bereitgestellt werden:  
  
- <xref:System.ServiceModel.Channels.MessageEncoder>  
  
- <xref:System.ServiceModel.Channels.MessageEncoderFactory>  
  
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
  
 Die Umwandlung der speicherinternen Version einer Nachricht zu einer Version, die in einen Stream geschrieben werden kann, ist Teil der <xref:System.ServiceModel.Channels.MessageEncoder>-Klasse, die als Factory für XML-Reader und XML-Writer mit Unterstützung für bestimmte XML-Codierungstypen fungiert.  
  
- Folgende Schlüsselmethoden dieser Klasse müssen außer Kraft gesetzt werden:  
  
- <xref:System.ServiceModel.Channels.MessageEncoder.WriteMessage%2A>: nimmt ein <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>-Objekt an und schreibt es in ein <xref:System.IO.Stream>-Objekt.  
  
- <xref:System.ServiceModel.Channels.MessageEncoder.ReadMessage%2A>: nimmt ein <xref:System.IO.Stream>-Objekt sowie eine maximale Headergröße an und gibt ein <xref:System.ServiceModel.Channels.Message>-Objekt zurück.  
  
 Die Umwandlung zwischen dem standardmäßigen Transportprotokoll und der benutzerdefinierten Codierung wird anhand des in diese Methoden geschriebenen Codes behandelt.  
  
 Der nächste Schritt besteht im Codieren einer Factoryklasse zum Erstellen des benutzerdefinierten Encoders. Überschreiben Sie den <xref:System.ServiceModel.Channels.MessageEncoderFactory.Encoder%2A>, um eine Instanz des benutzerdefinierten <xref:System.ServiceModel.Channels.MessageEncoder> zurückzugeben.  
  
 Verbinden Sie anschließend die benutzerdefinierte <xref:System.ServiceModel.Channels.MessageEncoderFactory> mit dem Bindungselementstapel für die Konfiguration des Diensts oder des Clients durch Überschreiben der <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A>-Methode, um eine Instanz der Factory zurückzugeben.  
  
 WCF enthält zwei Beispiele, die diesen Prozess mit Beispielcode veranschaulichen: [benutzerdefinierter Nachrichten Encoder: benutzerdefinierter Text Encoder](../samples/custom-message-encoder-custom-text-encoder.md) und [benutzerdefinierter Nachrichten Encoder: Komprimierungs Encoder](../samples/custom-message-encoder-compression-encoder.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MessageEncoderFactory>
- <xref:System.ServiceModel.Channels.MessageEncoder>
- [Datenübertragungsarchitektur - Übersicht](../feature-details/data-transfer-architectural-overview.md)
- [Auswählen eines Nachrichtenencoders](../feature-details/choosing-a-message-encoder.md)
- [Wählen eines Transports](../feature-details/choosing-a-transport.md)

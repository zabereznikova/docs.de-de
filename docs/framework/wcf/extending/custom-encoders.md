---
title: Benutzerdefinierte Encoder
ms.date: 03/30/2017
ms.assetid: fa0e1d7f-af36-4bf4-aac9-cd4eab95bc4f
ms.openlocfilehash: ae3904af83452dd76723abb78a7a06fdb0f798cc
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="custom-encoders"></a>Benutzerdefinierte Encoder
In diesem Thema wird das Erstellen benutzerdefinierter Encoder behandelt.  
  
 In Windows Communication Foundation (WCF), die Sie verwenden eine *Bindung* angeben, wie Daten in einem Netzwerk zwischen Endpunkten übertragen. Eine Bindung besteht aus einer Folge von *Bindungselementen*. Eine Bindung enthält optionale protokollbindungselemente, wie z. B. Sicherheit, ein erforderliches *Nachrichtenencoder* Bindungselement und ein erforderliches Transportbindungselement. Ein Nachrichtenencoder wird von einem Nachrichtencodierungs-Bindungselement dargestellt. Drei Nachrichtenencoder in WCF enthalten sind: Binär und Message Transmission Optimization Mechanism (MTOM) Text.  
  
 Ein Bindungselement für die Nachrichtencodierung dient zum Serialisieren einer ausgehenden <xref:System.ServiceModel.Channels.Message>. Anschließend wird die Nachricht an den Transport übergeben, oder die serialisierte Form einer Nachricht wird vom Transport empfangen und an die Protokollebene übergeben. Ist die Protokollebene nicht vorhanden, erfolgt die Übergabe an die Anwendung.  
  
 <xref:System.ServiceModel.Channels.Message>-Instanzen werden von Nachrichtenencodern in und aus Übertragungsdarstellungen umgewandelt. Obgleich Encoder als Elemente beschrieben werden, die der Transportebene des Kanalstapels übergeordnet sind, befinden sie sich eigentlich auf der Transportebene. Von Transporten (beispielsweise HTTP) wird die Nachricht gemäß den Anforderungen des Transportstandards formatiert. Die Encoder (beispielsweise Text-XML) dienen lediglich zum Codieren der Nachricht.  
  
 Beim Herstellen einer Verbindung mit einem vorhandenen Client oder Server muss möglicherweise eine bestimmte Nachrichtencodierung verwendet werden. WCF-Dienste können jedoch auch über mehrere Endpunkte bereitstellen, jeweils eine andere nachrichtencodierung zugänglich gemacht werden. Wenn ein einzelner Encoder nicht für alle Zielbenutzer des Diensts ausreicht, können Sie den Dienst über mehrere Endpunkte hinweg verfügbar machen. Somit kann von Clientanwendungen der optimale Endpunkt gewählt werden. Die Verwendung mehrerer Endpunkte ermöglicht es Ihnen, die Vorteile anderer Nachrichtencodierungen mit anderen Bindungselementen zu kombinieren.  
  
## <a name="system-provided-encoders"></a>Vom System bereitgestellte Encoder  
 WCF bietet mehrere vom System bereitgestellte Bindungen, mit denen die häufigsten Anwendungsszenarios abzudecken. In jeder dieser Bindungen wird ein Transport mit einem Nachrichtenencoder und anderen Optionen (beispielsweise Sicherheit) kombiniert. In diesem Thema wird beschrieben, wie zum Erweitern der `Text`, `Binary`, und `MTOM` Nachrichtenencoder, die in WCF enthalten sind, oder Erstellen von eigenen benutzerdefinierten Encoders. Der Textnachrichtenencoder unterstützt sowohl reine XML-Codierung als auch SOAP-Codierungen. Der reine XML-Codierungsmodus des Textnachrichtenencoders wird als POX-Encoder ("Plain Old XML") bezeichnet, um ihn von der textbasierten SOAP-Codierung zu unterscheiden.  
  
 Weitere Informationen zu den möglichen Kombinationen von Bindungselementen, die vom System bereitgestellten Bindungen gebotenen finden Sie im entsprechenden Abschnitt in [Wählen eines Transports](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md).  
  
## <a name="how-to-work-with-system-provided-encoders"></a>Arbeiten mit vom System bereitgestellten Encodern  
 Das Hinzufügen einer Codierung zu einem Bindungselement erfolgt mithilfe einer von <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> abgeleiteten Klasse.  
  
 WCF bietet die folgenden Typen von Bindungselementen, die abgeleitet wurde. die <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> Klasse, die für Text, Binär und Message Transmission Optimization Mechanism (MTOM) Codierung bereitstellen kann:  
  
-   <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>: Der am wenigsten effiziente Encoder für XML-Nachrichten, der jedoch das höchste Maß an Interoperabilität bietet. Text-XML kann in der Regel von Webdiensten oder Webdienstclients interpretiert werden. Das Übermitteln umfangreicher Blöcke binärer Daten in Textform ist jedoch wenig effizient.  
  
-   Die <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>-Klasse stellt das Bindungselement dar, von dem die Zeichencodierung und die für binäre XML-Nachrichten verwendete Nachrichtenversion angegeben werden. Dies ist die effizienteste Codierungsoptionen, aber die am wenigsten interoperabel, da sie nur von WCF-Endpunkten unterstützt wird.  
  
-   <<!--zz xref:System.ServiceModel.Channels.MTOMMessageEncodingBindingElement --> `System.ServiceModel.Channels.MTOMMessageEncodingBindingElement`>: stellt das Bindungselement, der angibt, das die zeichencodierung und Nachrichtenversion für eine Meldung mit MTOM Message Transmission Optimization Mechanism (MTOM). MTOM ist eine effiziente Technologie zum Übertragen von Binärdaten in WCF-Nachrichten. Der MTOM-Encoder versucht, einen Ausgleich zwischen Effizienz und Interoperabilität zu erschaffen. Die MTOM-Verschlüsselung überträgt die meisten XML-Daten in Textform, optimiert aber große Binärdatenblöcke durch Übertragung ohne Textkonvertierung.  
  
 Vom Bindungselement wird eine Binär-, MTOM- oder Text-<xref:System.ServiceModel.Channels.MessageEncoderFactory> erstellt. Von der Factory wird eine <xref:System.ServiceModel.Channels.MessageEncoderFactory>-Binär-, MTOM- oder Textinstanz erstellt. Üblicherweise ist lediglich eine einzelne Instanz vorhanden. Bei Verwendung von Sitzungen kann jedoch für jede Sitzung ein anderer Encoder bereitgestellt werden. Vom Binärencoder wird diese Möglichkeit zum Koordinieren dynamischer Wörterbücher genutzt (siehe XML-Infrastruktur).  
  
 Die Methoden <xref:System.ServiceModel.Channels.MessageEncoder.ReadMessage%2A> und <xref:System.ServiceModel.Channels.MessageEncoder.WriteMessage%2A> bilden den Kern der Encoder. Sie dienen zum Lesen einer Nachricht aus einem Stream oder aus einem <xref:System.Byte>-Array. Bytearrays werden verwendet, wenn der Transport im Puffermodus betrieben wird. Nachrichten werden stets in Streams geschrieben. Muss die Nachricht gepuffert werden, wird hierzu ein Stream bereitgestellt.  
  
 Die restlichen Member arbeiten mit Supportinhalten, Medientypen und <xref:System.ServiceModel.Channels.MessageEncoder.MessageVersion%2A>. Die Encodermethoden werden vom Transport aufgerufen, um zu testen, ob die eingehende Nachricht damit decodiert werden kann, oder um festzustellen, ob die ausgehende Nachricht für diesen Encoder geeignet ist.  
  
 Mit jeder der drei Encoderimplementierungen werden Eigenschaften hinzugefügt, die für die jeweilige Codierung benötigt werden. Darüber hinaus sind sie vollständig konfigurierbar. Von den Encodern werden überdies Readerkontingente mit sicheren Standardeinstellungen verfügbar gemacht. Informationen zu Kontingenten finden Sie im Thema zur XML-Infrastruktur.  
  
## <a name="features-of-system-provided-encoders"></a>Funktionen der vom System bereitgestellten Encoder  
 Die vom System bereitgestellten Encoder verfügen über eine Reihe von Funktionen.  
  
### <a name="pooling"></a>Pooling  
 Für jede der Encoderimplementierungen wird versucht, ein Höchstmaß an Pooling zu erzielen. Eine geeignete Vorgehensweise zum Verbessern der Leistung verwalteten Codes besteht im Verringern der Speicherbelegung. Für das Pooling wird von den Implementierungen die `SynchronizedPool`-Klasse verwendet. Die C#-Datei enthält eine Beschreibung der zusätzlichen, von dieser Klasse verwendeten Optimierungen.  
  
 Die Instanzen `XmlDictionaryReader` und `XmlDictionaryWriter` werden in einem Pool zusammengefasst und neu initialisiert, um eine Neuzuordnung von Instanzen für jede Nachricht zu unterbinden. Bei einem Reader wird dieser mithilfe eines `OnClose`-Rückrufs zurückgefordert, wenn `Close()` aufgerufen wird. Vom Encoder werden auch einige Nachrichtenzustandsobjekte wiederverwendet, die bei der Nachrichtenerstellung verwendet wurden. Die Größe dieser Pools kann über die Eigenschaften `MaxReadPoolSize` und `MaxWritePoolSize` für jede der drei von <xref:System.ServiceModel.Channels.MessageEncodingBindingElement> abgeleiteten Klassen konfiguriert werden.  
  
### <a name="binary-encoding"></a>Binärcodierung  
 Werden bei der Binärcodierung Sitzungen verwendet, muss die dynamische Wörterbuchzeichenfolge an den Empfänger der Nachricht übermittelt werden. Hierzu werden der Nachricht die dynamischen Wörterbuchzeichenfolgen als Präfix hinzugefügt. Vom Empfänger werden die Zeichenfolgen entfernt und der Sitzung hinzugefügt. Anschließend wird die Nachricht verarbeitet. Für die ordnungsgemäße Übergabe der Wörterbuchzeichenfolgen muss der Transport gepuffert werden.  
  
 Die Zeichenfolgen werden der Meldung mithilfe einer internen `AddSessionInformationToMessage`-Methode angehängt. Mit dieser Methode werden die Zeichenfolgen dem Nachrichtenanfang als UTF-8 hinzugefügt. Davor wird als Präfix die Länge der Zeichenfolgen eingefügt. Der gesamte Wörterbuchheader wird daraufhin mit einem Präfix versehen, das die Datenlänge enthält. Der umgekehrte Vorgang erfolgt mittels einer internen `ExtractSessionInformationFromMessage`-Methode.  
  
 Zusätzlich zum Verarbeiten dynamischer Wörterbuchschlüssel erfolgt der Empfang sitzungsbasierter Meldungen auf eindeutige Weise. Anstatt einen Reader über das Dokument zu erstellen und dieses anschließend zu verarbeiten, wird der binäre Stream bei der Binärcodierung mithilfe der internen `MessagePatterns`-Klasse zerlegt. Die Idee besteht, dass die meisten Nachrichten einen bestimmten Satz von Headern, die in einer bestimmten Reihenfolge beim Generieren von WCF angezeigt werden. Die Nachricht wird vom Mustersystem auf Basis der jeweiligen Erwartung zerlegt. Ist der Vorgang erfolgreich, wird ohne XML-Analyse ein <xref:System.ServiceModel.Channels.MessageHeaders>-Objekt erstellt. Andernfalls wird wieder die Standardmethode verwendet.  
  
### <a name="mtom-encoding"></a>MTOM-Codierung  
 Die <<!--zz xref:System.ServiceModel.Channels.MTOMMessageEncodingBindingElement --> `System.ServiceModel.Channels.MTOMMessageEncodingBindingElement`>-Klasse verfügt über eine zusätzliche Konfigurationseigenschaft mit dem Namen <<!--zz xref:System.ServiceModel.Channels.MTOMMessageEncodingBindingElement --> `System.ServiceModel.Channels.MTOMMessageEncodingBindingElement`. MaxBufferSize % 2A >. Hierdurch wird eine Obergrenze für die Menge der Daten festgelegt, die beim Lesen einer Nachricht gepuffert werden dürfen. Das XML Information Set (Infoset) sowie andere MIME-Teile müssen möglicherweise gepuffert werden, um MIME-Teile wieder zu einer einzelnen Nachricht zusammenzufügen.  
  
 Für das ordnungsgemäße Funktionieren mit HTTP werden vom internen MTOM-Nachrichtenencoder einige interne APIs für `GetContentType` (ebenfalls intern) und `WriteMessage` bereitgestellt. Letzteres Element ist öffentlich und kann außer Kraft gesetzt werden. Damit sichergestellt ist, dass die Werte in den HTTP-Headern mit den Werten in den MIME-Headern übereinstimmen, ist ein höheres Kommunikationsaufkommen erforderlich.  
  
 Intern wird der MTOM-Nachrichtenencoder TextReader von WCF verwendet und ist vergleichbar mit dem textencoder. Der Hauptunterschied besteht darin, dass vom MTOM-Nachrichtenencoder große Binärcodeabschnitte (oder "Binary Large Objects", so genannte BLOBs) optimiert werden, indem sie vor dem Einbetten in die Nachrichtenbytes nicht in eine Base-64-Codierung umgewandelt werden. Stattdessen bleiben diese BLOBs extrahiert und werden als MIME-Anhänge referenziert.  
  
## <a name="writing-your-own-encoder"></a>Schreiben eigener Encoder  
 Zum Implementieren eines eigenen Nachrichtenencoders müssen benutzerdefinierte Implementierungen der folgenden abstrakten Basisklassen bereitgestellt werden:  
  
-   <xref:System.ServiceModel.Channels.MessageEncoder>  
  
-   <xref:System.ServiceModel.Channels.MessageEncoderFactory>  
  
-   <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
  
 Die Umwandlung der speicherinternen Version einer Nachricht zu einer Version, die in einen Stream geschrieben werden kann, ist Teil der <xref:System.ServiceModel.Channels.MessageEncoder>-Klasse, die als Factory für XML-Reader und XML-Writer mit Unterstützung für bestimmte XML-Codierungstypen fungiert.  
  
-   Folgende Schlüsselmethoden dieser Klasse müssen außer Kraft gesetzt werden:  
  
-   <xref:System.ServiceModel.Channels.MessageEncoder.WriteMessage%2A>: nimmt ein <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>-Objekt an und schreibt es in ein <xref:System.IO.Stream>-Objekt.  
  
-   <xref:System.ServiceModel.Channels.MessageEncoder.ReadMessage%2A>: nimmt ein <xref:System.IO.Stream>-Objekt sowie eine maximale Headergröße an und gibt ein <xref:System.ServiceModel.Channels.Message>-Objekt zurück.  
  
 Die Umwandlung zwischen dem standardmäßigen Transportprotokoll und der benutzerdefinierten Codierung wird anhand des in diese Methoden geschriebenen Codes behandelt.  
  
 Der nächste Schritt besteht im Codieren einer Factoryklasse zum Erstellen des benutzerdefinierten Encoders. Überschreiben Sie den <xref:System.ServiceModel.Channels.MessageEncoderFactory.Encoder%2A>, um eine Instanz des benutzerdefinierten <xref:System.ServiceModel.Channels.MessageEncoder> zurückzugeben.  
  
 Verbinden Sie anschließend die benutzerdefinierte <xref:System.ServiceModel.Channels.MessageEncoderFactory> mit dem Bindungselementstapel für die Konfiguration des Diensts oder des Clients durch Überschreiben der <xref:System.ServiceModel.Channels.MessageEncodingBindingElement.CreateMessageEncoderFactory%2A>-Methode, um eine Instanz der Factory zurückzugeben.  
  
 Es gibt zwei Beispiele mit WCF bereitgestellt, in denen dieser Prozess mit Beispielcode veranschaulicht: [benutzerdefinierter Nachrichtenencoder: benutzerdefinierter Textencoder](../../../../docs/framework/wcf/samples/custom-message-encoder-custom-text-encoder.md) und [benutzerdefinierter Nachrichtenencoder: Komprimierungsencoder](../../../../docs/framework/wcf/samples/custom-message-encoder-compression-encoder.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.MessageEncoderFactory>  
 <xref:System.ServiceModel.Channels.MessageEncoder>  
 [Datenübertragungsarchitektur: Übersicht](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md)  
 [Auswählen eines Nachrichtenencoders](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [Auswählen eines Transports](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)

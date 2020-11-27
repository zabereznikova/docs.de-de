---
title: Datenübertragungsarchitektur - Übersicht
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data transfer [WCF], architectural overview
ms.assetid: 343c2ca2-af53-4936-a28c-c186b3524ee9
ms.openlocfilehash: efb6933ba90975d5ba35deb2bf22af12fc7c2cdc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291686"
---
# <a name="data-transfer-architectural-overview"></a>Datenübertragungsarchitektur - Übersicht

Windows Communication Foundation (WCF) kann als Messaging Infrastruktur betrachtet werden. Damit können Nachrichten empfangen, verarbeitet und für weitere Aktionen an Benutzercode verteilt werden, oder es können Nachrichten anhand von Daten des Benutzercodes erstellt und an ein Ziel übergeben werden. In diesem Thema, das sich an fortgeschrittene Entwickler richtet, wird die Architektur zur Verarbeitung von Nachrichten und der darin enthaltenen Daten beschrieben. Eine einfachere, funktionsbezogene Betrachtung zum Senden und Empfangen von Daten finden Sie unter [Specifying Data Transfer in Service Contracts](specifying-data-transfer-in-service-contracts.md).  
  
> [!NOTE]
> In diesem Thema werden WCF-Implementierungsdetails erläutert, die durch Untersuchen des WCF-Objektmodells nicht sichtbar sind. Zwei Hinweise im Hinblick auf die dokumentierten Implementierungsdetails sind wichtig. Zunächst einmal sind die Beschreibungen vereinfacht dargestellt; die tatsächliche Implementierung ist möglicherweise aufgrund von Optimierungen oder aus anderen Gründen komplexer. Zweitens: Sie sollten sich nie auf bestimmte Implementierungsdetails verlassen, auch nicht auf die dokumentierten, da sich diese ohne Vorankündigung von Version zu Version oder sogar innerhalb eines Service Release ändern können.  
  
## <a name="basic-architecture"></a>Grundlegende Architektur  

 Das Herzstück der WCF-Nachrichten Behandlungs Funktionen ist die- <xref:System.ServiceModel.Channels.Message> Klasse, die ausführlich unter [Verwenden der Message-Klasse](using-the-message-class.md)beschrieben wird. Die Laufzeitkomponenten von WCF können in zwei Hauptteile unterteilt werden: den Kanal Stapel und das Dienst Framework, wobei die <xref:System.ServiceModel.Channels.Message> Klasse der Verbindungspunkt ist.  
  
 Der Kanalstapel ist für die Konvertierung zwischen einer gültigen <xref:System.ServiceModel.Channels.Message> -Instanz und einer Aktion verantwortlich, die dem Senden und Empfangen von Nachrichtendaten entspricht. Auf der Absenderseite verwendet der Kanalstapel eine gültige <xref:System.ServiceModel.Channels.Message> -Instanz und führt nach einigen Verarbeitungsschritten eine Aktion aus, die logisch dem Senden der Nachricht entspricht. Bei der Aktion kann es sich um das Senden von TCP- oder HTTP-Paketen, das Senden der Nachricht an die Warteschlange von Message Queuing, das Schreiben der Nachricht in eine Datenbank, das Speichern in einer Dateifreigabe oder, je nach Implementierung, um eine andere Aktion handeln. Die am häufigsten verwendete Aktion ist das Senden der Nachricht über ein Netzwerkprotokoll. Auf der Empfängerseite geschieht genau das Gegenteil: Eine Aktion wird erkannt (dabei kann es sich um das Eintreffen von TCP- oder HTTP-Paketen oder eine andere Aktion handeln) und nach der Verarbeitung vom Kanalstapel in eine gültige <xref:System.ServiceModel.Channels.Message> -Instanz umgewandelt.  
  
 Sie können WCF verwenden, indem Sie die <xref:System.ServiceModel.Channels.Message> -Klasse und den Kanal Stapel direkt verwenden. Dies ist jedoch schwierig und zeitaufwändig. Außerdem bietet das- <xref:System.ServiceModel.Channels.Message> Objekt keine Metadatenunterstützung, sodass Sie keine stark typisierten WCF-Clients generieren können, wenn Sie WCF auf diese Weise verwenden.  
  
 WCF enthält daher ein Dienst Framework, das ein benutzerfreundliches Programmiermodell bereitstellt, das Sie zum Erstellen und empfangen von-Objekten verwenden können `Message` . Das Dienst Framework ordnet Dienste .NET Framework Typen über das Konzept von Dienstverträgen zu und sendet Nachrichten an Benutzer Vorgänge, bei denen es sich einfach um .NET Framework mit dem-Attribut markierten Methoden handelt <xref:System.ServiceModel.OperationContractAttribute> (Weitere Informationen finden Sie unter [Entwerfen von Dienstverträgen](../designing-service-contracts.md)). Diese Methoden verwenden möglicherweise Parameter und Rückgabewerte. Auf der Dienstseite wandelt das Dienstframework eingehende <xref:System.ServiceModel.Channels.Message> -Instanzen in Parameter um und Rückgabewerte in ausgehende <xref:System.ServiceModel.Channels.Message> -Instanzen. Auf der Clientseite findet das Gegenteil statt. Betrachten Sie z.&#160;B. den nachfolgenden `FindAirfare` -Vorgang.  
  
 [!code-csharp[c_DataArchitecture#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_dataarchitecture/cs/source.cs#1)]
 [!code-vb[c_DataArchitecture#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_dataarchitecture/vb/source.vb#1)]  
  
 Nehmen wir an, auf dem Client wird `FindAirfare` aufgerufen. Das Dienstframework auf dem Client wandelt die `FromCity` -Parameter und `ToCity` - Parameter in eine ausgehende <xref:System.ServiceModel.Channels.Message> -Instanz um und übergibt diese an den zu sendenden Kanalstapel.  
  
 Wenn auf der Dienstseite eine <xref:System.ServiceModel.Channels.Message> -Instanz vom Kanalstapel ankommt, extrahiert das Dienstframework die relevanten Daten aus der Nachricht, um die `FromCity` -Parameter und `ToCity` -Parameter zu füllen, und ruft dann die dienstseitige `FindAirfare` -Methode auf. Wenn die Methode zurückgegeben wird, verwendet das Dienstframework den zurückgegebenen Ganzzahlwert und den `IsDirectFlight` -Ausgabeparameter und erstellt eine <xref:System.ServiceModel.Channels.Message> -Objektinstanz, die diese Informationen enthält. Es übergibt dann die `Message` -Instanz an den Kanalstapel, damit sie an den Client zurückgesendet wird.  
  
 Auf der Clientseite entsteht eine <xref:System.ServiceModel.Channels.Message> -Instanz, die die Antwortmeldung vom Kanalstapel enthält. Das Dienstframework extrahiert den Rückgabewert und den `IsDirectFlight` -Wert und gibt diese an den Aufrufer des Clients zurück.  
  
## <a name="message-class"></a>Nachrichtenklasse  

 Die <xref:System.ServiceModel.Channels.Message> -Klasse soll eine abstrakte Darstellung einer Nachricht sein, ihre Struktur ist jedoch eng mit der SOAP-Nachricht verbunden. Eine <xref:System.ServiceModel.Channels.Message> enthält drei Hauptinformationen: einen Nachrichtentext, Nachrichtenheader und Nachrichteneigenschaften.  
  
## <a name="message-body"></a>Nachrichtentext  

 Der Nachrichtentext soll die tatsächliche Datennutzlast der Nachricht darstellen. Der Nachrichtentext wird immer als XML-Infoset dargestellt. Dies bedeutet nicht, dass alle Nachrichten, die in WCF erstellt oder empfangen werden, im XML-Format vorliegen müssen. Es obliegt dem Kanalstapel, zu entscheiden, wie der Nachrichtentext interpretiert wird. Er wird eventuell als XML ausgegeben, in ein anderes Format konvertiert oder sogar ganz weggelassen. Natürlich wird bei den meisten Bindungen, die WCF bereitstellt, der Nachrichtentext als XML-Inhalt im Textabschnitt eines SOAP-Umschlags dargestellt.  
  
 Ihnen sollte auf jeden Fall bewusst sein, dass die `Message` -Klasse nicht unbedingt einen Puffer mit XML-Daten enthält, die den Textkörper darstellen. `Message` enthält zwar ein XML-Infoset, dieser Infoset wurde jedoch eventuell dynamisch erstellt und ist im Speicher gar nicht physisch vorhanden.  
  
### <a name="putting-data-into-the-message-body"></a>Einfügen von Daten in den Nachrichtentext  

 Es gibt kein einheitliches Verfahren zum Einfügen von Daten in einen Nachrichtentext. Die <xref:System.ServiceModel.Channels.Message> -Klasse bietet eine abstrakte Methode, <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%28System.Xml.XmlDictionaryWriter%29>, die <xref:System.Xml.XmlDictionaryWriter>akzeptiert. Jede Unterklasse der <xref:System.ServiceModel.Channels.Message> -Klasse ist für das Überschreiben dieser Methode und Schreiben ihres eigenen Inhalts verantwortlich. Der Nachrichtentext enthält den XML-Infoset, der `OnWriteBodyContent` erzeugt, logisch. Betrachten Sie beispielsweise die folgende `Message` -Unterklasse:  
  
 [!code-csharp[c_DataArchitecture#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_dataarchitecture/cs/source.cs#2)]
 [!code-vb[c_DataArchitecture#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_dataarchitecture/vb/source.vb#2)]  
  
 Physisch enthält eine `AirfareRequestMessage` -Instanz nur zwei Zeichenfolgen ("fromCity" und "toCity"). Logisch enthält die Nachricht jedoch den folgenden XML-Infoset:  
  
```xml  
<airfareRequest>  
    <from>Tokyo</from>  
    <to>London</to>  
</airfareRequest>  
```  
  
 Selbstverständlich würden Sie im Normalfall keine Nachrichten auf diese Weise erstellen, da Sie zum Erstellen einer Nachricht wie der vorhergehenden aus Vorgangsvertragsparametern das Dienstframework verwenden können. Darüber hinaus bietet die <xref:System.ServiceModel.Channels.Message> -Klasse statische `CreateMessage` -Methoden, mit denen Sie Nachrichten mit häufig verwendeten Inhaltstypen erstellen können: eine leere Nachricht, eine Nachricht mit einem mit <xref:System.Runtime.Serialization.DataContractSerializer>XML-serialisierten Objekt, eine Nachricht, die einen SOAP-Fehler enthält, eine Nachricht, die durch <xref:System.Xml.XmlReader>dargestelltes XML enthält usw.  
  
### <a name="getting-data-from-a-message-body"></a>Abrufen von Daten aus einem Nachrichtentext  

 Sie können die in einem Nachrichtentext gespeicherten Daten auf zwei Arten extrahieren:  
  
- Sie können den gesamten Nachrichtentext einmalig abrufen, indem Sie die <xref:System.ServiceModel.Channels.Message.WriteBodyContents%28System.Xml.XmlDictionaryWriter%29> -Methode aufrufen und einen XML-Writer übergeben. Der vollständige Nachrichtentext wird an diesen Writer ausgeschrieben. Das einmalige Abrufen des gesamten Nachrichtentexts wird auch als *Schreiben einer Nachricht* bezeichnet. Das Schreiben wird hauptsächlich beim Senden der Nachrichten vom Kanalstapel übernommen. Ein Teil des Kanalstapels erhält in der Regel Zugriff auf den gesamten Nachrichtentext, codiert diesen und sendet ihn.  
  
- Eine weitere Methode zum Abrufen von Informationen aus dem Nachrichtentext besteht im Aufrufen von <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents> und Abrufen eines XML-Lesers. Auf den Nachrichtentext kann dann nacheinander nach Bedarf zugegriffen werden, indem Methoden im Reader aufgerufen werden. Das Abrufen des Nachrichtentexts Stück für Stück wird auch als *Lesen einer Nachricht* bezeichnet. Das Lesen der Nachricht wird hauptsächlich beim Empfangen von Nachrichten vom Dienstframework verwendet. Wenn z.&#160;B. <xref:System.Runtime.Serialization.DataContractSerializer> verwendet wird, lässt das Dienstframework einen XML-Leser über den Nachrichtentext laufen und übergibt ihn dann an die Deserialisierungs-Engine, die dann mit dem Lesen der Nachricht Element für Element und mit dem Erstellen des entsprechenden Objektdiagramms beginnt.  
  
 Ein Nachrichtentext kann nur einmalig abgerufen werden. Dies macht es möglich, mit Vorwärtsstreams zu arbeiten. So können Sie z.&#160;B. eine <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%28System.Xml.XmlDictionaryWriter%29> -Überschreibung schreiben, die aus <xref:System.IO.FileStream> liest und die Ergebnisse als XML-Infoset zurückgibt. Sie müssen niemals an den Anfang der Datei "Zurückspulen".  
  
 Die `WriteBodyContents` -Methode und `GetReaderAtBodyContents` -Methode prüfen einfach, ob der Nachrichtentext schon zuvor einmal abgerufen wurde, und rufen dann `OnWriteBodyContents` oder `OnGetReaderAtBodyContents`auf.  
  
## <a name="message-usage-in-wcf"></a>Nachrichtenverwendung in WCF  

 Die meisten Nachrichten können entweder als *ausgehend* (diejenigen, die vom Dienstframework zum Senden vom Kanalstapel erstellt werden) oder *eingehend* (diejenigen, die vom Kanalstapel eingehen und vom Dienstframework interpretiert werden) klassifiziert werden. Weiterhin kann der Kanalstapel entweder im gepufferten oder Streamingmodus operieren. Das Dienstframework kann auch ein per Streaming oder nicht per Streaming übertragenes Programmiermodell verfügbar machen. Dies führt zu den in der folgenden Tabelle aufgelisteten Fällen, zusammen mit vereinfachten Details ihrer Implementierung.  
  
|Nachrichtentyp|Textdaten in Nachricht|Write-Implementierung (OnWriteBodyContents)|Read-Implementierung (OnGetReaderAtBodyContents)|  
|------------------|--------------------------|--------------------------------------------------|-------------------------------------------------------|  
|Ausgehend, erstellt von nicht per Streaming übertragenem Programmiermodell|Die zum Schreiben der Nachricht benötigten Daten (z.&#160;B. ein Objekt und die zum Serialisieren benötigte <xref:System.Runtime.Serialization.DataContractSerializer> -Instanz)*|Eine benutzerdefinierte Logik zum Schreiben der Nachricht basierend auf den gespeicherten Daten (z. .B Aufruf von `WriteObject` am `DataContractSerializer` , falls dies das verwendete Serialisierungsprogramm ist)*|Aufrufen von `OnWriteBodyContents`, Puffern der Ergebnisse, Ausgeben eines XML-Lesers über den Puffer|  
|Ausgehend, erstellt von per Streaming übertragenem Programmiermodell|Der `Stream` mit den zu schreibenden Daten*|Schreiben von Daten vom gespeicherten Stream mit dem <xref:System.Xml.IStreamProvider> -Mechanismus *|Aufrufen von `OnWriteBodyContents`, Puffern der Ergebnisse, Ausgeben eines XML-Lesers über den Puffer|  
|Eingehend von Streamingkanalstapel|Ein `Stream` -Objekt, das die Daten darstellt, die über das Netzwerk mit einem darauf angewendeten <xref:System.Xml.XmlReader> eingehen|Ausschreiben des Inhalts aus dem gespeicherten `XmlReader` mit `WriteNode`|Gibt den gespeicherten `XmlReader`zurück|  
|Eingehend von nicht per Streaming übertragenem Kanalstapel|Ein Puffer, der Textdaten enthält, mit einem darauf angewendeten `XmlReader`|Schreibt den Inhalt des gespeicherten `XmlReader` mit `WriteNode`aus|Gibt die gespeicherte Sprache zurück|  
  
 \* Diese Elemente werden nicht direkt in `Message` Unterklassen implementiert, sondern in Unterklassen der- <xref:System.ServiceModel.Channels.BodyWriter> Klasse. Weitere Informationen zum <xref:System.ServiceModel.Channels.BodyWriter>finden Sie unter [Using the Message Class](using-the-message-class.md).  
  
## <a name="message-headers"></a>Nachrichtenheader  

 Eine Nachricht enthält möglicherweise Header. Ein Header besteht logisch aus einem XML-Infoset, der einem Namen, einem Namespace und einigen anderen Eigenschaften zugeordnet ist. Auf Nachrichtenheader wird mit der `Headers` -Eigenschaft auf <xref:System.ServiceModel.Channels.Message>zugegriffen. Jeder Header wird durch eine <xref:System.ServiceModel.Channels.MessageHeader> -Klasse dargestellt. In der Regel sind Nachrichtenheader SOAP-Nachrichtenheadern zugeordnet, wenn ein Kanalstapel verwendet wird, der für SOAP-Nachrichten konfiguriert ist.  
  
 Das Einfügen von Informationen in einen Nachrichtenheader und das Extrahieren von Daten daraus ähnelt der Verwendung des Nachrichtentexts. Der Prozess wird ein wenig vereinfacht, da das Streaming nicht unterstützt wird. Es ist möglich, auf den Inhalt desselben Headers mehr als einmal zuzugreifen. Auf die Header kann auch in willkürlicher Reihenfolge zugegriffen werden. Die Header werden dadurch gezwungen, immer gepuffert zu sein. Es ist kein allgemeiner Mechanismus verfügbar, um einen XML-Reader über einen Header zu erhalten, aber es gibt eine `MessageHeader` interne Unterklasse von WCF, die einen lesbaren Header mit einer solchen Funktion darstellt. Diese Art von `MessageHeader` wird vom Kanalstapel erstellt, wenn eine Nachricht mit benutzerdefinierten Anwendungsheadern eingeht. So kann das Dienstframework eine Deserialisierungs-Engine, z.B. den <xref:System.Runtime.Serialization.DataContractSerializer>, zum Interpretieren dieser Header verwenden.  
  
 Weitere Informationen finden Sie unter [Verwenden der Message-Klasse](using-the-message-class.md).  
  
## <a name="message-properties"></a>Nachrichteneigenschaften  

 Eine Nachricht kann Eigenschaften enthalten. Eine *Eigenschaft* ist ein beliebiges .NET Framework Objekt, das einem Zeichen folgen Namen zugeordnet ist. Der Zugriff erfolgt über die `Properties` -Eigenschaft von `Message`.  
  
 Im Gegensatz zum Nachrichtentext und den Nachrichtenheadern (die in der Regel dem SOAP-Text und den SOAP-Headern zugeordnet sind) werden Nachrichteneigenschaften in der Regel nicht zusammen mit den Nachrichten gesendet oder empfangen. Nachrichteneigenschaften existieren hauptsächlich als Kommunikationsmechanismus zum Übergeben von Daten über die Nachricht zwischen den verschiedenen Kanälen im Kanalstapel und zwischen dem Kanalstapel und dem Dienstmodell.  
  
 Beispielsweise kann der als Teil von WCF enthaltene HTTP-Transport Kanal verschiedene HTTP-Statuscodes erzeugen, z. b. "404 (nicht gefunden)" und "500 (interner Server Fehler)", wenn Antworten an Clients gesendet werden. Vor dem Senden einer Antwortnachricht wird überprüft, ob die `Properties` der- `Message` Eigenschaft eine Eigenschaft mit dem Namen "HttpResponse" enthält, die ein Objekt vom Typ enthält <xref:System.ServiceModel.Channels.HttpResponseMessageProperty> . Wird eine solche Eigenschaft gefunden, wird die <xref:System.ServiceModel.Channels.HttpResponseMessageProperty.StatusCode%2A> -Eigenschaft geprüft und dieser Statuscode verwendet. Andernfalls wird der Standardcode "200 (OK)" verwendet.  
  
 Weitere Informationen finden Sie unter [Verwenden der Message-Klasse](using-the-message-class.md).  
  
### <a name="the-message-as-a-whole"></a>Die Nachricht als Ganzes  

 Bis jetzt wurden Methoden für den Zugriff auf die verschiedenen Bestandteile der Nachricht isoliert erläutert. Die <xref:System.ServiceModel.Channels.Message> -Klasse stellt jedoch auch Methoden bereit, die mit der Nachricht als Ganzes ausgeführt werden. Die folgende `WriteMessage` -Methode schreibt z. B. die gesamte Nachricht in einen XML-Writer.  
  
 Damit dies möglich ist, muss zwischen der gesamten `Message` -Instanz und einem XML-Infoset eine Zuordnung definiert werden. Eine solche Zuordnung ist tatsächlich vorhanden: WCF verwendet den SOAP-Standard, um diese Zuordnung zu definieren. Wenn eine `Message` -Instanz als XML-Infoset geschrieben wird, ist der daraus resultierende Infoset der gültige SOAP-Umschlag, der die Nachricht enthält. So würde `WriteMessage` normalerweise die folgenden Schritte ausführen:  
  
1. Schreiben des öffnenden SOAP-Umschlagelementtags.  
  
2. Schreiben des öffnenden SOAP-Headerelementtags, Schreiben aller Header und Schließen des Headerelements.  
  
3. Schreiben des öffnenden SOAP-Textkörperelementtags.  
  
4. Aufrufen von `WriteBodyContents` oder einer entsprechenden Methode zum Schreiben des Texts.  
  
5. Schließen der Text- und Umschlagelemente.  
  
 Die vorhergehenden Schritte sind eng an den SOAP-Standard gebunden. Dies wird durch die Tatsache komplizierter, dass mehrere SOAP-Versionen vorhanden sind. So ist es z.&#160;B. möglich, das SOAP-Umschlagelement richtig zu schreiben, ohne die verwendete SOAP-Version zu kennen. Auch in einigen Fällen ist es möglicherweise wünschenswert, diese komplexe SOAP-spezifische Zuordnung völlig auszuschalten.  
  
 Für diese Zwecke wird eine `Version` -Eigenschaft für `Message`bereitgestellt. Sie kann auf die SOAP-Version festgelegt werden, die beim Schreiben der Nachricht verwendet wird, oder sie kann auf `None` festgelegt werden, um SOAP-spezifische Zuordnungen zu verhindern. Falls die `Version` -Eigenschaft auf `None`festgelegt ist, funktionieren Methoden, die mit der gesamten Nachricht arbeiten, so, als ob die Nachricht lediglich aus dem Textkörper besteht. So würde z.&#160;B. `WriteMessage` einfach `WriteBodyContents` aufrufen, und die oben beschriebenen Schritte werden nicht ausgeführt. Es wird erwartet, dass `Version` in eingehenden Nachrichten automatisch erkannt und ordnungsgemäß festgelegt wird.  
  
## <a name="the-channel-stack"></a>Der Kanalstapel  
  
### <a name="channels"></a>Kanäle  

 Wie zuvor bereits beschrieben, ist der Kanalstapel für die Umwandlung von ausgehenden <xref:System.ServiceModel.Channels.Message> -Instanzen in eine Aktion (wie Senden von Paketen über das Netzwerk) oder Umwandeln einer Aktion (wie Empfangen von Netzwerkpakten) in eingehende `Message` -Instanzen verantwortlich.  
  
 Der Kanalstapel besteht aus einem oder aus mehreren Kanälen, die in einer Sequenz angeordnet sind. Eine ausgehende `Message` -Instanz wird an den ersten Kanal im Stapel (auch als *oberster Kanal* bezeichnet) übergeben, der sie wiederum an den nächsten Kanal im Stapel übergibt usw. Die Nachricht endet im letzten Kanal, der als *Transportkanal* bezeichnet wird. Eingehende Nachrichten stammen aus dem Transportkanal und werden von Kanal zu Kanal nach oben im Stapel übergeben. Vom obersten Kanal wird die Nachricht normalerweise in das Dienstframework übergeben. Dies ist das Muster für Anwendungsnachrichten, das in der Regel verwendet wird. Einige Kanäle funktionieren eventuell anders. Sie senden z.&#160;B. eigene Infrastrukturnachrichten, ohne eine Nachricht von einem oben beschriebenen Kanal zu erhalten.  
  
 Die Kanäle wirken möglicherweise auf verschiedene Weise auf die Nachricht, die durch den Stapel geleitet wird. Der am häufigsten verwendete Vorgang besteht im Hinzufügen eines Headers zu einer ausgehenden Nachricht sowie im Lesen der Header einer eingehenden Nachricht. So kann ein Kanal z.&#160;B. die digitale Signatur einer Nachricht berechnen und sie als Header hinzufügen. Ein Kanal kann diesen digitalen Signaturheader in eingehenden Nachrichten auch prüfen und Nachrichten, die keine gültige Signatur enthalten, auf ihrem Weg durch den Kanalstapel blockieren. Kanäle legen auch häufig Nachrichteneigenschaften fest oder prüfen diese. Der Nachrichtentext wird in der Regel nicht geändert, obwohl dies zulässig ist, z. b. kann der WCF-Sicherheits Kanal den Nachrichtentext verschlüsseln.  
  
### <a name="transport-channels-and-message-encoders"></a>Transportkanäle und Nachrichtenencoder  

 Der Kanal, der sich im Stapel ganz unten befindet, ist für die Übertragung einer ausgehenden <xref:System.ServiceModel.Channels.Message>-Nachricht, die von anderen Kanälen geändert wurde, in eine Aktion verantwortlich. Auf Empfängerseite ist dies der Kanal, der eine Aktion in eine `Message` umwandelt, die von anderen Kanälen verarbeitet wird.  
  
 Wie zuvor bereits erläutert kann es sich um verschiedene Aktionen handeln: Senden oder Empfangen von Netzwerkpaketen über verschiedene Protokolle, Lesen und Schreiben der Nachricht in einer Datenbank oder Ablegen oder Abrufen der Nachricht aus einer Warteschlange von Message Queuing, um nur einige Beispiele zu nennen. Alle diese Aktionen haben einen gemeinsamen Vorgang: Sie erfordern eine Transformation zwischen der WCF `Message` -Instanz und einer tatsächlichen Gruppe von Bytes, die gesendet, empfangen, gelesen, geschrieben, in Warteschlangen eingereiht oder aus der Warteschlange entfernt werden können. Der Vorgang des Umwandelns einer `Message` in eine Gruppe von Bytes wird als *Codieren* bezeichnet, und der umgekehrte Vorgang des Erstellens einer `Message` aus einer Gruppe von Bytes wird als *Decodieren* bezeichnet.  
  
 Die meisten Transportkanäle verwenden Komponenten, die als *Nachrichtenencoder* bezeichnet werden, um die Codierung und Decodierung durchzuführen. Ein Nachrichtenencoder ist eine Unterklasse der <xref:System.ServiceModel.Channels.MessageEncoder> -Klasse. `MessageEncoder` umfasst verschiedene `ReadMessage` - und `WriteMessage` -Methodenüberladungen, um eine Konvertierung zwischen `Message` und Gruppen von Bytes durchzuführen.  
  
 Auf der Absenderseite übergibt ein Puffertransportkanal das `Message` -Objekt, das es von einem Kanal darüber erhalten hat, an `WriteMessage`. Es erhält ein Bytearray zurück, das zum Durchführen der Aktion (wie Packen dieser Bytes als gültige TCP-Pakete und Senden an das richtige Ziel) verwendet wird. Ein Streaming-Transportkanal erstellt zunächst einen `Stream` (z.&#160;B. für die ausgehende TCP-Verbindung) und übergibt dann sowohl den `Stream` als auch die `Message` an die entsprechende `WriteMessage` -Überladung, welche die Nachricht schreibt.  
  
 Auf der Empfängerseite extrahiert ein Puffertransportkanal eingehende Bytes (z.&#160;B. aus eingehenden TCP-Paketen) in ein Array und ruft `ReadMessage` auf, um ein `Message` -Objekt abzurufen, das im Kanalstapel weiter nach oben übergeben werden kann. Ein Streamingtransportkanal erstellt ein `Stream` -Objekt (z.&#160;B. einen Netzwerkstream über die eingehende TCP-Verbindung) und übergibt dieses an `ReadMessage` , um ein `Message` -Objekt zu erhalten.  
  
 Die Trennung zwischen den Transportkanälen und dem Nachrichtenencoder ist nicht erforderlich. Es ist möglich, einen Transportkanal zu schreiben, der keinen Nachrichtenencoder verwendet. Der Vorteil dieser Trennung liegt jedoch in der einfachen Zusammensetzung. Solange ein Transport Kanal nur den Basis <xref:System.ServiceModel.Channels.MessageEncoder> -verwendet, kann er mit jedem WCF-oder Drittanbieter-Nachrichten Encoder arbeiten. Ebenso kann der gleiche Encoder normalerweise in jedem Transportkanal verwendet werden.  
  
### <a name="message-encoder-operation"></a>Nachrichtenencodervorgang  

 Um den typischen Vorgang eines Encoders zu beschreiben, ist es nützlich, die folgenden vier Fälle zu betrachten.  
  
|Vorgang|Kommentar|  
|---------------|-------------|  
|Codierung, gepuffert|Im gepufferten Modus erstellt der Encoder in der Regel einen Puffer in verschiedenen Größen und dann einen XML-Writer dafür. Er ruft dann <xref:System.ServiceModel.Channels.Message.WriteMessage%28System.Xml.XmlWriter%29> für die codierte Nachricht auf. Dadurch werden die Header ausgeschrieben und anschließend der Textkörper mithilfe von <xref:System.ServiceModel.Channels.Message.WriteBodyContents%28System.Xml.XmlDictionaryWriter%29>, wie im folgenden Abschnitt über `Message` in diesem Thema beschrieben. Der Inhalt des Puffers (dargestellt als Bytearray) wird dann für die Verwendung vom Transportkanal zurückgegeben.|  
|Codierung, per Streaming übertragen|Im Streammodus ist der Vorgang ähnlich wie der oben beschriebene, aber einfacher. Es ist kein Puffer erforderlich. Für den Stream wird in der Regel ein XML-Writer erstellt und <xref:System.ServiceModel.Channels.Message.WriteMessage%28System.Xml.XmlWriter%29> für `Message` aufgerufen, um für diesen Writer zu schreiben.|  
|Decodierung, gepuffert|Wenn Sie im Puffermodus decodieren, wird eine besondere `Message` -Unterklasse erstellt, die die gepufferten Daten enthält. Die Header der Nachricht werden gelesen, und ein XML-Leser, der sich im Nachrichtentext befindet, wird erstellt. Dies ist der Leser, der mit <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents>zurückgegeben wird.|  
|Decodierung, per Streaming übertragen|Wenn Sie im Streammodus decodieren, wird in der Regel eine besondere Nachrichtenunterklasse erstellt. Der Stream wird gerade so weit bewegt, dass alle Header gelesen werden können und er im Nachrichtentext positioniert wird. Ein XML-Leser wird dann über dem Datenstrom erstellt. Dies ist der Leser, der mit <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents>zurückgegeben wird.|  
  
 Encoder können auch andere Funktionen ausführen. Zum Beispiel können die Encoder XML-Leser und -Writer zusammenlegen. Es ist teuer, jedes Mal einen neuen XML-Leser oder -Writer zu erstellen, wenn einer benötigt wird. Deshalb verwalten Encoder normalerweise einen Pool von Lesern und einen Pool von Writern in konfigurierbaren Größen. In den zuvor beschriebenen Beschreibungen des Codierungs Vorgangs bedeutet dies, dass immer dann, wenn der Ausdruck "Create a XML Reader/Writer" verwendet wird, normalerweise "nehmen Sie einen aus dem Pool nehmen oder einen erstellen, wenn ein solcher nicht verfügbar ist". Der Encoder (und die `Message` -Unterklassen, die er beim Decodieren erstellt) enthält Logik zum Zurückgeben von Lesern und Schreibern an den Pool, wenn sie nicht mehr benötigt werden (z. B. wenn die `Message` geschlossen wird).  
  
 WCF stellt drei Nachrichten Encoder zur Verfügung, obwohl es möglich ist, zusätzliche benutzerdefinierte Typen zu erstellen. Die angegebenen Typen sind Text, Binärdatei und MTOM (Message Transmission Optimization Mechanism, Nachrichtenübertragungs-Optimierungsmechanismus). Diese werden detailliert unter [Choosing a Message Encoder](choosing-a-message-encoder.md)beschrieben.  
  
### <a name="the-istreamprovider-interface"></a>Die IStreamProvider-Schnittstelle  

 Wenn eine ausgehende Nachricht, die einen in einem Stream befindlichen Hauptteil enthält, in einen XML-Writer geschrieben wird, verwendet <xref:System.ServiceModel.Channels.Message> eine Aufrufsequenz, die der folgenden Sequenz in ihrer <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%28System.Xml.XmlDictionaryWriter%29> -Implementierung ähnlich ist:  
  
- Schreiben Sie alle notwendigen Informationen, die dem Stream vorausgehen (z. B. das öffnende XML-Tag).  
  
- Schreiben Sie den Stream.  
  
- Schreiben Sie alle Informationen, die nach dem Stream folgen (z.&#160;B. das schließende XML-Tag).  
  
 Dies funktioniert gut bei Codierungen, die der Text-XML-Codierung ähnlich sind. Es gibt jedoch einige Codierungen, bei denen XML-Infosetinformationen (z.&#160;B. Tags für beginnende und endende XML-Elemente) nicht zusammen mit den in den Elementen enthaltenen Daten platziert werden. Zum Beispiel wird bei der MTOM-Codierung die Nachricht in mehrere Teile aufgeteilt. Ein Teil enthält den XML-Infoset, der in Bezug auf tatsächlichen Elementinhalt Verweise auf andere Teile enthalten kann. Da der XML-Infoset für gewöhnlich kleiner ist als der im Stream befindliche Inhalt, bietet es sich an, den Infoset zu puffern, ihn auszuschreiben und dann den Inhalt gestreamt zu schreiben. Dies bedeutet, dass zu dem Zeitpunkt, zu dem das Tag für das schließende Element geschrieben wird, der Stream noch nicht ausgeschrieben sein sollte.  
  
 Zu diesem Zweck wird die <xref:System.Xml.IStreamProvider> -Schnittstelle verwendet. Die Schnittstelle verfügt über eine <xref:System.Xml.IStreamProvider.GetStream> -Methode, die den zu schreibenden Stream zurückgibt. Die richtige Vorgehensweise, um einen in einem Stream befindlichen Nachrichtentext in <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%28System.Xml.XmlDictionaryWriter%29> auszuschreiben, lautet wie folgt:  
  
1. Schreiben Sie alle notwendigen Informationen, die dem Stream vorausgehen (z. B. das öffnende XML-Tag).  
  
2. Rufen Sie die `WriteValue` -Überladung in <xref:System.Xml.XmlDictionaryWriter> auf, die <xref:System.Xml.IStreamProvider>mit einer `IStreamProvider` -Implementierung verwendet, die den zu schreibenden Stream zurückgibt.  
  
3. Schreiben Sie alle Informationen, die nach dem Stream folgen (z.&#160;B. das schließende XML-Tag).  
  
 Auf diese Weise kann der XML-Writer bestimmen, wann <xref:System.Xml.IStreamProvider.GetStream> aufgerufen wird und die im Stream befindlichen Daten ausgeschrieben werden. So rufen die Text-XML-Writer und die binären XML-Writer die Daten zum Beispiel direkt auf und schreiben den im Stream befindlichen Inhalt zwischen die Start- und Endtags. Der MTOM-Writer ruft <xref:System.Xml.IStreamProvider.GetStream> möglicherweise erst dann auf, wenn er zum Schreiben des entsprechenden Nachrichtenteils bereit ist.  
  
## <a name="representing-data-in-the-service-framework"></a>Darstellen von Daten im Dienstframework  

 Wie im Abschnitt "grundlegende Architektur" in diesem Thema erwähnt, ist das Dienst Framework der Teil von WCF, der unter anderem für die Umstellung zwischen einem benutzerfreundlichen Programmiermodell für Nachrichten Daten und tatsächliche Instanzen zuständig ist `Message` . Normalerweise wird ein Nachrichtenaustausch im Dienst Framework als .NET Framework Methode dargestellt, die mit dem- <xref:System.ServiceModel.OperationContractAttribute> Attribut gekennzeichnet ist. Die Methode kann einige Parameter ausführen und einen Rückgabewert oder out-Parameter (oder beides) zurückgeben. Auf der Dienstseite stellen die Eingabeparameter die eingehende Nachricht dar. Der Rückgabewert und die out-Parameter stellen die ausgehende Nachricht dar. Auf der Clientseite gilt das Gegenteil. Das Programmiermodell zum Beschreiben von Nachrichten mithilfe von Parametern und Rückgabewert wird ausführlich unter [Specifying Data Transfer in Service Contracts](specifying-data-transfer-in-service-contracts.md)beschrieben. Der folgende Abschnitt enthält jedoch eine kurze Übersicht.  
  
## <a name="programming-models"></a>Programmiermodelle  

 Das WCF-Dienst Framework unterstützt fünf verschiedene Programmier Modelle zum Beschreiben von Nachrichten:  
  
### <a name="1-the-empty-message"></a>1. Die leere Nachricht  

 Dies ist der einfachste Fall. Um eine leere eingehende Nachricht zu beschreiben, verwenden Sie keine Eingabeparameter.  
  
 [!code-csharp[C_DataArchitecture#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_dataarchitecture/cs/source.cs#3)]
 [!code-vb[C_DataArchitecture#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_dataarchitecture/vb/source.vb#3)]  
  
 Um eine leere ausgehende Nachricht zu beschreiben, verwenden Sie einen void-Rückgabewert:  
  
 [!code-csharp[C_DataArchitecture#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_dataarchitecture/cs/source.cs#4)]
 [!code-vb[C_DataArchitecture#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_dataarchitecture/vb/source.vb#4)]  
  
 Beachten Sie, dass sich dies von einem unidirektionalen Vorgangsvertrag unterscheidet:  
  
 [!code-csharp[C_DataArchitecture#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_dataarchitecture/cs/source.cs#5)]
 [!code-vb[C_DataArchitecture#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_dataarchitecture/vb/source.vb#5)]  
  
 Im `SetDesiredTemperature` -Beispiel wird ein bidirektionales Nachrichtenaustauschmuster beschrieben. Eine Nachricht wird vom Vorgang zurückgegeben, ist jedoch leer. Es ist möglich, einen Fehler vom Vorgang zurückzugeben. Im Beispiel "Set Lightbulb" ist das Nachrichtenaustauschmuster unidirektional. Es ist also keine ausgehende Nachricht vorhanden, die beschrieben werden müsste. Der Dienst kann dem Client in diesem Fall keinen Status mitteilen.  
  
### <a name="2-using-the-message-class-directly"></a>2. Direktes Verwenden der Nachrichtenklasse  

 Es ist möglich, die <xref:System.ServiceModel.Channels.Message> -Klasse (oder eine ihrer Unterklassen) direkt in einem Vertrag für einen Vorgang zu verwenden. In diesem Fall übergibt das Dienstframework `Message` einfach an den Kanalstapel und umgekehrt, ohne weitere Verarbeitung.  
  
 Es gibt zwei Hauptanwendungsfälle für das direkte Verwenden von `Message` . Sie können es für erweiterte Szenarien verwenden, wenn keines der anderen Programmiermodelle ausreichende Flexibilität zum Beschreiben Ihrer Nachricht bietet. So möchten Sie z.&#160;B. eventuell Dateien auf Festplatte zum Beschreiben einer Nachricht verwenden, wobei die Dateieigenschaften zu Nachrichtenheadern werden und der Dateiinhalt zum Nachrichtentext wird. Sie können dann Folgendes erstellen.  
  
 [!code-csharp[C_DataArchitecture#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_dataarchitecture/cs/source.cs#6)]
 [!code-vb[C_DataArchitecture#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_dataarchitecture/vb/source.vb#6)]  
  
 Der zweite häufige Anwendungsfall für `Message` in einem Vorgangsvertrag tritt ein, wenn ein Dienst den Inhalt einer bestimmten Nachricht ignoriert und die Nachricht wie eine Blackbox behandelt. Zum Beispiel könnten Sie über einen Dienst verfügen, der Nachrichten an mehrere andere Empfänger weiterleitet. Der Vertrag kann wie folgt geschrieben werden.  
  
 [!code-csharp[C_DataArchitecture#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_dataarchitecture/cs/source.cs#7)]
 [!code-vb[C_DataArchitecture#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_dataarchitecture/vb/source.vb#7)]  
  
 Die Zeile Action = "*" deaktiviert das Senden von Nachrichten und stellt sicher, dass alle an den Vertrag gesendeten Nachrichten `IForwardingService` den `ForwardMessage` Vorgang durchführen. (Normalerweise würde der Verteiler den "action"-Header der Nachricht untersuchen, um zu ermitteln, für welchen Vorgang er bestimmt ist. Action = " \* " bedeutet "alle möglichen Werte des Aktions Headers".) Die Kombination aus Action = " \* " und die Verwendung der Nachricht als Parameter wird als "Universal Contract" bezeichnet, da Sie alle möglichen Nachrichten empfangen kann. Um alle möglichen Nachrichten senden zu können, verwenden Sie Message als Rückgabewert, und legen `ReplyAction` Sie auf " \* " fest. Auf diese Weise wird verhindert, dass das Dienstframework einen eigenen Action-Header hinzufügt. So können Sie diesen Header mit dem zurückgegebenen `Message` -Objekt steuern.  
  
### <a name="3-message-contracts"></a>3. Nachrichtenverträge  

 WCF stellt ein deklaratives Programmiermodell zum Beschreiben von Nachrichten bereit, die so genannten *Nachrichten Verträge*. Dieses Modell wird in [Using Message Contracts](using-message-contracts.md)ausführlich beschrieben. Im Wesentlichen wird die gesamte Nachricht durch einen einzelnen .NET Framework Typ dargestellt, der Attribute wie <xref:System.ServiceModel.MessageBodyMemberAttribute> und verwendet <xref:System.ServiceModel.MessageHeaderAttribute> , um zu beschreiben, welche Teile der Nachrichten Vertrags Klasse welchem Teil der Nachricht zugeordnet werden sollen.  
  
 Nachrichtenverträge bieten einen hohen Steuerungsgrad hinsichtlich der resultierenden `Message` -Instanzen (obwohl offensichtlich nicht so viel Steuerung wie bei der direkten Verwendung der `Message` -Klasse). So bestehen Nachrichtentexte häufig aus mehreren Informationskomponenten, von denen jede durch ein XML-Element dargestellt ist. Diese Elemente können entweder direkt im Textkörper (*leerer* Modus) vorhanden oder in ein übergeordnetes XML-Element *eingeschlossen* sein. Mit dem Programmiermodell für Nachrichtenverträge können Sie zwischen dem leeren und eingeschlossenen Modus wählen und den Wrappernamen und Namespace steuern.  
  
 Im folgenden Codebeispiel eines Nachrichtenvertrags werden diese Funktionen veranschaulicht.  
  
 [!code-csharp[C_DataArchitecture#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_dataarchitecture/cs/source.cs#9)]
 [!code-vb[C_DataArchitecture#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_dataarchitecture/vb/source.vb#9)]  
  
 Für die Serialisierung (mit dem Attribut <xref:System.ServiceModel.MessageBodyMemberAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute>oder anderen verwandten Attributen) gekennzeichnete Elemente müssen serialisierbar sein, um an einem Nachrichtenvertrag teilzunehmen. Weitere Informationen finden Sie im Abschnitt "Serialisierung" weiter unten in diesem Thema.  
  
### <a name="4-parameters"></a>4. Parameter  

 Häufig benötigt ein Entwickler, der einen Vorgang beschreiben möchte, der für mehrere Datenpakete gilt, nicht den Steuerungsgrad, den Nachrichtenverträge bieten. So muss z.&#160;B. beim Erstellen von neuen Diensten keine Entscheidung zwischen leer und eingeschlossen getroffen und kein Name für ein Wrapperelement festgelegt werden. Diese Entscheidungen setzen häufig eine tief greifende Kenntnis von Webdiensten und SOAP voraus.  
  
 Das WCF-Dienst Framework kann die beste und interoperable SOAP-Darstellung zum Senden oder empfangen von mehreren verwandten Informationen automatisch auswählen, ohne diese Optionen für den Benutzer zu erzwingen. Dies wird erreicht, indem diese Informationspakete als Parameter oder Rückgabewerte eines Vorgangsvertrags beschrieben werden. Betrachten Sie z.&#160;B. den folgenden Vorgangsvertrag.  
  
 [!code-csharp[C_DataArchitecture#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_dataarchitecture/cs/source.cs#11)]
 [!code-vb[C_DataArchitecture#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_dataarchitecture/vb/source.vb#11)]  
  
 Das Dienstframework entscheidet automatisch, alle drei Informationsabschnitte (`customerID`, `item`und `quantity`) in den Nachrichtentext zu integrieren und sie in ein Wrapper-Element mit dem Namen `SubmitOrderRequest`einzuschließen.  
  
 Die Beschreibung der Informationen, die als einfache Liste mit Vorgangsvertragsparametern gesendet oder empfangen werden, ist die empfohlene Methode, falls keine besonderen Gründe für einen Wechsel zu dem komplexeren Nachrichtenvertrag oder `Message`-basierten Programmiermodell vorliegen.  
  
### <a name="5-stream"></a>5. Stream  

 Die Verwendung eines `Stream` oder einer seiner Unterklassen in einem Vorgangsvertrag oder als einzelner Nachrichtentextteil in einem Nachrichtenvertrag kann als separates Programmiermodell im Gegensatz zu den oben beschriebenen betrachtet werden. Die Verwendung eines `Stream` auf diese Weise ist die einzige Möglichkeit, zu gewährleisten, dass Ihr Vertrag für ein Streamingmodell verwendet werden kann, fast so, als ob Sie eine eigene Streaming-kompatible `Message` -Unterklasse schreiben würden. Weitere Informationen finden Sie unter [große Datenmengen und Streaming](large-data-and-streaming.md).  
  
 Wenn der `Stream` oder eine seiner Unterklassen auf diese Art verwendet wird, wird das Serialisierungsprogramm nicht aufgerufen. Für ausgehende Nachrichten wird eine besondere `Message` -Streaming-Unterklasse erstellt, und der Stream wird ausgeschrieben, wie im Abschnitt über die <xref:System.Xml.IStreamProvider> -Schnittstelle beschrieben. Für eingehende Nachrichten erstellt das Dienstframework eine `Stream` -Unterklasse über der eingehenden Nachricht und übergibt sie an den Vorgang.  
  
## <a name="programming-model-restrictions"></a>Einschränkungen des Programmiermodells  

 Die oben beschriebenen Programmiermodelle können nicht willkürlich kombiniert werden. Wenn ein Vorgang beispielsweise einen Nachrichtenvertragstyp akzeptiert, muss der Nachrichtenvertrag der einzige Eingabeparameter sein. Darüber hinaus muss der Vorgang dann entweder eine leere Nachricht (ungültiger Rückgabewert) oder einen anderen Nachrichtenvertrag zurückgeben. Diese Einschränkungen des Programmiermodells werden in den Themen für jedes einzelne Programmiermodell beschrieben: [Using Message Contracts](using-message-contracts.md), [Using the Message Class](using-the-message-class.md)und [Large Data and Streaming](large-data-and-streaming.md).  
  
## <a name="message-formatters"></a>Nachrichtenformatierungsprogramme  

 Die oben beschriebenen Programmiermodelle werden von Plug-In-Komponenten, so genannten *Nachrichtenformatierungsprogrammen* , in das Dienstframework unterstützt. Nachrichtenformatierer sind Typen, die die <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> - <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> Schnittstelle oder die-Schnittstelle implementieren, bzw. beides für die Verwendung in Clients bzw. Dienst-WCF-Clients.  
  
 Nachrichtenformatierungsprogramme werden normalerweise über bestimmte Verhalten implementiert. Zum Beispiel implementiert <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> das Daten-Vertragsnachrichten-Formatierungsprogramm. Dies geschieht auf der Dienstseite, indem <xref:System.ServiceModel.Dispatcher.DispatchOperation.Formatter%2A> auf das richtige Formatierungsprogramm der <xref:System.ServiceModel.Description.IOperationBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.OperationDescription%2CSystem.ServiceModel.Dispatcher.DispatchOperation%29> -Methode festgelegt wird, oder auf der Clientseite, indem <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A> auf das richtige Formatierungsprogramm der <xref:System.ServiceModel.Description.IOperationBehavior.ApplyClientBehavior%28System.ServiceModel.Description.OperationDescription%2CSystem.ServiceModel.Dispatcher.ClientOperation%29> -Methode festgelegt wird.  
  
 Die folgenden Tabellen listen die Methoden auf, die ein Nachrichtenformatierungsprogramm möglicherweise implementiert.  
  
|Schnittstelle|Methode|Aktion|  
|---------------|------------|------------|  
|<xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>|<xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter.DeserializeRequest%28System.ServiceModel.Channels.Message%2CSystem.Object%5B%5D%29>|Konvertiert eine eingehende `Message` in Vorgangsparameter|  
|<xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>|<xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter.SerializeReply%28System.ServiceModel.Channels.MessageVersion%2CSystem.Object%5B%5D%2CSystem.Object%29>|Erstellt eine ausgehende `Message` aus Vorgangsrückgabewert/out-Parametern|  
|<xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>|<xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.SerializeRequest%28System.ServiceModel.Channels.MessageVersion%2CSystem.Object%5B%5D%29>|Erstellt eine ausgehende `Message` aus Vorgangsparametern|  
|<xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>|<xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.DeserializeReply%28System.ServiceModel.Channels.Message%2CSystem.Object%5B%5D%29>|Konvertiert eine eingehende `Message` in einen Rückgabewert/out-Parameter|  
  
## <a name="serialization"></a>Serialisierung  

 Wenn Sie Nachrichten Verträge oder Parameter zum Beschreiben des Nachrichten Inhalts verwenden, müssen Sie die Serialisierung verwenden, um zwischen .NET Framework Typen und der XML-infosetdarstellung zu konvertieren. Die Serialisierung wird an anderen Stellen in WCF verwendet, z. b. mit <xref:System.ServiceModel.Channels.Message> einer generischen Methode, die <xref:System.ServiceModel.Channels.Message.GetBody%2A> Sie verwenden können, um den gesamten Text der Nachricht zu lesen, die in ein-Objekt deserialisiert wird.  
  
 WCF unterstützt zwei Serialisierungstechnologien (standardmäßig) zum Serialisieren und Deserialisieren von Parametern und Nachrichten Teilen: <xref:System.Runtime.Serialization.DataContractSerializer> und `XmlSerializer` . Darüber hinaus können Sie benutzerdefinierte Serialisierungsprogramme schreiben. Allerdings können andere Teile von WCF (z. b. die generische- `GetBody` Methode oder die SOAP-Fehlerserialisierung) darauf beschränkt werden, nur die <xref:System.Runtime.Serialization.XmlObjectSerializer> -Unterklassen ( <xref:System.Runtime.Serialization.DataContractSerializer> und <xref:System.Runtime.Serialization.NetDataContractSerializer> , aber nicht die) zu verwenden <xref:System.Xml.Serialization.XmlSerializer> , oder Sie können sogar hart codiert werden, um nur die zu verwenden <xref:System.Runtime.Serialization.DataContractSerializer> .  
  
 Der `XmlSerializer` ist das Serialisierungsmodul, das in ASP.NET-Webdiensten verwendet wird. ph x="1" /&gt; ist die neue Serialisierungs-Engine, die das neue Datenvertrags-Programmiermodell versteht. `DataContractSerializer` ist die Standardauswahl. Die Entscheidung für die Verwendung von `XmlSerializer` kann mit dem <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.DataContractFormatAttribute%2A> für einzelne Vorgänge getroffen werden.  
  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> und <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> sind die Vorgangsverhalten, die für das Plug-In der Nachrichtenformatierungsprogramme für `DataContractSerializer` und `XmlSerializer`verantwortlich sind. Das <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> -Verhalten kann mit jedem Serialisierungsprogramm funktionieren, das von <xref:System.Runtime.Serialization.XmlObjectSerializer>abgeleitet wird, u.&#160;a. <xref:System.Runtime.Serialization.NetDataContractSerializer> (ausführlich beschrieben unter "Verwenden der eigenständigen Serialisierung"). Das Verhalten ruft eine der virtuellen `CreateSerializer` -Methodenüberladungen auf, um das Serialisierungsprogramm zu erhalten. Um ein anderes Serialisierungsprogramm zu verwenden, erstellen Sie eine neue <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> -Unterklasse und überschreiben beide `CreateSerializer` -Überladungen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Angeben von Datenübertragung in Dienstverträgen](specifying-data-transfer-in-service-contracts.md)

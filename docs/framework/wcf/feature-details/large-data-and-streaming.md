---
title: Umfangreiche Daten und Streaming
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ab2851f5-966b-4549-80ab-c94c5c0502d2
caps.latest.revision: "27"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 741fdd9c4326243414ce6c19dcdd8f80317fe225
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="large-data-and-streaming"></a>Umfangreiche Daten und Streaming
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ist eine auf XML basierende Kommunikationsinfrastruktur. Da XML-Daten häufig in im definierten standard-Text-Format codiert ist die [XML 1.0-Spezifikation](http://go.microsoft.com/fwlink/?LinkId=94838), verbundene Systeme Entwicklern und Architekten sind in der Regel besorgt Wire Ressourcenbedarf (oder der Größe) der gesendeten Nachrichten über das Netzwerk und die textbasierte Codierung von XML-dürfen besondere Herausforderung dar, für die effiziente Übertragung binärer Daten.  
  
## <a name="basic-considerations"></a>Allgemeine Überlegungen  
 In diesem Abschnitt werden einige der allgemeinen Fragen und Überlegungen hinsichtlich Codierung, binärer Daten und Streaming behandelt, die sich in der Regel auf die Infrastruktur verbundener Systeme beziehen. Diese Ausführungen dienen als Hintergrundinformationen für die anschließenden Informationen zu  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
### <a name="encoding-data-text-vs-binary"></a>Codieren von Daten: Text oder Binär  
 Zu den verbreiteten Bedenken von Entwicklern gehört die Annahme, dass XML im Vergleich zu binären Formaten einen erheblichen Mehraufwand mit sich bringt, angesichts der sich wiederholenden Natur von Starttags und Endtags. Die Codierung numerische Werte scheint ihnen wesentlich umfangreicher, da diese Werte in Textwerten ausgedrückt werden, und sie fürchten, dass binäre Daten nicht effizient ausgedrückt werden, da sie speziell codiert werden müssen, um in ein Textformat eingebettet werden zu können.  
  
 Zwar treffen diese und ähnliche Bedenken zu, doch ist der tatsächliche Unterschied zwischen XML-textcodierten Nachrichten in einer XML-Webdienstumgebung und binärcodierten Nachrichten in einer älteren RPC-Umgebung (Remote Procedure Call) häufig wesentlich geringer als auf den ersten Blick vermutet.  
  
 Während XML-textcodierte Nachrichten transparent und "lesbar" sind, sind binäre Nachrichten im Vergleich dazu häufig reichlich obskur und ohne Tools nur schwer zu decodieren. Der Unterschied in der Lesbarkeit verschleiert leicht die Tatsache, dass auch binäre Nachrichten häufig Inline-Metadaten in der Nutzlast enthalten, was genau wie bei XML-Textnachrichten zu Mehraufwand führt. Das trifft besonders auf binäre Formate zu, die Funktionen für lose Verknüpfungen und dynamische Aufrufe bieten sollen.  
  
 Binäre Formate führen in der Regel solche beschreibenden Metadateninformationen in einem "Header", in dem auch das Datenlayout für die folgenden Datensätze deklariert werden. Dieser allgemeinen Metadatenblockdeklaration folgt in der Regel die Nutzlast mit nur minimalem weiteren Mehraufwand. Im Gegensatz dazu schließt XML jedes Datenelement in ein Element oder Attribut ein, sodass das Einschließen von Metadaten für jedes serialisierte Nutzlastobjekt wiederholt erfolgt. Letztendlich ist die Größe eines einzelnen serialisierten Nutzlastobjekts bei einem Vergleich zwischen Text- und Binärdarstellungen ähnlich, da einige beschreibende Metadaten bei beidem ausgedrückt werden müssen. Das binäre Format profitiert jedoch von der gemeinsame Metadatenbeschreibung bei jedem zusätzlichen Nutzlastobjekt, das übertragen wird, aufgrund der des niedrigeren Gesamtaufwands.  
  
 Bei bestimmten Datentypen, wie z. B. Zahlen, kann die Verwendung binärer numerischer Darstellungen fester Größe, wie ein dezimaler 128-Bit-Typ anstelle von Nur-Text, allerdings ein gewisser Nachteil sein, da die Nur-Text-Darstellung einige Byte kleiner sein kann. Die normalerweise flexiblerern Optionen zur XML-Textcodierung können Textdaten auch Größenvorteile bescheren, während einige binäre Formate vielleicht standardmäßig das 16-Bit- oder sogar 32-Bit-Unicode-Format verwenden, was auf das .NET Binary XML-Format nicht zutrifft.  
  
 Somit ist die Entscheidung zwischen Text- oder Binärformat nicht ganz so einfach wie die Annahme, dass binäre Nachrichten immer kleiner sind als XML-Textnachrichten.  
  
 Ein eindeutiger Vorteil von XML-Textnachrichten besteht jedoch darin, dass sie auf Standards basieren und eine breite Palette an Interoperabilitätsoptionen und Plattformunterstützung bieten. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] dem Abschnitt "Codierungen" weiter unten in diesem Thema.  
  
### <a name="binary-content"></a>Binärer Inhalt  
 Es gibt einen Bereich, in dem binäre Codierungen textbasierten Codierungen in Hinblick auf die resultierende Nachrichtengröße überlegen sind, und zwar bei großen binären Datenelementen. Dazu gehören Bilder, Videos, Soundclips und jede sonstige Form von nicht transparenten, binären Daten, die zwischen einem Dienst und seinem Consumer ausgetauscht werden. Damit diese Typen in XML-Text passen, werden sie in der Regel mit Base64 codiert.  
  
 In einer Base64-codierten Zeichenfolge stellt jedes Zeichen 6 Bits der ursprünglichen 8-Bit-Daten dar. Das ergibt ein Codierung-Mehraufwand-Verhältnis von 4:3 für Base64, wobei üblicherweise bei der Konvertierung hinzugefügte zusätzliche Formatierungszeichen (Wagenrücklauf/Zeilenvorschub) nicht berücksichtigt werden. Während die Bedeutung der Unterschiede zwischen XML und binären Codierungen normalerweise vom Szenario abhängen, ist die Größenzunahme von über 33&#160;% beim Übertragen einer 500-MB-Nutzlast in der Regel nicht akzeptabel.  
  
 Um diesen Codierungsaufwand zu verhindern, ermöglicht der MTOM-Standard (Message Transmission Optimization Mechanism) eine Externalisierung großer Datenelement, die in einer Nachrichten enthalten sind. Dabei können die Elemente als Binärdaten ohne spezielle Codierung mit der Nachricht gesendet werden. Bei MTOM werden Daten in ähnlicher Weise wie bei SMTP-E-Mail-Nachrichten (Simple Mail Transfer Protocol) mit Anlagen oder eingebetteten Inhalten (Bilder oder anderer eingebetteter Inhalt) ausgetauscht. MTOM-Nachrichten werden als multipart/related MIME-Sequenzen verpackt, wobei der Stammteil die eigentliche SOAP-Nachricht darstellt.  
  
 Eine MTOM-SOAP-Nachricht wird in ihrer uncodierten Version geändert. Dabei ersetzen spezielle Elementtags, die sich auf die jeweiligen MIME-Teile beziehen, die ursprünglichen Elemente in der Nachricht, die binäre Daten enthielten. Als Ergebnis bezieht sich die SOAP-Nachricht auf binären Inhalt, indem auf die mit ihr gesendeten MIME-Teile verwiesen wird, ansonsten jedoch nur XML-Textdaten enthalten sind. Da dieses Model eng an das weit verbreiteten SMTP-Modell anlehnt, gibt es ein breites Angebot an Tools zur Codierung und Decodierung von MTOM-Nachrichten für viele Pattformen, was eine hohe Interoperabilität gewährleistet.  
  
 Doch wie bei Base64 ist auch bei MTOM ein gewisser Mehraufwand für das MIME-Format erforderlich, sodass sich die Vorteile von MTOM nur dann bemerkbar machen, wenn die Größe eines binären Datenelements ungefähr 1 KB überschreitet. Aufgrund dieses Mehraufwands sind MTOM-codierte Nachrichten möglicherweise größer als Nachrichten, die eine Base64-Codierung für binäre Daten verwenden, wenn die binäre Nutzlast diese Schwelle nicht überschreitet. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] dem Abschnitt "Codierungen" weiter unten in diesem Thema.  
  
### <a name="large-data-content"></a>Inhalte mit umfangreichen Daten  
 Abgesehen von der Übertragungsgröße stellt die oben erwähnte 500-MB-Nutzlast für den Dienst und den Client auch lokal ein nicht unerhebliches Problem dar. Standardmäßig [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verarbeitet die Nachrichten in *Puffermodus*. Dabei befindet sich der gesamte Inhalt vor dem Senden oder nach dem Empfang im Arbeitsspeicher. In den meisten Szenarien ist das zwar eine gute Strategie, und für Messagingfunktionen wie digitale Signaturen sowie für eine zuverlässige Zustellung ist das sogar eine Notwendigkeit, doch bei großen Nachrichten erschöpfen sich dadurch leicht die Systemressourcen.  
  
 Die bei großen Nutzlasten einzuschlagende Strategie ist Streaming. Obwohl Nachrichten, insbesondere in XML ausgedrückt, allgemein als relativ kompakte Datenpakete angesehen werden, kann eine Nachricht mehrere Gigabyte groß sein und eher einem durchgehenden Datenstrom ähneln statt einem Datenpaket. Wenn Daten im Streamingmodus anstatt im Puffermodus übertragen werden, macht der Absender den Inhalt des Nachrichtentextes in der Form eines Streams für den Empfänger verfügbar. Dabei leitet die Nachrichteninfrastruktur die Daten fortlaufend vom Absender an den Empfänger weiter.  
  
 Das häufigste Szenario, bei dem Inhalte mit umfangreichen Daten übertragen werden, sind Übertragungen von binären Datenobjekten, die folgende Merkmale aufweisen:  
  
-   Die Objekte können nur schwer in eine Nachrichtensequenz unterteilt werden.  
  
-   Die Zustellung muss schnell erfolgen.  
  
-   Die Objekte sind noch nicht vollständig verfügbar, wenn die Übertragung beginnt.  
  
 Bei Daten, die diesen Einschränkungen nicht unterliegen, ist es in der Regel besser, anstatt einer großen Nachricht Sequenzen der Nachrichten im Rahmen einer Sitzung zu senden. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] dem Abschnitt "Streaming von Daten" weiter unten in diesem Thema.  
  
 Beim Senden von großer Mengen von Daten müssen Sie festlegen der `maxAllowedContentLength` IIS-Einstellung (Weitere Informationen finden Sie unter [Konfigurieren von IIS Anforderungslimits](http://go.microsoft.com/fwlink/?LinkId=253165)) und die `maxReceivedMessageSize` binden Einstellung (z. B. [ System.ServiceModel.BasicHttpBinding.MaxReceivedMessageSize](xref:System.ServiceModel.HttpBindingBase.MaxReceivedMessageSize%2A) oder <xref:System.ServiceModel.NetTcpBinding.MaxReceivedMessageSize%2A>). Die `maxAllowedContentLength` -Eigenschaft hat den Standardwert 28,6 MB und der `maxReceivedMessageSize` -Eigenschaft standardmäßig auf 64 KB.  
  
## <a name="encodings"></a>Codierungen  
 Ein *Codierung* definiert einen Satz von Regeln dazu, wie Nachrichten bei der Übertragung zu präsentieren. Ein *Encoder* implementiert diese Codierung und sorgt auf der Absenderseite eingeräumt eine <xref:System.ServiceModel.Channels.Message> in-Memory-Nachricht in einen Bytestream oder Bytepuffer, der über das Netzwerk gesendet werden kann. Auf der Empfängerseite wandelt der Encoder die Bytesequenz wieder in eine Nachricht im Arbeitsspeicher um.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] enthält drei Encoder. Sie können jedoch gegebenenfalls auch eigene Encoder schreiben und integrieren.  
  
 Jede der Standardbindungen schließt einen vorkonfigurierten Encoder ein. Dabei verwenden standardmäßig die Bindungen mit dem Präfix Net* den binären Encoder (indem die <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>-Klasse eingeschlossen wird), und die Klassen <xref:System.ServiceModel.BasicHttpBinding> und <xref:System.ServiceModel.WSHttpBinding> verwenden den Textnachrichtenencoder (anhand der <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>-Klasse).  
  
|Bindungselement des Encoders|Beschreibung|  
|-----------------------------|-----------------|  
|<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>|Der Textnachrichtencoder ist der Standardencoder für alle HTTP-basierten Bindungen. Er empfiehlt sich für alle benutzerdefinierten Bindungen, bei denen besonders auf Interoperabilität Wert gelegt wird. Dieser Encoder liest und schreibt auf SOAP 1.1/SOAP 1.2 basierende Standardtextnachrichten ohne spezielle Behandlung von binären Daten. Wenn <xref:System.ServiceModel.Channels.MessageVersion> einer Nachricht nicht auf `None` festgelegt ist, wird der Wrapper des SOAP-Umschlags in der Ausgabe weggelassen und nur der Inhalt des Nachrichtentextes wird serialisiert.|  
|<xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>|Der MTOM-Nachrichtenencoder ist ein Textencoder, der eine spezielle Behandlung binärer Daten implementiert und nicht standardmäßig in den Standardbindungen verwendet wird, da es sich um ein extrem fallabhängiges Hilfsprogramm für Optimierungen handelt. Wenn die Nachricht binäre Daten enthält, die einen Schwellenwert überschreiten, nach dem die MTOM-Codierung vorteilhafter ist, werden die Daten in einen MIME-Teil externalisiert, der auf den Nachrichtenumschlag folgt. Siehe "Aktivieren von MTOM" weiten unten in diesem Abschnitt.|  
|<xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>|Der binäre Nachrichtenencoder ist der Standardencoder für Net*-Bindungen und empfiehlt sich, wenn beide Kommunikationspartner auf [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] basieren. Der binäre Nachrichtenencoder verwendet das .NET Binary XML-Format. Dieses Format ist eine spezielle Binärdarstellung für XML-Informationssets (Infosets) von Microsoft, die in der Regel kompakter ist als die entsprechende XML 1.0-Darstellung und binäre Daten als Bytestream codiert.|  
  
 Die Textnachrichtencodierung empfiehlt sich in der Regel für Kommunikationspfade, die Interoperabilität erfordern, während die binäre Nachrichtencodierung für jeden anderen Kommunikationspfad die optimale Lösung ist. Die binäre Nachrichtencodierung führt im Vergleich zu Text bei einzelnen Nachrichten meist zu einer geringeren Größe und progressiv im Verlauf einer Kommunikationssitzung sogar zu noch kleineren Nachrichten. Im Unterschied zur Textcodierung gibt es bei der binären Codierung keine spezielle Behandlung von binären Daten, wie die Verwendung von Base64, sondern Bytes werden als Bytes dargestellt.  
  
 Wenn Sie für Ihre Lösung keine Interoperabilität benötigen, aber trotzdem den HTTP-Transport verwenden möchten, machen Sie <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> zu einer benutzerdefinierten Bindung, die die <xref:System.ServiceModel.Channels.HttpTransportBindingElement>-Klasse für den Transport verwendet. Wenn verschiedene Clients Ihres Dienstes Interoperabilität benötigen, sollten Sie parallele Endpunkte verfügbar machen, bei denen jeweils die geeigneten Transport- und Codieroptionen für den entsprechenden Client aktiviert sind.  
  
### <a name="enabling-mtom"></a>Aktivieren von MTOM  
 Wenn Interoperabilität erforderlich ist und umfangreiche binäre Daten gesendet werden müssen, stellt die MTOM-Nachrichtencodierung die alternative Codierungsstrategie dar, die Sie für die Standardbindungen <xref:System.ServiceModel.BasicHttpBinding> oder <xref:System.ServiceModel.WSHttpBinding> aktivieren können. Legen Sie dazu die jeweilige `MessageEncoding`-Eigenschaft auf <xref:System.ServiceModel.WSMessageEncoding.Mtom> fest, oder machen Sie <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> zu einer <xref:System.ServiceModel.Channels.CustomBinding>. Der folgende Beispielcode, extrahiert aus der [MTOM-Codierung](../../../../docs/framework/wcf/samples/mtom-encoding.md) Beispiel zeigt, wie zum Aktivieren von MTOM in Konfiguration.  
  
```xml  
<system.serviceModel>  
     …  
    <bindings>  
      <wsHttpBinding>  
        <binding name="ExampleBinding" messageEncoding="Mtom"/>  
      </wsHttpBinding>  
    </bindings>  
     …  
<system.serviceModel>  
```  
  
 Wie bereits erwähnt, hängt die Entscheidung für die MTOM-Codierung vom zu sendenden Datenvolumen ab. Da MTOM auf der Bindungsebene aktiviert wird, wirkt sich diese Codierung auf alle Vorgänge eines bestimmten Endpunkts aus.  
  
 Der MTOM-Encoder gibt unabhängig davon, ob binäre Daten letztendlich externalisiert werden, immer MTOM-codierte MIME-Multipart-Nachrichten aus. Aktivieren Sie deshalb MTOM nur für Endpunkte, die Nachrichten mit über 1&#160;KB binärer Daten austauschen. Außerdem sollten die Dienstverträge, die für die Verwendung mit für MTOM aktivierten Endpunkten möglichst darauf beschränkt sein, dass sie nur Vorgänge zu solchen Datenübertragungen angeben. Die zugehörigen Steuerungsfunktionen sollten sich in einem gesonderten Vertrag befinden. Diese "Nur-MTOM"-Regel gilt nur für Nachrichten, die über einen für MTOM aktivierten Endpunkt gesendet werden. Der MTOM-Encoder kann auch eingehende Nachrichten decodieren und analysieren, die nicht auf MTOM basieren.  
  
 Die Verwendung des MTOM-Encoders ist mit allen anderen Funktionen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] konform. Beachten Sie jedoch, dass diese Regel nicht in allen Fällen gelten kann, wie z. B. bei einer erforderlichen Sitzungsunterstützung.  
  
### <a name="programming-model"></a>Programmiermodell  
 Unabhängig davon, welchen der drei integrierten Encoder Sie in Ihrer Anwendung verwenden, erfolgt die Programmierung zur Übertragung binärer Daten in allen Fällen auf die gleiche Weise. Der Unterschied besteht darin, wie die Daten basierend auf dem Datentyp in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] behandelt werden.  
  
```  
[DataContract]  
class MyData  
{  
    [DataMember]  
    byte[] binaryBuffer;  
    [DataMember]  
    string someStringData;  
}   
```  
  
 Bei der Verwendung von MTOM wird der vorausgehende Datenvertrag nach den folgenden Regeln serialisiert:  
  
-   Wenn `binaryBuffer` nicht `null` ist und im Einzelfall genügend Daten enthält, um den MTOM-Externalisierungsmehraufwand (MIME-Header usw.) im Vergleich zur Base64-Codierung zu rechtfertigen, werden die Daten externalisiert und als binärer MIME-Teil mit der Nachricht gesendet. Wird der Schwellenwert nicht überschritten, werden die Daten als Base64 codiert.  
  
-   Die Zeichenfolge (und alle anderen nicht binären Typen) wird unabhängig von der Größe immer als Zeichenfolge innerhalb des Nachrichtentextes dargestellt.  
  
 Die Auswirkungen auf die MTOM-Codierung bleiben gleich, unabhängig davon, ob Sie einen expliziten Datenvertrag wie im vorherigen Beispiel, eine Parameterliste in einem Vorgang oder geschachtelte Datenverträge verwenden oder ob Sie Datenvertragsobjekte innerhalb einer Auflistung übertragen. Bytearrays eignen sich immer für eine Optimierung und werden optimiert, wenn die Optimierungsschwellenwerte erreicht sind.  
  
> [!NOTE]
>  Verwenden Sie keine von <xref:System.IO.Stream?displayProperty=nameWithType> abgeleiteten Typen in Datenverträgen. Streamdaten sollten nach einem Streamingmodell übermittelt werden, wie im folgenden Abschnitt "Streaming von Daten" erläutert wird.  
  
## <a name="streaming-data"></a>Streaming von Daten  
 Wenn Sie eine große Datenmenge übertragen müssen, ist der Streamingübertragungsmodus in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] eine praktische Alternative zum Standardverhalten, bei dem vollständiger Nachrichten im Arbeitsspeicher bepuffert und verarbeitet werden.  
  
 Aktivieren Sie bei großen Nachrichten (mit Text oder binärem Inhalt) die Streamingfunktion, wenn die Daten nicht segmentiert werden können, schnell zugestellt werden müssen oder wenn die Daten beim Beginn der Übertragung noch nicht vollständig verfügbar sind.  
  
### <a name="restrictions"></a>Beschränkungen  
 Sie können bei aktiviertem Streaming sehr viele [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Funktionen verwenden:  
  
-   Digitale Signaturen für den Nachrichtentext sind nicht möglich, da sie Berechnungen oder einen Hash zum gesamten Nachrichteninhalt erfordern. Beim Streaming ist der Inhalt nicht vollständig verfügbar, wenn die Nachrichtenheader erstellt und gesendet werden, weshalb keine digitale Signatur berechnet werden kann.  
  
-   Die Verschlüsselung hängt von digitalen Signaturen ab, mit denen überprüft wird, ob die Daten ordnungsgemäß rekonstruiert wurden.  
  
-   Zuverlässige Sitzungen müssen gesendete Nachrichten für den Client puffen, damit bei der Übertragung verlorgen gegangene Nachrichten neu gesendet werden können. Außerdem müssen sie Nachrichten vor einer Weitergabe an die Dienstimplementierung für den Dienst zurückhalten, um die richtige Nachrichtenfolge beizubehalten, falls Nachrichten nicht in der richtigen Folge eingehen.  
  
 Wegen dieser funktionalen Einschränkungen können Sie nur Sicherheitsoptionen auf Transportebene für das Streaming verwenden. Zuverlässige Sitzungen können nicht bereitgestellt werden. Das Streaming ist nur mit den folgenden vom System definierten Bindungen verfügbar:  
  
-   <xref:System.ServiceModel.BasicHttpBinding>  
  
-   <xref:System.ServiceModel.NetTcpBinding>  
  
-   <xref:System.ServiceModel.NetNamedPipeBinding>  
  
-   <xref:System.ServiceModel.WebHttpBinding>  
  
 Da die zugrunde liegenden Transporte von <xref:System.ServiceModel.NetTcpBinding> und <xref:System.ServiceModel.NetNamedPipeBinding> im Unterschied zu HTTP naturgemäß eine zuverlässige Zustellung und verbindungsbasierte Sitzungsunterstützung aufweisen, sind diese Bindungen in der Praxis nur minimal von diesen Einschränkungen betroffen.  
  
 Streaming ist für den MSMQ-Transport (Message Queuing) nicht verfügbar und kann deshalb nicht mit der <xref:System.ServiceModel.NetMsmqBinding>- oder der <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>-Klasse verwendet werden. Der MSMQ-Transport unterstützt nur gepufferte Datenübertragungen mit einer eingeschränkten Nachrichtengröße. Alle anderen Transporte unterliegen in den meisten Szenarien jedoch keiner speziellen Einschränkung hinsichtlich der Nachrichtengröße.  
  
 Streaming ist auch beim Peerkanaltransport nicht verfügbar und kann deshalb nicht mit <xref:System.ServiceModel.NetPeerTcpBinding> verwendet werden.  
  
#### <a name="streaming-and-sessions"></a>Streaming und Sitzungen  
 Möglicherweise tritt beim Streaming von Aufrufen mit einer sitzungsbasierten Bindung ein unerwartetes Verhalten auf. Alle Streamingaufrufe erfolgen über einen einzigen Kanal (den Datagrammkanal), der keine Sitzungen unterstützt, selbst wenn die verwendete Bindung für die Verwendung von Sitzungen konfiguriert ist. Wenn mehrere Clients Streamingaufrufe an dasselbe Dienstobjekt über eine sitzungsbasierte Bindung durchführen und der Parallelitätsmodus des Dienstobjekts auf "single" und sein Instanzkontextmodus auf "PerSession" festgelegt ist, müssen alle Aufrufe den Datagrammkanal passieren, sodass immer nur jeweils ein Aufruf verarbeitet wird. Bei einem oder mehreren Clients kommt es dabei unter Umständen zu einem Timeout. Sie können dieses Problem umgehen, indem Sie entweder den Instanzkontextmodus des Dienstobjekts auf "PerCall" oder die Parallelität auf "Multiple" festlegen.  
  
> [!NOTE]
>  MaxConcurrentSessions hat in diesem Fall keine Auswirkungen, da nur eine "Sitzung" verfügbar ist.  
  
### <a name="enabling-streaming"></a>Aktivieren des Streaming  
 Das Streaming kann in folgender Weise aktiviert werden:  
  
-   Anforderungen werden im Streamingmodus gesendet und akzeptiert, und Antworten werden im Puffermodus akzeptiert und zurückgegeben (<xref:System.ServiceModel.TransferMode.StreamedRequest>).  
  
-   Anforderungen werden im Puffermodus gesendet und akzeptiert, und Antworten werden im Streamingmodus akzeptiert und zurückgegeben (<xref:System.ServiceModel.TransferMode.StreamedResponse>).  
  
-   Anforderungen und Antworten werden in beiden Richtungen im Streamingmodus gesendet und empfangen. (<xref:System.ServiceModel.TransferMode.Streamed>).  
  
 Sie können das Streaming deaktivieren, indem Sie den Übertragungsmodus auf <xref:System.ServiceModel.TransferMode.Buffered>, die Standardeinstellungen für alle Bindungen, festlegen. Im folgenden Codebeispiel wird veranschaulicht, wie der Übertragungsmodus in der Konfiguration festgelegt wird.  
  
```xml  
<system.serviceModel>  
     …  
    <bindings>  
      <basicHttpBinding>  
        <binding name="ExampleBinding" transferMode="Streaming"/>  
      </basicHttpBinding>  
    </bindings>  
     …  
<system.serviceModel>  
```  
  
 Wenn Sie eine Bindung im Code instanziieren, müssen Sie die jeweilige `TransferMode`-Eigenschaft der Bindung (oder das Transportbindungselement, wenn Sie eine benutzerdefinierte Bindung erstellen) auf einen der oben erwähnten Werte festlegen.  
  
 Sie können Streaming ohne Funktionseinschränkung für Anforderungen und Antworten, oder für beide Richtungen unabhängig, auf jeder Seite der Kommunikation aktivieren. Gehen Sie jedoch immer davon aus, dass die übertragene Datenmenge groß genug ist, um eine Aktivierung des Streaming für beide Endpunkte einer Kommunikationsverbindung zu rechtfertigen. Bei einer plattformübergreifenden Kommunikation, bei der einer der Endpunkte nicht mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementiert ist, hängt die Fähigkeit zur Verwendung des Streaming von den Streamingfähigkeit der Plattform ab. Eine weitere seltene Ausnahme kann eine Szenario sein, das auf dem Arbeitsspeicherverbrauch basiert, wobei der Client oder Dienst die Arbeitsseiten minimieren muss und nur geringe Puffergrößen möglich sind.  
  
### <a name="enabling-asynchronous-streaming"></a>Aktivieren von asynchronem Streaming  
 Um das asynchrone Streaming zu aktivieren, fügen Sie dem Diensthost das <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>-Endpunktverhalten hinzu und legen dessen <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.AsynchronousSendEnabled%2A>-Eigenschaft auf `true` fest. Die Funktion für echtes asynchrones Streaming auf der Senderseite wurde ebenfalls hinzugefügt. Dies verbessert die Skalierbarkeit des Diensts in Szenarien, in denen Nachrichten an mehrere Clients gestreamt werden, von denen einige eine langsame Lesegeschwindigkeit haben, möglicherweise aufgrund von Netzwerküberlastung, oder überhaupt nicht lesen. In diesen Szenarien werden nicht einzelne Threads für den Dienst pro Client blockiert. Dadurch wird sichergestellt, dass der Dienst in der Lage ist, viel mehr Clients zu verarbeiten und somit die Skalierbarkeit des Diensts zu verbessern.  
  
### <a name="programming-model-for-streamed-transfers"></a>Programmiermodell für Streamingübertragungen  
 Das Programmiermodell für Streaming ist unkompliziert. Geben Sie für eingehende Streamingdaten einen Vorgangsvertrag mit einem einzelnen Eingabeparameter vom Typ <xref:System.IO.Stream> an. Geben Sie für zurückgehende Streamingdaten einen <xref:System.IO.Stream>-Verweis an.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IStreamedService  
{  
    [OperationContract]  
    Stream Echo(Stream data);  
    [OperationContract]  
    Stream RequestInfo(string query);  
    [OperationContract(OneWay=true)]  
    void ProvideInfo(Stream data);  
}  
```  
  
 Im Vorgang `Echo` im obigen Beispiel wird ein Stream empfangen und zurückgegeben und sollte deshalb für eine Bindung mit <xref:System.ServiceModel.TransferMode.Streamed> verwendet werden. Für den Vorgang `RequestInfo` eignet sich <xref:System.ServiceModel.TransferMode.StreamedResponse> am besten, da nur <xref:System.IO.Stream> zurückgegeben wird. Der unidirektionale Vorgang eignet sich für <xref:System.ServiceModel.TransferMode.StreamedRequest> am besten.  
  
 Wenn Sie den folgenden `Echo`- oder `ProvideInfo`-Vorgängen einen zweiten Parameter hinzufügen, wird das Dienstmodell auf eine Pufferstrategie zurückgesetzt und verwendet die Laufzeitserialisierungsdarstellung des Streams. Nur Vorgänge mit einem Eingabestreamparameter sind mit einem End-to-End-Anforderungsstreaming kompatibel.  
  
 Diese Regel gilt in ähnlicher Weise für Nachrichtenverträge. Wie im folgenden Nachrichtenvertrag dargestellt, kann der Nachrichtenvertrag nur einen einzigen Textmember enthalten, der ein Stream ist. Wenn Sie zusätzliche Informationen mit dem Stream übermitteln möchten, müssen diese Informationen in Nachrichtenheadern übertragen werden. Der Nachrichtentext ist ausschließlich für Streaminginhalt reserviert.  
  
```  
[MessageContract]  
public class UploadStreamMessage  
{  
   [MessageHeader]  
   public string appRef;  
   [MessageBodyMember]  
   public Stream data;  
}   
```  
  
 Streamingübertragungen sind beendet und die Nachricht wird geschlossen, wenn der Stream das Ende der Datei (End of File, EOF) erreicht. Beim Senden einer Nachricht (Zurückgeben eines Werts oder Aufrufen eines Vorgangs) können Sie <xref:System.IO.FileStream> übergeben. Die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Infrastruktur ruft daraufhin die Daten aus diesem Stream ab, bis er vollständig gelesen wurde und EOF erreicht hat. Um Streamingdaten für die Quelle zu übertragen, die über keine integrierte, von <xref:System.IO.Stream> abgeleitete Klasse dieser Art verfügt, erstellen sie eine solche Klasse, überlagern Sie die Streamquelle mit dieser Klasse, und verwenden Sie das als Argument oder Rückgabewert.  
  
 Beim Empfang einer Nachricht erstellt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] einen Stream über den Base64-codierten Nachrichtentextinhalt (oder den entsprechenden MIME-Teil bei Verwendung von MTOM), und der Stream erreicht EOF, wenn der Inhalt gelesen wurde.  
  
 Streaming auf Transportebene funktioniert auch mit jedem anderen Nachrichtenvertragstyp (Parameterlisten, Datenvertragsargumente und explizitem Nachrichtenvertrag). Da jedoch die Serialisierung und Deserialisierung von Nachrichten dieses Typs eine Pufferung durch das Serialisierungsprogramm erfordert, ist die Verwendung dieser Vertragsvarianten nicht ratsam.  
  
### <a name="special-security-considerations-for-large-data"></a>Besondere Sicherheitsüberlegungen für umfangreiche Daten  
 Sie können mit allen Bindungen die Größe eingehender Nachrichten einschränken, um Denial-of-Service-Angriffe zu verhindern. Die <xref:System.ServiceModel.BasicHttpBinding>, z. B. macht eine [System.ServiceModel.BasicHttpBinding.MaxReceivedMessageSize](xref:System.ServiceModel.HttpBindingBase.MaxReceivedMessageSize%2A) -Eigenschaft, die die Größe der eingehenden Nachricht, beschränkt und damit auch die Höchstmenge an Arbeitsspeicher, auf die zugegriffen wird Beim Verarbeiten der Nachricht. Diese Wert wird in Byte festgelegt, mit einem Standardwert von 65.536 Bytes.  
  
 Ein Sicherheitsrisiko, das speziell beim Streaming umfangreicher Daten entsteht, und einen Denial-of-Service-Angriff bedeuten kann, besteht darin, wenn Daten gepuffert werden, während der Empfänger ein Streaming erwartet. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puffert z. B. immer die SOAP-Header einer Nachricht. Ein Angreifer kann somit eine große Nachricht in böswilliger Absicht erstellen, die ausschließlich aus Headern besteht, um eine Pufferung der Daten zu erzwingen. Legen Sie bei aktiviertem Streaming `MaxReceivedMessageSize` auf einen extrem hohen Wert fest, da der Empfänger nicht davon ausgeht, dass die gesamte Nachricht gleichzeitig im Arbeitsspeicher gepuffert wird. Wenn [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zum Puffern der Nachricht gezwungen wird, tritt ein Speicherüberlauf auf.  
  
 Deshalb reicht es in diesem Fall nicht aus, die maximale Größe eingehender Nachrichten einzuschränken. Die von `MaxBufferSize` gepufferte Menge des Arbeitsspeichers muss mit der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Eigenschaft eingeschränkt werden. Legen Sie beim Streaming dafür einen sicheren Wert fest (oder behalten Sie den Standardwert bei). Angenommen, der Dienst muss Dateien bis zu einer Größe von 4 GB empfangen und auf der lokalen Festplatte speichern. Der Arbeitsspeicher ist in diesem Szenario so eingeschränkt, dass immer nur 64 KB gepuffert werden können. Sie würden dann `MaxReceivedMessageSize` auf 4 GB und `MaxBufferSize` auf 64 KB festlegen. Außerdem müssen Sie in der Dienstimplementierung sicherstellen, dass nur aus dem eingehenden Stream in 64-KB-Segmenten gelesen wird und das nächste Segment erst gelesen wird, nachdem das vorherige auf die Festplatte geschrieben wurde und es dann aus dem Arbeitspeicher gelöscht wird.  
  
 Beachten Sie, dass dieses Kontingent nur die Pufferung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] einschränkt, jedoch keinen Schutz bietet, wenn Sie eine Pufferung in einem eigenen Dienst oder der Clientimplementierung ausführen. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Weitere Überlegungen zur Sicherheit, finden Sie unter [Sicherheitsüberlegungen zu Daten](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).  
  
> [!NOTE]
>  Die Entscheidung über die Verwendung der gepufferten oder der Streamingübertragung wird lokal am Endpunkt getroffen. Bei HTTP-Übertragungen wird der Übertragungsmodus nicht über Verbindungen oder an Proxyserver oder andere Vermittler weitergegeben. Das Festlegen des Übertragungsmodus spiegelt sich nicht in der Beschreibung der Dienstschnittstelle wider. Nachdem Sie einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client für einen Dienst erstellt haben, müssen Sie die Konfigurationsdatei für Dienste bearbeiten, die mit Streamingübertragungen verwendet werden sollen, um den Modus festzulegen. Bei TCP und Named Pipe-Transporten wird der Übertragungsmodus als Richtlinienassertion weitergegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Aktivieren von Streaming](../../../../docs/framework/wcf/feature-details/how-to-enable-streaming.md)

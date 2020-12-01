---
title: Ableiten von WebRequest
ms.date: 03/30/2017
helpviewer_keywords:
- WebRequest class, pluggable protocols
- protocol-specific request handler
- sending data, pluggable protocols
- pluggable protocols, class criteria
- Internet, pluggable protocols
- receiving data, pluggable protocols
- protocols, pluggable
ms.assetid: 9810c177-973e-43d7-823c-14960bd625ea
ms.openlocfilehash: a480f38aeefed3481187e5027409a49d1535c9f4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250553"
---
# <a name="deriving-from-webrequest"></a>Ableiten von WebRequest

Die <xref:System.Net.WebRequest>-Klasse ist eine abstrakte Basisklasse, die die grundlegende Methoden und Eigenschaften bereitstellt, mit denen ein protokollspezifischer Anforderungshandler erstellt wird, der in das austauschbare Protokollmodell von .NET Framework passt. Anwendungen, die die **WebRequest**-Klasse verwenden, können Daten mit einem beliebigen unterstützten Protokoll anfordern, ohne das verwendete Protokoll anzugeben.  
  
 Zwei Kriterien müssen erfüllt sein, damit eine protokollspezifische Klasse als ein austauschbares Protokoll verwendet werden kann: Die Klasse muss die <xref:System.Net.IWebRequestCreate>-Schnittstelle implementieren und sie mit der <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType>-Methode registrieren. Die Klasse muss alle abstrakten Methoden und Eigenschaften von **WebRequest** überschreiben, um die austauschbare Schnittstelle bereitzustellen.  
  
 **WebRequest**-Instanzen sind für die einmalige Verwendung vorgesehen. Wenn Sie eine andere Anforderung vornehmen möchten, erstellen Sie eine neue **WebRequest**. **WebRequest** unterstützt die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle, um Entwicklern zu ermöglichen, eine **WebRequest**-Vorlage zu serialisieren und die Vorlage für zusätzliche Anforderungen zu rekonstruieren.  
  
## <a name="iwebrequest-create-method"></a>IWebRequest Create-Methode  

 Die <xref:System.Net.IWebRequestCreate.Create%2A>-Methode ist verantwortlich für das Initialisieren einer neuen Instanz der protokollspezifischen Klasse. Wenn eine neue **WebRequest** erstellt wird, entspricht die <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>-Methode dem angeforderten URI und die URI-Präfixe werden mit der **RegisterPrefix**-Methode registriert. Die **Create**-Methode des entsprechenden protokollspezifischen Nachfolgers muss eine initialisierte Instanz des Nachfolgers zurückgeben, die eine Standardtransaktion für Anforderungen/Antworten für das Protokoll ausführen kann, ohne ein protokollspezifisches Feld zu ändern.  
  
## <a name="connectiongroupname-property"></a>ConnectionGroupName-Eigenschaft  

 Die <xref:System.Net.WebRequest.ConnectionGroupName%2A>-Eigenschaft wird verwendet, um eine Gruppe von Verbindungen mit einer Ressource zu benennen, damit mehrere Anforderungen über eine einzelne Verbindung ausgeführt werden können. Um die Freigabe von Verbindungen zu implementieren, müssen Sie eine protokollspezifische Methode zum Pooling und Zuweisen von Verbindungen verwenden. Zum Beispiel implementiert die bereitgestellte <xref:System.Net.ServicePointManager>-Klasse die gemeinsame Nutzung von Verbindungen für die <xref:System.Net.HttpWebRequest>-Klasse. Die **ServicePointManager**-Klasse erstellt eine <xref:System.Net.ServicePoint>, die eine Verbindung mit einem bestimmten Server für jede Verbindungsgruppierung bereitstellt.  
  
## <a name="contentlength-property"></a>ContentLength-Eigenschaft  

 Die <xref:System.Net.WebRequest.ContentLength%2A>-Eigenschaft gibt die Anzahl der Datenbytes an, die beim Hochladen von Daten an den Server gesendet werden.  
  
 In der Regel muss die <xref:System.Net.WebRequest.Method%2A>-Eigenschaft so festgelegt werden, dass sie angibt, dass ein Upload stattfindet, wenn die **ContentLength**-Eigenschaft auf einen Wert größer als 0 (null) festgelegt ist.  
  
## <a name="contenttype-property"></a>ContentType-Eigenschaft  

 Die <xref:System.Net.WebRequest.ContentType%2A>-Eigenschaft stellt spezielle Informationen zur Verfügung, die Sie für Ihr Protokoll an den Server senden müssen, um den Typ des Inhalts, den Sie senden, zu identifizieren. In der Regel ist dies der MIME-Inhaltstyp aller hochgeladenen Daten.  
  
## <a name="credentials-property"></a>Credentials-Eigenschaft  

 Die <xref:System.Net.WebRequest.Credentials%2A>-Eigenschaft enthält Informationen, die zum Authentifizieren der Anforderung mit dem Server erforderlich sind. Sie müssen die Details des Authentifizierungsprozesses für Ihr Protokoll implementieren. Die <xref:System.Net.AuthenticationManager>-Klasse ist verantwortlich für das Authentifizieren von Anforderungen und die Bereitstellung eines Authentifizierungstokens. Die Klasse, die die von Ihrem Protokoll benötigten Anmeldeinformationen bereitstellt, muss die <xref:System.Net.ICredentials>-Schnittstelle implementieren.  
  
## <a name="headers-property"></a>Header-Eigenschaft  

 Die <xref:System.Net.WebRequest.Headers%2A>-Eigenschaft enthält eine beliebige Auflistung von Name/Wert-Paaren der Metadaten, die der Anforderung zugeordnet sind. Alle für das Protokoll erforderlichen Metadaten, die als Name-Wert-Paar ausgedrückt werden, können in die **Header**-Eigenschaft aufgenommen werden. In der Regel müssen diese Informationen festgelegt werden, bevor die <xref:System.Net.WebRequest.GetRequestStream%2A>- oder <xref:System.Net.WebRequest.GetResponse%2A>-Methoden aufgerufen werden. Sobald die Anforderung gestellt wurde, gelten die Metadaten als schreibgeschützt.  
  
 Sie müssen die **Header**-Eigenschaft nicht verwenden, um die Header-Metadaten zu nutzen. Protokollspezifische Metadaten können als Eigenschaften verfügbar gemacht werden. So macht die <xref:System.Net.HttpWebRequest.UserAgent%2A?displayProperty=nameWithType>-Eigenschaft z.B. den HTTP-Header **User-Agent** verfügbar. Wenn Sie die Header-Metadaten als Eigenschaft verfügbar machen, sollten Sie nicht zulassen, dass die gleiche Eigenschaft die **Header**-Eigenschaft verwendet.  
  
## <a name="method-property"></a>Methode-Eigenschaft  

 Die <xref:System.Net.WebRequest.Method%2A>-Eigenschaft enthält das Verb oder die Aktion, die der Server auf Anfrage ausführen soll. Die Standardeinstellung für die **Method**-Eigenschaft muss eine Standardanforderung/-antwort aktivieren, ohne protokollspezifische Eigenschaften festzulegen. Die <xref:System.Net.HttpWebResponse.Method%2A>-Methode wird z.B. standardmäßig auf „GET“ festgelegt, womit eine Ressource von einem Webserver angefordert und die Antwort zurückgegeben wird.  
  
 In der Regel muss die **ContentLength**-Eigenschaft auf einen Wert höher als 0 (null) festgelegt werden, wenn die **Method**-Eigenschaft auf ein Verb oder eine Aktion festgelegt ist, die angeben, dass ein Upload stattfindet.  
  
## <a name="preauthenticate-property"></a>PreAuthenticate-Eigenschaft  

 Anwendungen legen die <xref:System.Net.WebRequest.PreAuthenticate%2A>-Eigenschaft fest, um anzugeben, dass die Authentifizierungsinformationen mit der ursprünglichen Anforderung gesendet werden sollen anstatt auf eine Authentifizierungsaufforderung zu warten. Die **PreAuthenticate**-Eigenschaft ist nur sinnvoll, wenn das Protokoll die Authentifizierungsinformationen unterstützt, die mit der ursprünglichen Anforderung gesendet wurden.  
  
## <a name="proxy-property"></a>Proxy-Eigenschaft  

 Die <xref:System.Net.WebRequest.Proxy%2A>-Eigenschaft enthält eine <xref:System.Net.IWebProxy>-Schnittstelle, die verwendet wird, um auf die angeforderte Ressource zuzugreifen. Die **Proxy**-Eigenschaft ist nur sinnvoll, wenn Ihr Protokoll Proxyanforderungen unterstützt. Sie müssen den Standardproxy festlegen, wenn dieser von Ihrem Protokoll benötigt wird.  
  
 In einigen Umgebungen, z.B. hinter einer Unternehmensfirewall, benötigt Ihr Protokoll möglicherweise einen Proxy. In diesem Fall müssen Sie die **IWebProxy**-Schnittstelle implementieren, um eine Proxyklasse zu erstellen, die für Ihr Protokoll verwendet werden kann.  
  
## <a name="requesturi-property"></a>RequestUri-Eigenschaft  

 Die <xref:System.Net.WebRequest.RequestUri%2A>-Eigenschaft enthält den URI, der an die **WebRequest.Create**-Methode übergeben wurde. Er ist schreibgeschützt und kann nicht geändert werden, sobald **WebRequest** erstellt wurde. Wenn Ihr Protokoll Umleitung unterstützt, kann die Antwort aus einer durch einen anderen URI identifizierten Ressource stammen. Wenn Sie den Zugriff auf den URI, der geantwortet hat, ermöglichen müssen, müssen Sie eine zusätzliche Eigenschaft angeben, die diesen URI enthält.  
  
## <a name="timeout-property"></a>Timeouteigenschaft  

 Die <xref:System.Net.WebRequest.Timeout%2A>-Eigenschaft enthält die abzuwartende Zeitdauer in Millisekunden, bevor die Anforderung ein Timeout und eine Ausnahme auslöst. **Timeout** gilt nur für synchrone Anforderungen durch die <xref:System.Net.WebRequest.GetResponse%2A>-Methode. Asynchrone Anforderungen müssen die <xref:System.Net.WebRequest.Abort%2A>-Methode verwenden, um eine ausstehende Anforderung abzubrechen.  
  
 Das Festlegen der **Timeout**-Eigenschaft ist nur sinnvoll, wenn die protokollspezifische Klasse einen Timeout-Prozess implementiert.  
  
## <a name="abort-method"></a>Abort-Methode  

 Die <xref:System.Net.WebRequest.Abort%2A>-Methode bricht eine ausstehende asynchrone Anforderung an einen Server ab. Nachdem die Anforderung abgebrochen wurde, löst ein Aufruf von **GetResponse**, **BeginGetResponse**, **EndGetResponse**, **GetRequestStream**, **BeginGetRequestStream** oder **EndGetRequestStream** eine <xref:System.Net.WebException> aus, und die <xref:System.Net.WebException.Status%2A>-Eigenschaft ist auf <xref:System.Net.WebExceptionStatus> festgelegt.  
  
## <a name="begingetrequeststream-and-endgetrequeststream-methods"></a>BeginGetRequestStream- und EndGetRequestStream-Methoden  

 Die <xref:System.Net.WebRequest.BeginGetRequestStream%2A>-Methode startet eine asynchrone Anforderung für den Datenstrom, der zum Hochladen von Daten an den Server verwendet wird. Die <xref:System.Net.WebRequest.EndGetRequestStream%2A>-Methode schließt die asynchrone Anforderung ab und gibt den angeforderten Datenstrom zurück. Diese Methoden implementieren die **GetRequestStream**-Methode mithilfe des standardmäßigen asynchronen .NET Framework-Musters.  
  
## <a name="begingetresponse-and-endgetresponse-methods"></a>BeginGetResponse- und EndGetResponse-Methoden  

 Die <xref:System.Net.WebRequest.BeginGetResponse%2A>-Methode beginnt eine asynchrone Anforderung an einen Server. Die <xref:System.Net.WebRequest.EndGetResponse%2A>-Methode schließt die asynchrone Anforderung ab und gibt die angeforderte Antwort zurück. Diese Methoden implementieren die **GetResponse**-Methode mithilfe des standardmäßigen asynchronen .NET Framework-Musters.  
  
## <a name="getrequeststream-method"></a>GetRequestStream-Methode  

 Die <xref:System.Net.WebRequest.GetRequestStream%2A>-Methode gibt einen Datenstrom zurück, der zum Schreiben von Daten an den angeforderten Server verwendet wird. Der zurückgegebene Datenstrom sollte ein lesegeschützter, nicht suchender Datenstrom sein. Er soll einen unidirektionalen Datenstrom darstellen, der an den Server geschrieben wird. Der Datenstrom gibt FALSE für die <xref:System.IO.Stream.CanRead%2A>- und <xref:System.IO.Stream.CanSeek%2A>-Eigenschaften und TRUE für die <xref:System.IO.Stream.CanWrite%2A>-Eigenschaft zurück.  
  
 Die **GetRequestStream**-Methode öffnet in der Regel eine Verbindung mit dem Server und sendet vor der Rückgabe des Datenstroms Headerinformationen, die angeben, dass Daten an den Server gesendet werden. Da **GetRequestStream** die Anforderung startet, dürfen die **Header**-Eigenschaften oder die **ContentLength**-Eigenschaft in der Regel nicht nach dem **GetRequestStream**-Aufruf festgelegt werden.  
  
## <a name="getresponse-method"></a>GetResponse-Methode  

 Die <xref:System.Net.WebRequest.GetResponse%2A>-Methode gibt einen protokollspezifischen Nachfolger der <xref:System.Net.WebResponse>-Klasse zurück, der die Antwort des Servers darstellt. Solange die Anforderung noch nicht durch die **GetRequestStream**-Methode eingeleitet wurde, erstellt die **GetResponse**-Methode eine Verbindung mit der durch **RequestUri** identifizierten Ressource, versendet Headerinformationen, die den Typ der Anforderung angeben, und empfängt dann die Antwort von der Ressource.  
  
 Sobald die **GetResponse**-Methode aufgerufen wird, sollten alle Eigenschaften als schreibgeschützt angesehen werden. **WebRequest**-Instanzen sind für die einmalige Verwendung vorgesehen. Wenn Sie eine andere Anforderung vornehmen möchten, erstellen Sie eine neue **WebRequest**.  
  
 Die **GetResponse**-Methode ist verantwortlich für das Erstellen eines entsprechenden **WebResponse**-Nachfolgers, der die eingehende Antwort enthält.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.WebRequest>
- <xref:System.Net.HttpWebRequest>
- <xref:System.Net.FileWebRequest>
- [Programming Pluggable Protocols (Programmieren austauschbarer Protokolle)](programming-pluggable-protocols.md)
- [Ableiten von WebResponse](deriving-from-webresponse.md)

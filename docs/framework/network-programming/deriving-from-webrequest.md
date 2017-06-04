---
title: "Ableiten von WebRequest | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "WebRequest-Klasse, austauschbare Protokolle"
  - "Protokollspezifische Anforderungshandler"
  - "Senden von Daten, austauschbare Protokolle"
  - "Austauschbare Protokolle, Klassenkriterien"
  - "Internet, austauschbare Protokolle"
  - "Empfangen von Daten, austauschbare Protokolle"
  - "Protokolle, austauschbare"
ms.assetid: 9810c177-973e-43d7-823c-14960bd625ea
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# Ableiten von WebRequest
Die <xref:System.Net.WebRequest>\-Klasse ist eine abstrakte Basisklasse, die die grundlegenden Methoden und Eigenschaften zum Erstellen eines protokollspezifischen Anforderungshandlers bereitstellt, der das austauschbare Protokollmodell .NET Framework passt.  Anwendungen, die die **WebRequest**\-Klasse verwenden, können Daten mit den einzelnen unterstützten Protokolls benötigen, ohne benötigen, um des verwendeten Protokolls anzugeben.  
  
 Zwei Kriterien erfüllt werden müssen, damit eine protokollspezifische Klasse als austauschbares Protokoll verwendet werden kann: Die Klasse muss die <xref:System.Net.IWebRequestCreate>\-Schnittstelle implementieren, und sie muss mit der <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=fullName>\-Methode registrieren.  Die Klasse muss alle abstrakten Methoden und Eigenschaften von **WebRequest** überschreiben, um die austauschbare Schnittstelle bereitzustellen.  
  
 **WebRequest**\-Instanzen werden für einmalige Verwendung vorgesehen, Wenn Sie einen anderen Anwendung um möchten, erstellen Sie ein neues **WebRequest**.  **WebRequest** unterstützt die <xref:System.Runtime.Serialization.ISerializable>\-Schnittstelle, Entwicklern zu ermöglichen, eine Vorlage **WebRequest** zu serialisieren und die Vorlage für zusätzliche Anforderungen erneut zu erstellen.  
  
## IWebRequest\-Erstellungsmethode  
 Die <xref:System.Net.IWebRequestCreate.Create%2A>\-Methode ist für das Initialisieren einer neuen Instanz der Klasse protokollspezifischen zuständig.  Wenn neues **WebRequest** erstellt wird, entspricht der <xref:System.Net.WebRequest.Create%2A?displayProperty=fullName>\-Methode das angeforderte URI mit den URI\-Präfixen ab, die mit der **RegisterPrefix**\-Methode registriert werden.  Die **Create**\-Methode des richtigen protokollspezifischen Nachfolgers muss eine initialisierte Instanz des Nachfolgers zurückgeben, der dem Ausführen eines Standardersuchens\/der Wartetransaktion für das Protokoll kann, ohne protokollspezifischen geänderten Felder zu erfordern.  
  
## ConnectionGroupName\-Eigenschaft  
 Die <xref:System.Net.WebRequest.ConnectionGroupName%2A>\-Eigenschaft wird verwendet, um eine Gruppe Verbindungen zu einer Ressource zu benennen, damit mehrere Anforderungen zu einer einzelnen Verbindung gemacht werden können.  Damit allgemeine Verbindungsnutzung zu implementieren, müssen Sie eine protokollspezifische Methode des Poolings verwenden und Zuweisenverbindungen.  Beispielsweise implementiert die bereitgestellte <xref:System.Net.ServicePointManager>\-Klasse häufige Verbindungsnutzung für die <xref:System.Net.HttpWebRequest>\-Klasse.  Die **ServicePointManager**\-Klasse erstellt <xref:System.Net.ServicePoint>, die eine Verbindung zu einem bestimmten Server für jede Verbindungsgruppe bereitstellt.  
  
## ContentLength\-Eigenschaft  
 Die <xref:System.Net.WebRequest.ContentLength%2A>\-Eigenschaft gibt die Anzahl der Bytes an Daten, die an den Server gesendet werden, wenn die Daten hochgeladen werden.  
  
 In der Regel muss die <xref:System.Net.WebRequest.Method%2A>\-Eigenschaft festgelegt werden, um anzugeben, dass ein Upload ausgeführt werden, wenn die **ContentLength**\-Eigenschaft auf einen Wert festgelegt wird, der größer null ist.  
  
## ContentType\-Eigenschaft  
 Die <xref:System.Net.WebRequest.ContentType%2A>\-Eigenschaft enthält spezielle Informationen, die das Protokoll verlangt, den Server zu senden, um den Inhaltstyp zu identifizieren, den Sie senden.  In der Regel ist dies der MIME\-Inhaltstyp aller hochgeladenen Daten.  
  
## Anmeldeinformationens\-Eigenschaft  
 Die <xref:System.Net.WebRequest.Credentials%2A>\-Eigenschaft enthält die Informationen, die erforderlich sind, um die Anforderung mit dem Server zu authentifizieren.  Sie müssen die Details des Authentifizierungsprozesses für das Protokoll implementieren.  Die <xref:System.Net.AuthenticationManager>\-Klasse ist zum Authentifizieren von Anforderungen und die Bereitstellung eines Authentifizierungstoken zuständig.  Die Klasse, die die Anmeldeinformationen enthält, die durch das Protokoll verwendet werden, muss die <xref:System.Net.ICredentials>\-Schnittstelle implementieren.  
  
## Header\-Eigenschaft  
 Die <xref:System.Net.WebRequest.Headers%2A>\-Eigenschaft enthält eine beliebige Auflistung Name\-Wert\-Paare Metadaten, die mit der Anforderung zugeordnet sind.  Alle Metadaten, die vom Protokoll benötigt werden, das als Name\-Wert\-Paar ausgedrückt werden kann, können in der **Headers**\-Eigenschaft enthalten sind.  In der Regel müssen diese Informationen festgelegt werden, bevor die <xref:System.Net.WebRequest.GetRequestStream%2A> oder <xref:System.Net.WebRequest.GetResponse%2A>\-Methoden aufruft, einmal ist die Anforderung vorgenommen, die Metadaten wird als schreibgeschützt.  
  
 Es ist nicht erforderlich, die **Headers**\-Eigenschaft verwenden, um Headermetadaten zu verwenden.  Protokollspezifische Metadaten können als Eigenschaften verfügbar gemacht werden, beispielsweise macht die <xref:System.Net.HttpWebRequest.UserAgent%2A?displayProperty=fullName>\-Eigenschaft den Header **User\-Agent**  HTTP verfügbar.  Wenn Sie Headermetadaten als Eigenschaft verfügbar machen, sollten Sie nicht zulassen, dass die gleiche Eigenschaft mithilfe der **Headers**\-Eigenschaft festgelegt wird.  
  
## Methoden\-Eigenschaft  
 Die <xref:System.Net.WebRequest.Method%2A>\-Eigenschaft enthält das Verb oder die Aktion, dass die Anforderung den Server anfordert auszuführen.  Der Standardwert für die **Method**\-Eigenschaft muss eine Standardanforderung\/eine Warteaktion aktivieren, ohne protokollspezifischen Eigenschaften zu müssen festgelegt werden.  Zum Beispiel führt die [HttpWebResponse](frlrfSystemNetHttpWebResponseClassMethodTopic)\-Methode den Standardwert an, um abrufen können, die eine Ressource von einem Webserver anfordert und die Antwort zurückgibt.  
  
 In der Regel muss die **ContentLength**\-Eigenschaft auf einen Wert festgelegt werden, der größer null ist, wenn die **Method**\-Eigenschaft zu einem Verb oder einer Aktion festgelegt wird, die angibt, dass ein Upload stattfindet.  
  
## PreAuthenticate\-Eigenschaft  
 Anwendungen legen die <xref:System.Net.WebRequest.PreAuthenticate%2A>\-Eigenschaft fest, um anzugeben, dass Authentifizierungsinformationen mit der ursprünglichen Anforderung, anstatt auf eine Authentifizierungsaufforderung wartenden gesendet werden sollen.  Die **PreAuthenticate**\-Eigenschaft ist nur sinnvoll, wenn das Protokoll die Authentifizierungsinformationen unterstützt, die mit der ursprünglichen Anforderung gesendet werden.  
  
## Proxy\-Eigenschaft  
 Die <xref:System.Net.WebRequest.Proxy%2A>\-Eigenschaft enthält eine <xref:System.Net.IWebProxy>\-Schnittstelle, die verwendet wird, um auf die angeforderte Ressource zuzugreifen.  Die **Proxy**\-Eigenschaft ist sinnvoll, wenn das Protokoll Proxy Anforderungen unterstützt.  Sie müssen den Standardproxy festlegen, wenn Sie durch das Protokoll benötigt wird.  
  
 In einigen Umgebungen wie hinter einer Firewall des Unternehmens, wird das Protokoll erforderlich sein, einen Proxy verwendet.  In diesem Fall müssen Sie die **IWebProxy**\-Schnittstelle implementieren, um eine Proxyklasse zu erstellen, die für das Protokoll funktioniert.  
  
## RequestUri\-Eigenschaft  
 Die <xref:System.Net.WebRequest.RequestUri%2A>\-Eigenschaft enthält den URI, das der **WebRequest.Create**\-Methode übergeben wurde.  Es ist schreibgeschützt und kann nicht geändert werden, sobald **WebRequest** erstellt wurde.  Wenn das Protokoll Umleitung unterstützt, kann die Antwort von einer Ressource stammen, die durch ein anderes URI angegeben wird.  Wenn Sie Zugriff auf den URI bieten müssen, das reagierte, müssen Sie eine zusätzliche Eigenschaft bereitstellen, die dieser URI enthält.  
  
## TIMEOUTeigenschaft  
 Die <xref:System.Net.WebRequest.Timeout%2A>\-Eigenschaft enthält die Zeitspanne, in Millisekunden, um vor den einer und \-Würfen warten eine Ausnahme.  **Timeout** gilt nur für die synchronen Anforderungen zu, die mit der <xref:System.Net.WebRequest.GetResponse%2A>\-Methode gemacht werden, asynchrone Anforderungen müssen die <xref:System.Net.WebRequest.Abort%2A>\-Methode verwenden, um eine ausstehende Anforderung abzubrechen.  
  
 Die **Timeout**\-Eigenschaft festzulegen ist sinnvoll, wenn die protokollspezifische Klasse einen TIMEOUTprozess implementiert.  
  
## Abbruchs\-Methode  
 Die <xref:System.Net.WebRequest.Abort%2A>\-Methode bricht eine ausstehende asynchrone Anforderung zu einem Server ab.  Nachdem die Anforderung abgebrochen wurde, **GetResponse** dazu, lösen **BeginGetResponse**, **EndGetResponse**, **GetRequestStream**, **BeginGetRequestStream** oder **EndGetRequestStream**<xref:System.Net.WebException> mit dem <xref:System.Net.WebException.Status%2A> festgelegt [RequestCanceled](frlrfSystemNetWebExceptionStatusClassTopic) aus.  
  
## Methoden BeginGetRequestStream und EndGetRequestStream  
 Die <xref:System.Net.WebRequest.BeginGetRequestStream%2A>\-Methode beginnt ein asynchrones Anforderungen für den Stream, der verwendet wird, um Daten an den Server hochzuladen.  Die <xref:System.Net.WebRequest.EndGetRequestStream%2A>\-Methode enthält die asynchrone Anforderung ab und gibt den angeforderten Stream zurück.  Diese Methoden implementieren die **GetRequestStream** \-Methode mit dem Standard\-.NETFramework\-asynchronenMusters.  
  
## Methoden BeginGetResponse und EndGetResponse  
 Die <xref:System.Net.WebRequest.BeginGetResponse%2A>\-Methode beginnt eine asynchrone Anforderung auf einen Server.  Die <xref:System.Net.WebRequest.EndGetResponse%2A>\-Methode enthält die asynchrone Anforderung ab und gibt die angeforderte Antwort zurück.  Diese Methoden implementieren die **GetResponse** \-Methode mit dem Standard\-.NETFramework\-asynchronenMusters.  
  
## GetRequestStream\-Methode  
 Die <xref:System.Net.WebRequest.GetRequestStream%2A>\-Methode gibt einen Stream zurück, der verwendet wird, um Daten zum angeforderten Server zu schreiben.  Der zurückgegebene Stream sollte ein lesegeschützter Streams handeln, der nicht durchsucht; Es wird als unidirektionaler Stream von Daten bestimmt, die dem Server geschrieben wird.  Die Streamrückgaben falsch für die <xref:System.IO.Stream.CanRead%2A> und <xref:System.IO.Stream.CanSeek%2A>\-Eigenschaften und true für die <xref:System.IO.Stream.CanWrite%2A>\-Eigenschaft.  
  
 Die **GetRequestStream**\-Methode in der Regel wird eine Verbindung zum Server und, bevor der Stream zurückgibt, sendet Headerinformationen, die diese Daten werden an den Server gesendet angibt.  Da **GetRequestStream** die Anforderung beginnt, wird das Festlegen **Header** keine Eigenschaften oder der **ContentLength**\-Eigenschaft in der Regel nicht zulässig, nachdem **GetRequestStream** aufgerufen hat.  
  
## GetResponse\-Methode  
 Die <xref:System.Net.WebRequest.GetResponse%2A>\-Methode gibt einen protokollspezifischen Nachfolger der <xref:System.Net.WebResponse>\-Klasse zurück, die die Antwort vom Server darstellt.  Es sei denn, die Anforderung bereits durch die **GetRequestStream**\-Methode initiiert wurde, erstellt die **GetResponse**\-Methode eine Verbindung mit der Ressource, die von **RequestUri** identifiziert wird, sendet die Headerinformationen, die den Typ der Anforderung angibt, die ausgeführt wird und empfängt dann die Antwort der Ressource.  
  
 Sobald die **GetResponse**\-Methode aufgerufen wird, sollten alle Eigenschaften als schreibgeschützt betrachtet werden.  **WebRequest**\-Instanzen werden für einmalige Verwendung vorgesehen, Wenn Sie eine weitere Anforderung darstellen möchten, sollten Sie neues **WebRequest** erstellen.  
  
 Die **GetResponse**\-Methode ist zum Erstellen eines entsprechenden **WebResponse** Nachfolgers, um die eingehende Antwort zu enthalten zuständig.  
  
## Siehe auch  
 <xref:System.Net.WebRequest>   
 <xref:System.Net.HttpWebRequest>   
 <xref:System.Net.FileWebRequest>   
 [Programmieren austauschbarer Protokolle](../../../docs/framework/network-programming/programming-pluggable-protocols.md)   
 [Ableiten von WebResponse](../../../docs/framework/network-programming/deriving-from-webresponse.md)
---
title: "Neues in Windows Communication Foundation 4.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF [WCF], Neues"
  - "Windows Communication Foundation [WCF], Neues"
ms.assetid: 7e93fe73-af93-46b5-9f63-32f761ee40cf
caps.latest.revision: 35
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 35
---
# Neues in Windows Communication Foundation 4.5
In diesem Thema werden die neuen Funktionen von [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] erläutert.  
  
## WCF\-Vereinfachungsfunktionen  
 Es wurde viel unternommen, um die Entwicklung und Verwaltung von WCF 4.5\-Anwendungen zu vereinfachen.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][WCF\-Vereinfachungsfunktionen](../../../docs/framework/wcf/wcf-simplification-features.md).  
  
### Taskbasierte asynchrone Unterstützung  
 Durch **Dienstverweis hinzufügen** werden standardmäßig asynchrone Methoden für Dienstvorgänge generiert, die Tasks zurückgeben.Dies erfolgt sowohl für synchrone als auch für asynchrone Methoden.Auf diese Weise können die Dienstvorgänge mithilfe des neuen taskbasierten asynchronen Programmiermodells asynchron aufgerufen werden.Wenn Sie die generierte Proxymethode aufrufen, erstellt WCF ein Taskobjekt, das den asynchronen Vorgang darstellt, und gibt diesen Task an Sie zurück.Der Task wird zusammen mit dem Vorgang abgeschlossen. Daher können Sie einen asynchronen Vorgang als taskbasierten asynchronen Vorgang implementieren.Weitere Informationen finden Sie unter [Synchrone und asynchrone Vorgänge](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).  
  
### Vereinfachte generierte Konfigurationsdateien  
 Wenn Sie einen Dienstverweis in Visual Studio hinzufügen oder das SvcUtil.exe\-Tool verwenden, wird eine Clientkonfigurationsdatei generiert.In früheren Versionen von WCF enthielten diese Konfigurationsdateien den Wert jeder Bindungseigenschaft, auch wenn deren Wert dem Standardwert entsprach.In WCF 4.5 enthalten die generierten Konfigurationsdateien nur die Bindungseigenschaften, die auf einen nicht standardmäßigen Wert festgelegt sind.  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [WCF\-Vereinfachungsfunktionen](../../../docs/framework/wcf/wcf-simplification-features.md)  
  
### Vertrag zuerst\-Entwicklung  
 WCF unterstützt jetzt die Vertrag zuerst\-Entwicklung.Das svcutl.exe\-Tool verfügt über einen \/serviceContract\-Schalter, der das Generieren von Dienst\- und Datenverträgen von einem WSDL\-Dokument ermöglicht.  
  
### Hinzufügen eines Dienstverweises aus einem Projekt für die portable Teilmenge  
 Projekte für portable Teilmengen ermöglichen es Programmierern von .NET\-Assemblys, eine einzelne Quellstruktur zu verwalten und das System mit Unterstützung mehrerer .NET\-Plattformen \(Desktop, Silverlight, Windows Phone und XBOX\) aufzubauen.Projekte für portable Teilmengen verweisen nur auf portable .NET\-Bibliotheken, die einer .NET Framework\-Assembly entsprechen, die von einer beliebigen .NET\-Kernplattform verwendet werden kann.Die Entwicklererfahrung ist identisch mit dem Hinzufügen eines Dienstverweises innerhalb einer beliebigen anderen WCF\-Clientanwendung.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Hinzufügen eines Dienstverweises in einem Projekt für die portable Teilmenge](../../../docs/framework/wcf/add-service-reference-in-a-portable-subset-project.md).  
  
### Geänderter Standard für den ASP.NET\-Kompatibilitätsmodus  
 WCF bietet einen ASP.NET\-Kompatibilitätsmodus, der Entwicklern beim Schreiben von WCF\-Diensten vollständigen Zugriff auf die Funktionen in der ASP.NET\-HTTP\-Pipeline gewährt.Um den Modus zu verwenden, müssen Sie das `aspNetCompatibilityEnabled`\-Attribut im [\<serviceHostingEnvironment\>](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)\-Abschnitt von **web.config** auf **True** festlegen.Außerdem muss die `RequirementsMode`\-Eigenschaft für jeden Dienst in dieser appDomain für <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> auf <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> oder <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> festgelegt sein.Standardmäßig ist <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> jetzt auf <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> festgelegt.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][What's New in Windows Communication Foundation](../../../docs/framework/wcf/whats-new.md) und [WCF\-Dienste und ASP.NET](../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
### Neue Standardwerte für Transporte  
 Um die Konfiguration zu vereinfachen, wurden einige Standardwerte der Transporteigenschaft geändert.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][WCF\-Vereinfachungsfunktionen](../../../docs/framework/wcf/wcf-simplification-features.md).  
  
### XmlDictionaryReaderQuotas  
 <xref:System.Xml.XmlDictionaryReaderQuotas> enthält konfigurierbare Kontingentwerte für XML\-Wörterbuchreader, die den Arbeitsspeicher begrenzen, der beim Erstellen einer Nachricht von einem Encoder verwendet wird.Diese Kontingente sind konfigurierbar, allerdings wurden die Standardwerte geändert, um die Wahrscheinlichkeit zu verringern, dass sie von einem Entwickler explizit festgelegt werden müssen.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][WCF\-Vereinfachungsfunktionen](../../../docs/framework/wcf/wcf-simplification-features.md).  
  
### WCF\-Konfigurationsvalidierung  
 Im Rahmen des Buildvorgangs innerhalb von Visual Studio werden WCF\-Konfigurationsdateien jetzt für die Attribute überprüft, die innerhalb des Projekts definiert sind.Eine Liste mit Validierungsfehlern oder Warnungen wird in Visual Studio angezeigt, wenn die Validierung fehlschlägt.  
  
### XML\-Editor\-QuickInfos  
 Um neuen und bereits erfahrenen Entwicklern von WCF\-Diensten die Konfiguration zu erleichtern, zeigt der XML\-Editor in Visual Studio nun QuickInfos für jedes Konfigurationselement, das Teil der Dienstkonfigurationsdatei ist, und dessen Eigenschaften an.  
  
## Verbesserungen beim Streaming  
 Es wurde Unterstützung für echtes asynchrones Streaming hinzugefügt, bei dem die Senderseite keine Threads blockiert, wenn die Empfängerseite keine Nachrichten liest bzw. Nachrichten langsam liest. Dies erhöht die Skalierbarkeit.Die Einschränkung des Nachrichtenpuffers, die gilt, wenn ein Client eine gestreamte Nachricht an einen von IIS gehosteten WCF\-Dienst sendet, wurde aufgehoben.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][WCF\-Vereinfachungsfunktionen](../../../docs/framework/wcf/wcf-simplification-features.md).  
  
## Einfacheres Verfügbarmachen eines Endpunkts über HTTPS mit IIS  
 Eine HTTPS\-Protokollzuordnung wurde hinzugefügt, um das Verfügbarmachen eines Endpunkts über HTTPS zu vereinfachen.Um einen HTTPS\-Endpunkt zu aktivieren, stellen Sie sicher, dass für die Website eine HTTPS\-Bindung und ein SSL\-Zertifikat konfiguriert wurden. Aktivieren Sie dann einfach HTTPS für das virtuelle Verzeichnis, von dem der Dienst gehostet wird.Wenn Metadaten für den Dienst aktiviert sind, werden sie ebenfalls über HTTPS verfügbar gemacht.  
  
## Generieren eines einzelnen WSDL\-Dokuments  
 WSDL\-Verarbeitungsstapel einiger Drittanbieter sind nicht in der Lage, WSDL\-Dokumente zu verarbeiten, die über Abhängigkeiten mit anderen Dokumenten in Form von "xsd: import" verfügen.In WCF können Sie jetzt angeben, dass alle WSDL\-Informationen in einem einzelnen Dokument zurückgegeben werden.Um ein einzelnes WSDL\-Dokument anzufordern, fügen Sie "? singleWSDL" an den URI an, wenn Sie Metadaten vom Dienst anfordern.  
  
## WebSocket\-Unterstützung  
 WebSockets ist eine Technologie, die die echte bidirektionale Kommunikation über die Ports 80 und 443 ermöglicht, wobei die Leistungsmerkmale denen von TCP ähneln.Um die Kommunikation über einen WebSocket\-Transport zu unterstützen, wurden zwei neue Bindungen hinzugefügt.<xref:System.ServiceModel.NetHttpBinding> und <xref:System.ServiceModel.NetHttpsBinding>.Weitere Informationen finden Sie unter [Vom System bereitgestellte Bindungen](../../../docs/framework/wcf/system-provided-bindings.md).  
  
## Neue Standardwerte für Transporte  
 Anhand der folgenden Tabelle erfahren Sie, welche Einstellungen geändert wurden und wo Sie zusätzliche Informationen finden.  
  
|Eigenschaft|On|Neuer Standard|Weitere Informationen finden Sie unter|  
|-----------------|--------|--------------------|--------------------------------------------|  
|channelInitializationTimeout|<xref:System.ServiceModel.NetTcpBinding>|30 Sekunden|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.ChannelInitializationTimeout%2A>|  
|listenBacklog|<xref:System.ServiceModel.NetTcpBinding>|12 \* Anzahl der Prozessoren|<xref:System.ServiceModel.NetTcpBinding.ListenBacklog%2A>|  
|maxPendingAccepts|ConnectionOrientedTransportBindingElement<br /><br /> SMSvcHost.exe|2 \* Anzahl der Prozessoren für den Transport<br /><br /> 4 \* Anzahl der Prozessoren für "SMSvcHost.exe"|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingAccepts%2A> [Configuring the Net.TCP Port Sharing Service](http://msdn.microsoft.com/de-de/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)|  
|maxPendingConnections|ConnectionOrientedTransportBindingElement|12 \* Anzahl der Prozessoren|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingConnections%2A>|  
|receiveTimeout|SMSvcHost.exe|30 Sekunden|[Configuring the Net.TCP Port Sharing Service](http://msdn.microsoft.com/de-de/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)|  
  
## XML\-Editor\-QuickInfos  
 Um neuen und bereits erfahrenen Entwicklern von WCF\-Diensten die Konfiguration zu erleichtern, zeigt der XML\-Editor in Visual Studio nun QuickInfos für jedes Konfigurationselement, das Teil der Dienstkonfigurationsdatei ist, und dessen Eigenschaften an.  
  
## Konfigurieren von WCF\-Diensten in Code  
 Mit [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] können Entwickler Dienste mithilfe von Konfigurationsdateien oder Code konfigurieren.Konfigurationsdateien sind nützlich, wenn ein Dienst konfiguriert werden muss, nachdem er bereitgestellt wurde.Bei der Verwendung von Konfigurationsdateien muss ein IT\-Experte nur die Konfigurationsdatei aktualisieren, es ist keine Neukompilierung erforderlich.Konfigurationsdateien können jedoch komplex und schwierig zu pflegen sein.Das Debuggen von Konfigurationsdateien wird nicht unterstützt. Auf Konfigurationselemente wird über den Namen verwiesen, was die Erstellung von Konfigurationsdateien fehleranfällig und schwierig macht.[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ermöglicht auch das Konfigurieren von Diensten im Code.In früheren Versionen von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] \(4.0 und früher\) war das Konfigurieren von Diensten im Code in selbstgehosteten Szenarien einfach, weil die <xref:System.ServiceModel.ServiceHost>\-Klasse die Möglichkeit bot, Endpunkte und Verhaltensweisen vor dem Aufrufen von **ServiceHost.Open** zu konfigurieren.In webgehosteten Szenarien haben Sie jedoch keinen Zugriff auf die <xref:System.ServiceModel.ServiceHost>\-Klasse.Um einen webgehosteten Dienst zu konfigurieren, mussten Sie eine <xref:System.ServiceModel.ServiceHostFactory> erstellen, durch die ein <xref:System.ServiceModel.ServiceHost> erstellt und alle erforderlichen Konfigurationsschritte ausgeführt wurden.Ab .NET 4.5 bietet [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] eine einfachere Möglichkeit, selbstgehostete und webgehostete Dienste im Code zu konfigurieren.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Konfigurieren von WCF\-Diensten in Code](../../../docs/framework/wcf/configuring-wcf-services-in-code.md).  
  
## ChannelFactory\-Caching  
 WCF\-Clientanwendungen verwenden die <xref:System.ServiceModel.ChannelFactory%601>\-Klasse, um einen Kommunikationskanal mit einem WCF\-Dienst zu erstellen.Die Erstellung von <xref:System.ServiceModel.ChannelFactory%601>\-Instanzen verursacht einigen Mehraufwand, da sie die folgenden Vorgänge umfasst:  
  
1.  Erstellen der <xref:System.ServiceModel.Description.ContractDescription>\-Struktur  
  
2.  Reflektieren aller erforderlichen CLR\-Typen  
  
3.  Erstellen des Kanalstapels  
  
4.  Freigeben von Ressourcen  
  
 Um den Mehraufwand zu minimieren, kann WCF Kanalfactorys zwischenspeichern, wenn Sie einen WCF\-Clientproxy verwenden.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Kanalfactory und Zwischenspeichern](../../../docs/framework/wcf/feature-details/channel-factory-and-caching.md).  
  
## Komprimierung und binärer Encoder  
 Ab WCF 4.5 bietet der binäre WCF\-Encoder Komprimierungsunterstützung.Der Komprimierungstyp wird mit der <xref:System.ServiceModel.Channels.BinaryMessageEncodingElement.CompressionFormat%2A>\-Eigenschaft konfiguriert.Sowohl der Client als auch der Dienst müssen die <xref:System.ServiceModel.Channels.BinaryMessageEncodingElement.CompressionFormat%2A>\-Eigenschaft konfigurieren.Die Komprimierung unterstützt die HTTP\-, HTTPS\- und TCP\-Protokolle.Wenn ein Client angibt, dass die Komprimierung verwendet werden soll, der Dienst aber keine Komprimierung unterstützt, wird eine Ausnahme über einen Protokollkonflikt ausgelöst.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Auswählen eines Nachrichtenencoders](../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
  
## UDP  
 Es wurde Unterstützung für einen UDP\-Transport hinzugefügt, der es Entwicklern ermöglicht, Dienste mit "fire and forget"\-Messaging \(Auslösen und Vergessen\) zu schreiben.Ein Client sendet eine Nachricht an einen Dienst und erwartet von diesem keine Antwort.  
  
## Unterstützung mehrerer Authentifizierungen  
 Es werden jetzt mehrere Authentifizierungsmodi, so wie von IIS unterstützt, für einen einzelnen WCF\-Endpunkt unterstützt, wenn der HTTP\-Transport und die Transportsicherheit verwendet werden.IIS ermöglicht es Ihnen, mehrere Authentifizierungsmodi für ein virtuelles Verzeichnis zu aktivieren. Durch diese Funktion kann ein einzelner WCF\-Endpunkt mehrere Authentifizierungsmodi unterstützen, die für das virtuelle Verzeichnis aktiviert sind, in dem der WCF\-Dienst gehostet wird.  
  
## IDN\-Unterstützung  
 Unterstützung für WCF\-Dienste mit IDNs \(Internationalized Domain Names\) wurde hinzugefügt.Weitere Informationen finden Sie unter [WCF und internationale Domänennamen](../../../docs/framework/wcf/feature-details/wcf-and-internationalized-domain-names.md).  
  
## HttpClient  
 Eine neue Klasse mit dem Namen <xref:System.Net.Http.HttpClient> wurde hinzugefügt, um das Arbeiten mit HTTP\-Anforderungen erheblich zu vereinfachen.Weitere Informationen finden Sie unter [Vorbereiten von Apps für soziale Netzwerke und für die Verbindung mit HTTP\-Diensten](http://go.microsoft.com/fwlink/?LinkId=231886) und im [Beispiel für einen HTTP\-Client](http://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664).  
  
## IntelliSense\-Konfiguration  
 Attributwerte in den Konfigurationsdateien für benutzerdefinierte Attribute, die im Projekt definiert sind, unterstützen jetzt IntelliSense, um das schnelle und präzise Arbeiten mit Konfigurationen zu erleichtern.  
  
## QuickInfos zur Konfiguration  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Elemente und \-Attribute verfügen jetzt über QuickInfos im XML\-Editor, um den Verwendungszweck des Elements oder Attributs einfacher und genauer zu identifizieren.  
  
## Einfügen von Daten als Klassen  
 In einem WCF\-Projekt können die in XML definierten Datentypen \(die in einem Dienst verfügbar gemacht sind\) direkt in eine Codepage eingefügt werden.Der XML\-Typ wird als CLR\-Typ eingefügt.Ausführliche Informationen finden Sie unter [Generieren von Datentypklassen aus XML](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md).  
  
## WebServiceHost und Standardendpunkte  
 In Visual Studio 2010 wurde von WebServiceHost automatisch ein Standardendpunkt erstellt, unabhängig davon, ob ein Endpunkt explizit angegeben wurde oder nicht.In Visual Studio 2012 erstellt WebServiceHost nur einen Standardendpunkt, wenn keine Endpunkte explizit hinzugefügt wurden.Wenn der Client den Standardendpunkt erwartet, können Sie einen Endpunkt explizit hinzufügen und den Client darauf verweisen.Alternativ können Sie WCF anweisen, zum früheren Verhalten zurückzukehren, indem Sie der Anwendungskonfigurationsdatei folgende Einstellung hinzufügen:  
  
```xml  
<appSettings>  
    <add key="wcf:webservicehost:enableautomaticendpointscompatability" value="true"/>  
  </appSettings>  
  
```  
  
## IHttpCookieContainerManager  
 Diese von <xref:System.ServiceModel.Channels.HttpChannelFactory> verfügbar gemachte Schnittstelle vereinfacht die Verwendung von Cookies auf der Clientseite.Wenn **AllowCookies** für die Bindung auf **True** festgelegt ist, können Sie mit folgendem Code auf Cookies zugreifen:  
  
```csharp  
IHttpCookieContainerManager cookieManager = factory.GetProperty<IHttpCookieContainerManager>();   
System.Net.CookieContainer container = cookieManager.CookieContainer;  
  
```  
  
 Anschließend können die Cookies unter Verwendung von <xref:System.Net.CookieContainer> abgerufen oder festgelegt werden.Wenn **AllowCookies** auf **False** festgelegt ist, können Sie die Cookies mit <xref:System.ServiceModel.OperationContext> manuell abrufen und in anderen Anforderungen unter Verwendung eines anderen <xref:System.ServiceModel.OperationContext> oder Meldungsinspektors senden.Die IHttpCookieContainerManager\-Schnittstelle ermöglicht es Ihnen, einen Benutzer bei einem Dienst zu authentifizieren und das vom Dienst zurückgegebene Authentifizierungscookie zum Authentifizieren bei anderen Diensten zu verwenden.
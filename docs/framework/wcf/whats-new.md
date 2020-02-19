---
title: Neues in Windows Communication Foundation 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], what's new
- Windows Communication Foundation [WCF], what's new
ms.assetid: 7e93fe73-af93-46b5-9f63-32f761ee40cf
ms.openlocfilehash: b22266efe2e775acd04c400cf9da50bffab28183
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449503"
---
# <a name="whats-new-in-windows-communication-foundation-45"></a>Neues in Windows Communication Foundation 4.5

In diesem Thema werden die neuen Features von Windows Communication Foundation (WCF) Version 4,5 erläutert.

## <a name="wcf-simplification-features"></a>WCF-Vereinfachungsfunktionen

Es wurde viel unternommen, um die Entwicklung und Verwaltung von WCF 4.5-Anwendungen zu vereinfachen. Weitere Informationen finden Sie unter [WCF-Vereinfachungs Funktionen](wcf-simplification-features.md).

### <a name="task-based-async-support"></a>Aufgabenbasierte asynchrone Unterstützung

Durch {1}Dienstverweis hinzufügen{2} werden standardmäßig asynchrone Methoden für Dienstvorgänge generiert, die Tasks zurückgeben. Dies erfolgt sowohl für synchrone als auch für asynchrone Methoden. Auf diese Weise können die Dienstvorgänge mithilfe des neuen aufgabenbasierten asynchronen Programmiermodells asynchron aufgerufen werden. Wenn Sie die generierte Proxymethode aufrufen, erstellt WCF ein Taskobjekt, das den asynchronen Vorgang darstellt, und gibt diesen Task an Sie zurück. Die Aufgabe wird abgeschlossen, wenn der Vorgang abgeschlossen ist. Beim Implementieren eines asynchronen Vorgangs können Sie ihn als aufgabenbasierten asynchronen Vorgang implementieren. Weitere Informationen finden Sie unter [synchrone und asynchrone Vorgänge](synchronous-and-asynchronous-operations.md).

### <a name="simplified-generated-configuration-files"></a>Vereinfachte generierte Konfigurationsdateien

Wenn Sie einen Dienstverweis in Visual Studio hinzufügen oder das SvcUtil.exe-Tool verwenden, wird eine Clientkonfigurationsdatei generiert. In früheren Versionen von WCF enthielten diese Konfigurationsdateien den Wert jeder Bindungseigenschaft, auch wenn deren Wert dem Standardwert entsprach. In WCF 4.5 enthalten die generierten Konfigurationsdateien nur die Bindungseigenschaften, die auf einen nicht standardmäßigen Wert festgelegt sind.

Weitere Informationen finden Sie unter [WCF-Vereinfachungs Funktionen](wcf-simplification-features.md).

### <a name="contract-first-development"></a>Vertrag zuerst-Entwicklung

WCF unterstützt jetzt die Vertrag zuerst-Entwicklung. Die Datei "Svcutil. exe" verfügt über einen/ServiceContract-Schalter-Switch, mit dem Sie Dienst-und Datenverträge aus einem WSDL-Dokument generieren können.

### <a name="add-service-reference-from-a-portable-subset-project"></a>Hinzufügen eines Dienstverweises aus einem Projekt für die portable Teilmenge

Portable Teilmengen Projekte ermöglichen es .net-assemblyprogrammierern, eine einzelne Quell Struktur und ein Buildsystem zu verwalten, während mehrere .net-Plattformen (Desktop, Silverlight, Windows Phone und Xbox) unterstützt werden. Projekte für Portable Teilmengen verweisen nur auf Portable .NET-Bibliotheken, die Assemblys sind, die auf jeder .NET-Plattform verwendet werden können. Die Entwicklererfahrung ist identisch mit dem Hinzufügen eines Dienstverweises innerhalb einer beliebigen anderen WCF-Clientanwendung. Weitere Informationen finden Sie unter [Dienstverweis hinzufügen in einem Projekt für eine Portable Teilmenge](add-service-reference-in-a-portable-subset-project.md).

### <a name="aspnet-compatibility-mode-default-changed"></a>Geänderter Standard für den ASP.NET-Kompatibilitätsmodus

WCF bietet einen ASP.NET-Kompatibilitätsmodus, der Entwicklern beim Schreiben von WCF-Diensten vollständigen Zugriff auf die Funktionen in der ASP.NET-HTTP-Pipeline gewährt. Um diesen Modus zu verwenden, müssen Sie das `aspNetCompatibilityEnabled`-Attribut im [\<ServiceHost->](../configure-apps/file-schema/wcf/servicehostingenvironment.md) Abschnitt der Datei "Web. config" auf "true" festlegen. Außerdem muss für jeden Dienst in dieser AppDomain die `RequirementsMode`-Eigenschaft in der <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> auf <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> oder <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>festgelegt sein. Standardmäßig ist <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> jetzt auf <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>festgelegt. Weitere Informationen finden Sie unter [WCF-Dienste und ASP.net](./feature-details/wcf-services-and-aspnet.md).

### <a name="new-transport-default-values"></a>Neue Standardwerte für Transporte

Um die Konfiguration zu vereinfachen, wurden einige Standardwerte der Transporteigenschaft geändert. Weitere Informationen finden Sie unter [WCF-Vereinfachungs Funktionen](wcf-simplification-features.md).

### <a name="xmldictionaryreaderquotas"></a>XmlDictionaryReaderQuotas

<xref:System.Xml.XmlDictionaryReaderQuotas> enthält konfigurierbare Kontingentwerte für XML-Wörterbuchreader, die den Arbeitsspeicher begrenzen, der beim Erstellen einer Nachricht von einem Encoder verwendet wird. Diese Kontingente sind konfigurierbar, allerdings wurden die Standardwerte geändert, um die Wahrscheinlichkeit zu verringern, dass sie von einem Entwickler explizit festgelegt werden müssen. Weitere Informationen finden Sie unter [WCF-Vereinfachungs Funktionen](wcf-simplification-features.md).

### <a name="wcf-configuration-validation"></a>WCF-Konfigurationsvalidierung

Im Rahmen des Buildvorgangs innerhalb von Visual Studio werden WCF-Konfigurationsdateien jetzt für die Attribute überprüft, die innerhalb des Projekts definiert sind. Eine Liste mit Validierungsfehlern oder Warnungen wird in Visual Studio angezeigt, wenn die Validierung fehlschlägt.

### <a name="xml-editor-tooltips"></a>XML-Editor-QuickInfos

Um neuen und bereits erfahrenen Entwicklern von WCF-Diensten die Konfiguration zu erleichtern, zeigt der XML-Editor in Visual Studio nun QuickInfos für jedes Konfigurationselement, das Teil der Dienstkonfigurationsdatei ist, und dessen Eigenschaften an.

## <a name="streaming-improvements"></a>Verbesserungen beim Streaming

Es wurde Unterstützung für echtes asynchrones Streaming hinzugefügt, bei dem die Senderseite keine Threads blockiert, wenn die Empfängerseite keine Nachrichten liest bzw. Nachrichten langsam liest. Dies erhöht die Skalierbarkeit. Die Einschränkung des Nachrichtenpuffers, die gilt, wenn ein Client eine gestreamte Nachricht an einen von IIS gehosteten WCF-Dienst sendet, wurde aufgehoben. Weitere Informationen finden Sie unter [WCF-Vereinfachungs Funktionen](wcf-simplification-features.md).

## <a name="simplifying-exposing-an-endpoint-over-https-with-iis"></a>Einfacheres Verfügbarmachen eines Endpunkts über HTTPS mit IIS

Eine HTTPS-Protokollzuordnung wurde hinzugefügt, um das Verfügbarmachen eines Endpunkts über HTTPS zu vereinfachen. Um einen HTTPS-Endpunkt zu aktivieren, stellen Sie sicher, dass für die Website eine HTTPS-Bindung und ein SSL-Zertifikat konfiguriert wurden. Aktivieren Sie dann einfach HTTPS für das virtuelle Verzeichnis, von dem der Dienst gehostet wird. Wenn Metadaten für den Dienst aktiviert sind, werden sie ebenfalls über HTTPS verfügbar gemacht.

## <a name="generating-a-single-wsdl-document"></a>Generieren eines einzelnen WSDL-Dokuments

WSDL-Verarbeitungsstapel einiger Drittanbieter sind nicht in der Lage, WSDL-Dokumente zu verarbeiten, die über Abhängigkeiten mit anderen Dokumenten in Form von "xsd: import" verfügen. In WCF können Sie jetzt angeben, dass alle WSDL-Informationen in einem einzelnen Dokument zurückgegeben werden. Zum Anfordern eines einzelnen WSDL-Dokuments wird "? singlewsdl" an den URI angehängt, wenn Metadaten vom Dienst angefordert werden.

## <a name="websocket-support"></a>WebSocket-Unterstützung

WebSockets ist eine Technologie, die die echte bidirektionale Kommunikation über die Ports 80 und 443 ermöglicht, wobei die Leistungsmerkmale denen von TCP ähneln. Um die Kommunikation über einen WebSocket-Transport zu unterstützen, wurden zwei neue Bindungen hinzugefügt. <xref:System.ServiceModel.NetHttpBinding> und <xref:System.ServiceModel.NetHttpsBinding>: Weitere Informationen finden Sie unter: vom [System bereitgestellte Bindungen](system-provided-bindings.md).

## <a name="new-transport-default-values"></a>Neue Standardwerte für Transporte

Anhand der folgenden Tabelle erfahren Sie, welche Einstellungen geändert wurden und wo Sie zusätzliche Informationen finden.

|Eigenschaft|Ein|Neuer Standard|Weitere Informationen finden Sie unter .|
|--------------|--------|-----------------|------------------------------|
|channelInitializationTimeout|<xref:System.ServiceModel.NetTcpBinding>|30 Sekunden|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.ChannelInitializationTimeout%2A>|
|listenBacklog|<xref:System.ServiceModel.NetTcpBinding>|12 * Anzahl der Prozessoren|<xref:System.ServiceModel.NetTcpBinding.ListenBacklog%2A>|
|maxPendingAccepts|ConnectionOrientedTransportBindingElement<br /><br /> SMSvcHost.exe|2 * Anzahl der Prozessoren für den Transport<br /><br /> 4 \* Anzahl der Prozessoren für "SMSvcHost. exe"|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingAccepts%2A> [Konfigurieren des net. TCP-Port Freigabe diensdienstanbieter](./feature-details/configuring-the-net-tcp-port-sharing-service.md)|
|maxPendingConnections|ConnectionOrientedTransportBindingElement|12 * Anzahl der Prozessoren|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingConnections%2A>|
|receiveTimeout|SMSvcHost.exe|30 Sekunden|[Konfigurieren des Net.TCP-Portfreigabediensts](./feature-details/configuring-the-net-tcp-port-sharing-service.md)|

## <a name="xml-editor-tooltips"></a>XML-Editor-QuickInfos

Um neuen und bereits erfahrenen Entwicklern von WCF-Diensten die Konfiguration zu erleichtern, zeigt der XML-Editor in Visual Studio nun QuickInfos für jedes Konfigurationselement, das Teil der Dienstkonfigurationsdatei ist, und dessen Eigenschaften an.

## <a name="configuring-wcf-services-in-code"></a>Konfigurieren von WCF-Diensten in Code

Windows Communication Foundation (WCF) ermöglicht es Entwicklern, Dienste mithilfe von Konfigurationsdateien oder Code zu konfigurieren. Konfigurationsdateien sind nützlich, wenn ein Dienst konfiguriert werden muss, nachdem er bereitgestellt wurde. Bei der Verwendung von Konfigurationsdateien muss ein IT-Experte nur die Konfigurationsdatei aktualisieren, es ist keine Neukompilierung erforderlich. Konfigurationsdateien können jedoch komplex und schwierig zu pflegen sein. Das Debuggen von Konfigurationsdateien wird nicht unterstützt. Auf Konfigurationselemente wird über den Namen verwiesen, was die Erstellung von Konfigurationsdateien fehleranfällig und schwierig macht. WCF ermöglicht Ihnen außerdem das Konfigurieren von Diensten im Code. In früheren Versionen von WCF (4,0 und früher) war das Konfigurieren von Diensten im Code in selbstgeh osteten Szenarien ganz einfach. mit der <xref:System.ServiceModel.ServiceHost>-Klasse haben Sie die Möglichkeit, Endpunkte und Verhaltensweisen vor dem Aufrufen von Service Host. Open zu konfigurieren. In webgehosteten Szenarien haben Sie jedoch keinen Zugriff auf die <xref:System.ServiceModel.ServiceHost>-Klasse. Um einen webgehosteten Dienst zu konfigurieren, mussten Sie eine `System.ServiceModel.ServiceHostFactory` erstellen, durch die ein <xref:System.ServiceModel.Activation.ServiceHostFactory> erstellt und alle erforderlichen Konfigurationsschritte ausgeführt wurden. Ab .NET 4,5 bietet WCF eine einfachere Möglichkeit, selbstgeh ostete und im Internet gehostete Dienste im Code zu konfigurieren. Weitere Informationen finden Sie unter [Konfigurieren von WCF-Diensten im Code](configuring-wcf-services-in-code.md).

## <a name="channelfactory-caching"></a>ChannelFactory-Caching

WCF-Clientanwendungen verwenden die <xref:System.ServiceModel.ChannelFactory%601>-Klasse, um einen Kommunikationskanal mit einem WCF-Dienst zu erstellen. Die Erstellung von <xref:System.ServiceModel.ChannelFactory%601>-Instanzen verursacht einigen Mehraufwand, da sie die folgenden Vorgänge umfasst:

1. Erstellen der <xref:System.ServiceModel.Description.ContractDescription>-Struktur

2. Reflektieren aller erforderlichen CLR-Typen

3. Erstellen des Kanalstapels

4. Freigeben von Ressourcen

Um den Mehraufwand zu minimieren, kann WCF Kanalfactorys zwischenspeichern, wenn Sie einen WCF-Clientproxy verwenden. Weitere Informationen finden Sie unter [Kanalfactory und Caching](./feature-details/channel-factory-and-caching.md).

## <a name="compression-and-the-binary-encoder"></a>Komprimierung und binärer Encoder

Ab WCF 4.5 bietet der binäre WCF-Encoder Komprimierungsunterstützung. Der Komprimierungstyp wird mit der <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.CompressionFormat%2A>-Eigenschaft konfiguriert. Sowohl der Client als auch der Dienst müssen die <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement.CompressionFormat%2A>-Eigenschaft konfigurieren. Die Komprimierung unterstützt die HTTP-, HTTPS- und TCP-Protokolle. Wenn ein Client angibt, dass die Komprimierung verwendet werden soll, der Dienst aber keine Komprimierung unterstützt, wird eine Ausnahme über einen Protokollkonflikt ausgelöst. Weitere Informationen finden Sie unter [Auswählen eines Nachrichten Encoders](./feature-details/choosing-a-message-encoder.md).

## <a name="udp"></a>UDP

Es wurde Unterstützung für einen UDP-Transport hinzugefügt, mit dem Entwickler Dienste schreiben können, die "Fire and Forget"-Messaging verwenden. Ein Client sendet eine Nachricht an einen Dienst und erwartet von diesem keine Antwort.

## <a name="multiple-authentication-support"></a>Unterstützung mehrerer Authentifizierungen

Es werden jetzt mehrere Authentifizierungsmodi, so wie von IIS unterstützt, für einen einzelnen WCF-Endpunkt unterstützt, wenn der HTTP-Transport und die Transportsicherheit verwendet werden. IIS ermöglicht es Ihnen, mehrere Authentifizierungsmodi für ein virtuelles Verzeichnis zu aktivieren. Durch diese Funktion kann ein einzelner WCF-Endpunkt mehrere Authentifizierungsmodi unterstützen, die für das virtuelle Verzeichnis aktiviert sind, in dem der WCF-Dienst gehostet wird.

## <a name="idn-support"></a>IDN-Unterstützung

Unterstützung für WCF-Dienste mit IDNs (Internationalized Domain Names) wurde hinzugefügt. Weitere Informationen finden Sie unter [WCF und internationalisierte Domänen Namen](./feature-details/wcf-and-internationalized-domain-names.md).

## <a name="httpclient"></a>HttpClient

Eine neue Klasse mit dem Namen <xref:System.Net.Http.HttpClient> wurde hinzugefügt, um das Arbeiten mit HTTP-Anforderungen erheblich zu vereinfachen. Weitere Informationen finden Sie unter [Erstellen von Apps für soziale Netzwerke und verbinden mit HTTP-Diensten](https://channel9.msdn.com/Events/BUILD/BUILD2011/PLAT-581T) und dem [http-Client Beispiel](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664).

## <a name="configuration-intellisense"></a>IntelliSense-Konfiguration

Attributwerte in den Konfigurationsdateien für benutzerdefinierte Attribute, die im Projekt definiert sind, unterstützen jetzt IntelliSense, um das schnelle und präzise Arbeiten mit Konfigurationen zu erleichtern.

## <a name="configuration-tooltips"></a>QuickInfos zur Konfiguration

WCF-Elemente und-Attribute verfügen jetzt über Quick Infos im XML-Editor, um den Zweck des Elements oder Attributs leichter und präziser zu identifizieren.

## <a name="paste-data-as-classes"></a>Einfügen von Daten als Klassen

In einem WCF-Projekt können die in XML definierten Datentypen (die in einem Dienst verfügbar gemacht sind) direkt in eine Codepage eingefügt werden. Der XML-Typ wird als CLR-Typ eingefügt. Weitere Informationen finden Sie [unter Erstellen von Datentyp Klassen aus XML](generating-data-type-classes-from-xml.md) .

## <a name="webservicehost-and-default-endpoints"></a>WebServiceHost und Standardendpunkte

In Visual Studio 2010 wurde von WebServiceHost automatisch ein Standardendpunkt erstellt, unabhängig davon, ob ein Endpunkt explizit angegeben wurde oder nicht. In Visual Studio 2012 und höher erstellt Webservice Host nur dann einen Standard Endpunkt, wenn keine Endpunkte explizit hinzugefügt werden. Wenn der Client den Standard Endpunkt erwartet, können Sie explizit einen Endpunkt hinzufügen und den Client darauf verweisen. Alternativ können Sie WCF anweisen, zum früheren Verhalten zurückzukehren, indem Sie der Anwendungskonfigurationsdatei folgende Einstellung hinzufügen:

```xml
<appSettings>
    <add key="wcf:webservicehost:enableautomaticendpointscompatability" value="true"/>
  </appSettings>
```

## <a name="ihttpcookiecontainermanager"></a>IHttpCookieContainerManager

Diese von <xref:System.ServiceModel.Channels.IChannelFactory%601> verfügbar gemachte Schnittstelle vereinfacht die Verwendung von Cookies auf der Clientseite. Wenn {1}AllowCookies{2} für die Bindung auf {3}True{4} festgelegt ist, können Sie mit folgendem Code auf Cookies zugreifen:

```csharp
IHttpCookieContainerManager cookieManager = factory.GetProperty<IHttpCookieContainerManager>();
System.Net.CookieContainer container = cookieManager.CookieContainer;
```

Anschließend können die Cookies unter Verwendung von <xref:System.Net.CookieContainer> abgerufen oder festgelegt werden. Wenn <xref:System.ServiceModel.OperationContext>AllowCookies<xref:System.ServiceModel.OperationContext> auf {3}False{4} festgelegt ist, können Sie die Cookies mit {5} manuell abrufen und in anderen Anforderungen unter Verwendung eines anderen {6} oder Meldungsinspektors senden. Die IHttpCookieContainerManager-Schnittstelle ermöglicht es Ihnen, einen Benutzer bei einem Dienst zu authentifizieren und das vom Dienst zurückgegebene Authentifizierungscookie zum Authentifizieren bei anderen Diensten zu verwenden.

---
title: WCF-Vereinfachungsfunktionen
ms.date: 03/30/2017
ms.assetid: 4535a511-6064-4da0-b361-80262a891663
ms.openlocfilehash: f4c5d1c0dc5aa9df92368de1266044db3a6c294a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57467180"
---
# <a name="wcf-simplification-features"></a>WCF-Vereinfachungsfunktionen

In diesem Thema werden neue Funktionen erörtert, die das Schreiben von WCF-Anwendungen vereinfachen.

## <a name="simplified-generated-configuration-files"></a>Vereinfachte generierte Konfigurationsdateien

Wenn Sie einen Dienstverweis in Visual Studio hinzufügen oder das SvcUtil.exe-Tool verwenden, wird eine Clientkonfigurationsdatei generiert. In früheren Versionen von WCF enthielten diese Konfigurationsdateien den Wert jeder Bindungseigenschaft, auch wenn deren Wert dem Standardwert entsprach. In WCF 4.5 enthalten die generierten Konfigurationsdateien nur die Bindungseigenschaften, die auf einen nicht standardmäßigen Wert festgelegt sind.

Im folgenden Beispiel wird eine mit WCF 3.0 generierte Konfigurationsdatei gezeigt.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
    <system.serviceModel>
        <bindings>
            <basicHttpBinding>
                <binding name="BasicHttpBinding_IService1" closeTimeout="00:01:00"
                    openTimeout="00:01:00" receiveTimeout="00:10:00" sendTimeout="00:01:00"
                    allowCookies="false" bypassProxyOnLocal="false"
                    hostNameComparisonMode="StrongWildcard" maxBufferSize="65536"
                    maxBufferPoolSize="524288" maxReceivedMessageSize="65536"
                    messageEncoding="Text" textEncoding="utf-8" transferMode="Buffered"
                    useDefaultWebProxy="true">
                    <readerQuotas maxDepth="32" maxStringContentLength="8192"
                        maxArrayLength="16384" maxBytesPerRead="4096"
                        maxNameTableCharCount="16384" />
                    <security mode="None">
                        <transport clientCredentialType="None" proxyCredentialType="None"
                            realm="" />
                        <message clientCredentialType="UserName" algorithmSuite="Default" />
                    </security>
                </binding>
            </basicHttpBinding>
        </bindings>
        <client>
            <endpoint address="http://localhost:36906/Service1.svc" binding="basicHttpBinding"
                bindingConfiguration="BasicHttpBinding_IService1" contract="IService1"
                name="BasicHttpBinding_IService1" />
        </client>
    </system.serviceModel>
</configuration>
```

Im folgenden Beispiel wird eine mit WCF 4.5 generierte Konfigurationsdatei gezeigt.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
    <system.serviceModel>
        <bindings>
            <basicHttpBinding>
                <binding name="BasicHttpBinding_IService1" />
            </basicHttpBinding>
        </bindings>
        <client>
            <endpoint address="http://localhost:36906/Service1.svc" binding="basicHttpBinding"
                bindingConfiguration="BasicHttpBinding_IService1" contract="IService1"
                name="BasicHttpBinding_IService1" />
        </client>
    </system.serviceModel>
</configuration>
```

## <a name="contract-first-development"></a>Vertrag zuerst-Entwicklung

WCF unterstützt jetzt die Vertrag zuerst-Entwicklung. Das svcutil.exe-Tool verfügt über einen/ServiceContract-Schalter zum Generieren von Dienst- und Datenverträgen aus einem WSDL-Dokument ermöglicht.

## <a name="add-service-reference-from-a-portable-subset-project"></a>Hinzufügen eines Dienstverweises aus einem Projekt für die portable Teilmenge

Projekte für Portable Teilmengen ermöglichen .NET Assembly-Programmierern, die eine einzelne Quellstruktur zu verwalten und Buildsystem Unterstützung mehrerer .NET Implementierungen (Desktop, Silverlight, Windows Phone und XBOX). Projekte für Portable Teilmengen verweisen nur auf .NET portable Bibliotheken, die eine .NET Framework-Assembly sind, die auf jeder .NET-Implementierung verwendet werden kann. Die Entwicklererfahrung ist identisch mit dem Hinzufügen eines Dienstverweises innerhalb einer beliebigen anderen WCF-Clientanwendung. Weitere Informationen finden Sie unter [Hinzufügen eines Dienstverweises in einem Projekt der portablen Teilmenge](../../../docs/framework/wcf/add-service-reference-in-a-portable-subset-project.md).

## <a name="aspnet-compatibility-mode-default-changed"></a>Geänderter Standard für den ASP.NET-Kompatibilitätsmodus

WCF bietet einen ASP.NET-Kompatibilitätsmodus, der Entwicklern beim Schreiben von WCF-Diensten vollständigen Zugriff auf die Funktionen in der ASP.NET-HTTP-Pipeline gewährt. Um diesen Modus verwenden zu können, müssen Sie festlegen der `aspNetCompatibilityEnabled` Attribut auf "true", in der [ \<ServiceHostingEnvironment >](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) Abschnitt der Datei "Web.config". Außerdem muss die `RequirementsMode`-Eigenschaft für jeden Dienst in dieser appDomain für <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> auf <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> oder <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required> festgelegt sein. Standardmäßig <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> ist nun so festgelegt <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> und die Standardvorlage für die WCF-Dienst die Vorlage legt Anwendung die `aspNetCompatibilityEnabled` Attribut `true`. Weitere Informationen finden Sie unter [Neuigkeiten in Windows Communication Foundation 4.5](../../../docs/framework/wcf/whats-new.md) und [WCF-Dienste und ASP.NET](../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).

## <a name="streaming-improvements"></a>Verbesserungen beim Streaming

- Der WCF wurde neue Unterstützung für asynchrones Streaming hinzugefügt. Um das asynchrone Streaming zu aktivieren, fügen Sie dem Diensthost das <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>-Endpunktverhalten hinzu und legen dessen <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior.AsynchronousSendEnabled%2A>-Eigenschaft auf `true` fest. Dies begünstigt die Skalierbarkeit, wenn ein Dienst gestreamte Nachrichten an mehrere Clients mit niedriger Lesegeschwindigkeit sendet. Von WCF wird nicht mehr ein Thread pro Client blockiert; der Thread steht für weitere Clients zur Verfügung.

- Einschränkungen im Hinblick auf die Nachrichtenpufferung bei von IIS gehosteten Diensten wurden aufgehoben. Wenn in früheren WCF-Versionen eine Nachricht für einen IIS-gehosteten Dienst einging, der die Nachrichtenübertragung per Stream nutzte, wurde die gesamte Nachricht vor der Übertragung an WCF von ASP.NET gepuffert. Dieser Vorgang beanspruchte viel Arbeitsspeicher. Da diese Pufferung in .NET 4.5 entfernt wurde, können IIS-gehostete WCF-Dienste jetzt mit der Verarbeitung des eingehenden Datenstroms beginnen, bevor die Nachricht vollständig empfangen wurde. Das schafft die Voraussetzungen für echtes Streaming. Dadurch kann WCF sofort auf Nachrichten reagieren, was eine verbesserte Leistung bedeutet. Außerdem muss für das ASP.NET-Größenlimit für eingehende Anforderungen `maxRequestLength` kein Wert mehr angegeben werden. Wenn diese Eigenschaft festgelegt ist, wird sie ignoriert. Weitere Informationen zu `maxRequestLength` finden Sie unter [ \<HttpRuntime >-Konfigurationselements](https://go.microsoft.com/fwlink/?LinkId=223344). Sie müssen dennoch zum Konfigurieren von MaxAllowedContentLength für Weitere Informationen finden Sie unter [Grenzwerte für die IIS-Anforderungen](https://go.microsoft.com/fwlink/?LinkId=225908).

## <a name="new-transport-default-values"></a>Neue Standardwerte für Transporte

Anhand der folgenden Tabelle erfahren Sie, welche Einstellungen geändert wurden und wo Sie zusätzliche Informationen finden.

|Eigenschaft|Ein|Neuer Standard|Weitere Informationen|
|--------------|--------|-----------------|----------------------|
|channelInitializationTimeout|<xref:System.ServiceModel.NetTcpBinding>|30 Sekunden|Diese Eigenschaft bestimmt die Zeit, die eine TCP-Verbindung beanspruchen darf, um sich über das .NET Framework-Protokoll zu authentifizieren. Ein Client muss vorab einige Daten senden, bevor der Server über genügend Informationen zum Ausführen der Authentifizierung verfügt. Für dieses Timeout wurde bewusst ein geringerer Wert als für ReceiveTimeout (10 Minuten) festgelegt, damit Serververbindungen von böswilligen, nicht authentifizierten Clients nicht zu lange aufrechterhalten werden können. Der Standardwert ist 30 Sekunden. Weitere Informationen zu <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.ChannelInitializationTimeout%2A>|
|listenBacklog|<xref:System.ServiceModel.NetTcpBinding>|16 * Anzahl der Prozessoren|Diese Eigenschaft auf Socketebene gibt an, wie viele Anforderungen, deren Annahme aussteht, in die Warteschlange eingereiht werden dürfen. Sobald die listenBacklog-Warteschlange voll ist, werden neue Socketanforderungen abgelehnt. Weitere Informationen zu <xref:System.ServiceModel.NetTcpBinding.ListenBacklog%2A>|
|maxPendingAccepts|ConnectionOrientedTransportBindingElement<br /><br /> SMSvcHost.exe|2 * Anzahl der Prozessoren für den Transport<br /><br /> 4 \* Anzahl der Prozessoren für SMSvcHost.exe|Diese Eigenschaft begrenzt die Anzahl der Kanäle, die auf dem Server auf einen Listener warten können. Weist MaxPendingAccepts einen zu geringen Wert auf, ist der Zeitraum, in dem alle wartenden Kanäle mit der Verarbeitung von Verbindungen begonnen haben, zu kurz, als dass neue Kanäle das Lauschen gestartet haben könnten. Wenn während dieses Zeitraums eine Verbindungsanforderung eingeht, wird sie fehlschlagen, da auf dem Server noch nicht auf neue Verbindungen gelauscht wird. Diese Eigenschaft kann konfiguriert werden, indem die <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingConnections%2A>-Eigenschaft auf einen höheren Wert festgelegt wird. Weitere Informationen finden Sie unter <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingAccepts%2A> und [konfigurieren den Net.TCP-Portfreigabedienst](../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)|
|maxPendingConnections|ConnectionOrientedTransportBindingElement|12 * Anzahl der Prozessoren|Diese Eigenschaft steuert, wie viele Verbindungen von einem Transport akzeptiert, vom ServiceModel-Verteiler jedoch noch nicht ausgewählt wurden. Um diesen Wert festzulegen, verwenden Sie `MaxConnections` für die Bindung oder `maxOutboundConnectionsPerEndpoint` für das Bindungselement. Weitere Informationen zu <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingConnections%2A>|
|receiveTimeout|SMSvcHost.exe|30 Sekunden|Diese Eigenschaft gibt das Timeout für das Lesen der TCP-Rahmendaten und das Verteilen der zugrunde liegenden Verbindungen an. Dadurch wird die Dauer beschränkt, die der SMSvcHost.exe-Dienst mit dem Lesen der Präambel einer eingehenden Verbindung beschäftigt ist. Weitere Informationen finden Sie unter [konfigurieren den Net.TCP-Portfreigabedienst](../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).|

> [!NOTE]
> Diese neuen Standardwerte werden nur verwendet, wenn Sie den WCF-Dienst auf einem Computer mit .NET Framework 4.5 bereitstellen. Wenn Sie denselben Dienst auf einem Computer mit .NET Framework 4.0 bereitstellen, werden die Standardwerte von .NET Framework 4.0 verwendet. In solchen Fällen wird empfohlen, die Einstellungen explizit zu konfigurieren.

## <a name="xmldictionaryreaderquotas"></a>XmlDictionaryReaderQuotas

<xref:System.Xml.XmlDictionaryReaderQuotas> enthält konfigurierbare Kontingentwerte für XML-Wörterbuchreader, die den Arbeitsspeicher begrenzen, der beim Erstellen einer Nachricht von einem Encoder verwendet wird. Während diese Kontingente konfigurierbar sind, wurden die Standardwerte geändert, um die Wahrscheinlichkeit zu vermindern, dass sie von einem Entwickler explizit festgelegt werden müssen. Das `MaxReceivedMessageSize`-Kontingent wurde nicht geändert und kann den Arbeitsspeicherverbrauch weiterhin einschränken. So entfällt die Notwendigkeit, komplexe <xref:System.Xml.XmlDictionaryReaderQuotas> zu überwachen. In der folgenden Tabelle sind die Kontingente, die neuen Standardwerte und eine kurze Erläuterung zum Verwendungszweck der einzelnen Kontingente enthalten.

|Kontingentname|Standardwert|Beschreibung|
|----------------|-------------------|-----------------|
|<xref:System.Xml.XmlDictionaryReaderQuotas.MaxArrayLength%2A>|Int32.MaxValue|Ruft die maximal zulässige Arraylänge ab und legt sie fest. Dieses Kontingent schränkt die maximale Größe eines Arrays von Primitiven ein, einschließlich Bytearrays, die vom XML-Reader zurückgegeben werden. Der Arbeitsspeicherverbrauch im XML-Reader selbst wird mit diesem Kontingent nicht eingeschränkt, jedoch in der Komponente, die den Reader verwendet. Wenn <xref:System.Runtime.Serialization.DataContractSerializer> z.&#160;B. einen Reader verwendet, der mit <xref:System.Xml.XmlDictionaryReaderQuotas.MaxArrayLength%2A>gesichert ist, werden keine Bytearrays deserialisiert, deren Größe dieses Kontingent überschreitet.|
|<xref:System.Xml.XmlDictionaryReaderQuotas.MaxBytesPerRead%2A>|Int32.MaxValue|Ruft die bei jedem Lesevorgang zurückgegebenen maximal zulässigen Bytes ab und legt sie fest. Dieses Kontingent beschränkt die Anzahl der Bytes, die in einem einzelnen Vorgang beim Lesen des Starttags des Elements und dessen Attributen gelesen werden. (In Fällen ohne Streaming wird der Elementname selbst nicht in die Berechnung des Kontingents einbezogen.) Bei zu vielen XML-Attributen kann die Verarbeitungszeit übermäßig lange dauern, da die Attributnamen auf Eindeutigkeit überprüft werden müssen. <xref:System.Xml.XmlDictionaryReaderQuotas.MaxBytesPerRead%2A> mindert dieses Risiko.|
|<xref:System.Xml.XmlDictionaryReaderQuotas.MaxDepth%2A>|Tiefe von 128 Knoten|Diese Kontingent schränkt die maximale Schachtelungstiefe von XML-Elementen ein. <xref:System.Xml.XmlDictionaryReaderQuotas.MaxDepth%2A> interagiert mit <xref:System.Xml.XmlDictionaryReaderQuotas.MaxBytesPerRead%2A>: Der Reader behält stets Daten für das aktuelle Element und alle seiner übergeordneten Elemente im Arbeitsspeicher, weshalb der maximale Arbeitsspeicherverbrauch proportional zum Produkt aus diesen beiden Einstellungen ist. Wenn Sie ein tief geschachteltes Objektdiagramm deserialisieren, ist das Deserialisierungsprogramm gezwungen, auf den gesamten Stapel zuzugreifen und eine nicht behebbare <xref:System.StackOverflowException>auszulösen. Ein direkter Zusammenhang besteht zwischen der XML-Schachtelung und der Objektschachtelung sowohl für <xref:System.Runtime.Serialization.DataContractSerializer> als auch für <xref:System.Xml.Serialization.XmlSerializer>. <xref:System.Xml.XmlDictionaryReaderQuotas.MaxDepth%2A> wird verwendet, um dieses Risiko zu mindern.|
|<xref:System.Xml.XmlDictionaryReaderQuotas.MaxNameTableCharCount%2A>|Int32.MaxValue|Dieses Kontingent beschränkt die maximale Anzahl von Zeichen, die in einer Nametable zulässig sind. Die Nametable enthält bestimmte Zeichenfolgen (z. B. Namespaces and Präfixe), die beim Verarbeiten von XML-Dokumenten auftreten. Da diese Zeichenfolgen im Arbeitsspeicher gepuffert werden, kann mit diesem Kontingent eine übermäßige Pufferung verhindert werden, wenn die Zeichenfolgen erwartungsgemäß gestreamt werden sollen.|
|<xref:System.Xml.XmlDictionaryReaderQuotas.MaxStringContentLength%2A>|Int32.MaxValue|Dieses Kontingent schränkt die maximale Größe der Zeichenfolgen ein, die vom XML-Reader zurückgegeben werden. Der Arbeitsspeicherverbrauch im XML-Reader selbst wird mit diesem Kontingent nicht eingeschränkt, jedoch in der Komponente, die den Reader verwendet. Wenn <xref:System.Runtime.Serialization.DataContractSerializer> z.&#160;B. einen Reader verwendet, der mit <xref:System.Xml.XmlDictionaryReaderQuotas.MaxStringContentLength%2A>gesichert ist, werden keine Zeichenfolgen deserialisiert, deren Größe dieses Kontingent überschreitet.|

> [!IMPORTANT]
> Finden Sie unter "Sicheres Verwenden von XML" unter [Sicherheitsüberlegungen zu Daten](../../../docs/framework/wcf/feature-details/security-considerations-for-data.md) für Weitere Informationen zum Schützen Ihrer Daten.

> [!NOTE]
> Diese neuen Standardwerte werden nur verwendet, wenn Sie den WCF-Dienst auf einem Computer mit .NET Framework 4.5 bereitstellen. Wenn Sie denselben Dienst auf einem Computer mit .NET Framework 4.0 bereitstellen, werden die Standardwerte von .NET Framework 4.0 verwendet. In solchen Fällen wird empfohlen, die Einstellungen explizit zu konfigurieren.

## <a name="wcf-configuration-validation"></a>WCF-Konfigurationsvalidierung

Im Rahmen des Buildvorgangs innerhalb von Visual Studio werden WCF-Konfigurationsdateien jetzt überprüft. Eine Liste mit Validierungsfehlern oder Warnungen wird in Visual Studio angezeigt, wenn die Validierung fehlschlägt.

## <a name="xml-editor-tooltips"></a>XML-Editor-QuickInfos

Um neuen und bereits erfahrenen Entwicklern von WCF-Diensten die Konfiguration zu erleichtern, zeigt der XML-Editor in Visual Studio nun QuickInfos für jedes Konfigurationselement, das Teil der Dienstkonfigurationsdatei ist, und dessen Eigenschaften an.

## <a name="basichttpbinding-improvements"></a>BasicHttpBinding-Verbesserungen

1. Ermöglicht es einem einzelnen WCF-Endpunkt, auf verschiedene Authentifizierungsmodi zu reagieren.

2. Ermöglicht die Steuerung der Sicherheitseinstellungen eines WCF-Diensts durch IIS.

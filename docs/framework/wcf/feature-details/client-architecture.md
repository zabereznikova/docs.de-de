---
title: Clientarchitektur
ms.date: 03/30/2017
ms.assetid: 02624403-0d77-41cb-9a86-ab55e98c7966
ms.openlocfilehash: d2a7c25b73562155a7120ecee4998b0de364ca45
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295105"
---
# <a name="client-architecture"></a>Clientarchitektur

Anwendungen verwenden Windows Communication Foundation (WCF)-Client Objekte zum Aufrufen von Dienst Vorgängen. In diesem Thema werden WCF-Client Objekte, WCF-Client Kanäle und deren Beziehungen zur zugrunde liegenden Kanal Architektur erläutert. Eine grundlegende Übersicht über WCF-Client Objekte finden Sie unter Übersicht über den [WCF-Client](../wcf-client-overview.md). Weitere Informationen zur Kanal Ebene finden Sie unter [Erweitern der Kanal Ebene](../extending/extending-the-channel-layer.md).  
  
## <a name="overview"></a>Übersicht  

 Mit der Laufzeit des Dienst Modells werden WCF-Clients erstellt, die aus folgendem bestehen:  
  
- Eine automatisch generierte Clientimplementierung eines Dienstvertrags, der Aufrufe Ihres Anwendungscodes in ausgehende Nachrichten umwandelt und Antwortnachrichten in Ausgabeparameter und Rückgabewerte, die von Ihrer Anwendung abgerufen werden können.  
  
- Eine Implementierung der Steuerungsschnittstelle (<xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>), die verschiedene Schnittstellen gruppiert und Zugriff auf die Steuerungsfunktionalität bietet, vor allem die Möglichkeit, die Clientsitzung zu schließen und den Kanal zu verwerfen.  
  
- Ein Clientkanal, der auf Grundlage der von der verwendeten Bindung angegebenen Konfigurationseinstellungen erstellt wird.  
  
 Anwendungen können solche Clients Bedarfs gesteuert erstellen, indem Sie entweder über eine <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> oder eine Instanz einer <xref:System.ServiceModel.ClientBase%601> abgeleiteten Klasse erstellen, die vom [Service Model Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)generiert wird. Diese vorgefertigten Clientklassen kapseln und delegieren an eine Clientkanalimplementierung, die durch eine <xref:System.ServiceModel.ChannelFactory> dynamisch erstellt wird. Deshalb stehen der Clientkanal und die Kanalfactory, die diese hervorbringen, bei dieser Erläuterung im Zentrum des Interesses.  
  
## <a name="client-objects-and-client-channels"></a>Clientobjekte und Clientkanäle  

 Die Basisschnittstelle von WCF-Clients ist die- <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> Schnittstelle, die die Kern Client Funktionalität sowie die grundlegenden Kommunikations Objektfunktionen von <xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType> , die Kontext Funktionalität von <xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType> und das erweiterbare Verhalten von verfügbar macht <xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType> .  
  
 Die <xref:System.ServiceModel.IClientChannel>-Schnittstelle definiert jedoch keinen Dienstvertrag. Diese werden von der Dienstvertragschnittstelle deklariert (in der Regel mit einem Tool wie dem Service [Model Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)). WCF-Client Typen erweitern sowohl <xref:System.ServiceModel.IClientChannel> als auch die Ziel-Dienstvertragschnittstelle, damit Anwendungen Vorgänge direkt aufrufen können und auch Zugriff auf Client seitige Lauf Zeitfunktionen haben. Beim Erstellen eines WCF-Clients werden WCF <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> -Objekte die Informationen bereitstellt, die zum Erstellen einer Laufzeit erforderlich sind, mit der der konfigurierte Dienst Endpunkt verbunden werden kann.  
  
 Wie bereits erwähnt, müssen die beiden WCF-Client Typen konfiguriert werden, bevor Sie Sie verwenden können. Die einfachsten WCF-Client Typen sind Objekte, die von abgeleitet werden <xref:System.ServiceModel.ClientBase%601> (oder, <xref:System.ServiceModel.DuplexClientBase%601> Wenn der Dienstvertrag ein Duplex Vertrag ist). Sie können diese Typen mithilfe eines Konstruktors erstellen, der programmgesteuert konfiguriert wird, oder durch Verwenden einer Konfigurationsdatei, die direkt aufgerufen wird, um Dienstvorgänge aufzurufen. Eine grundlegende Übersicht über- <xref:System.ServiceModel.ClientBase%601> Objekte finden Sie unter Übersicht über den [WCF-Client](../wcf-client-overview.md).  
  
 Der zweite Typ wird zur Laufzeit von einem Aufruf der <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>-Methode generiert. Anwendungen, die eine strenge Steuerung der Kommunikations Besonderheiten betreffen, verwenden in der Regel diesen Clienttyp, der als *Client Kanal Objekt* bezeichnet wird, da dadurch eine direktere Interaktion als die zugrunde liegende Client Laufzeit und das Channelsystem möglich ist.  
  
## <a name="channel-factories"></a>Kanalfactorys  

 Die Klasse, die für das Erstellen der zugrunde liegenden Laufzeit verantwortlich ist, die Clientaufrufe unterstützt, ist die <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>-Klasse. WCF-Client Objekte und WCF-Client Kanal Objekte verwenden ein- <xref:System.ServiceModel.ChannelFactory%601> Objekt zum Erstellen von-Instanzen <xref:System.ServiceModel.ClientBase%601> . das abgeleitete Client Objekt kapselt die Verarbeitung der Kanalfactory, aber für eine Reihe von Szenarios ist es durchaus sinnvoll, die Kanalfactory direkt zu verwenden. Das am häufigsten vorkommende Szenario ist, wenn Sie wiederholt aus einer bereits vorhandenen Factory neue Clientkanäle erstellen möchten. Wenn Sie ein-Client Objekt verwenden, können Sie die zugrunde liegende Kanalfactory von einem WCF-Client Objekt abrufen, indem Sie die- <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A?displayProperty=nameWithType> Eigenschaft aufrufen.  
  
 Bei Kanalfactorys muss beachtet werden, dass sie neue Instanzen von Clientkanälen für die ihnen zur Verfügung stehende Konfiguration erstellen, bevor sie <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> aufrufen. Wenn Sie <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> (oder <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> , <xref:System.ServiceModel.ClientBase%601.CreateChannel%2A?displayProperty=nameWithType> oder einen Vorgang für ein WCF-Client Objekt) aufgerufen haben, können Sie die Kanalfactory nicht ändern und erwarten, dass Kanäle zu verschiedenen Dienst Instanzen gelangen, auch wenn Sie lediglich die zielend Punkt Adresse ändern. Wenn Sie ein Clientobjekt oder einen Clientkanal mit einer anderen Konfiguration erstellen möchten, müssen Sie zunächst eine neue Kanalfactory erstellen.  
  
 Weitere Informationen zu verschiedenen Problemen bei der Verwendung von WCF-Client Objekten und WCF-Client Kanälen finden Sie unter [zugreifen auf Dienste mithilfe eines WCF-Clients](accessing-services-using-a-client.md).  
  
 In den folgenden beiden Abschnitten wird die Erstellung und Verwendung von WCF-Client Kanal Objekten beschrieben.  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>Erstellen eines neuen WCF-Clientkanalobjekts  

 Um die Verwendung eines Clientkanals zu illustrieren, wird davon ausgegangen, dass der folgende Dienstvertrag generiert wurde.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Um eine Verbindung mit einem `ISampleService`-Dienst herzustellen, verwenden Sie die generierte Vertragsschnittstelle direkt mit einer Kanalfactory (<xref:System.ServiceModel.ChannelFactory%601>). Sobald Sie eine Kanalfactory für einen bestimmten Vertrag erstellt und konfiguriert haben, können Sie die <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>-Methode aufrufen, um die Clientkanalobjekte zurückzugeben, die Sie für die Kommunikation mit einem `ISampleService`-Dienst verwenden können.  
  
 Beim Verwenden der <xref:System.ServiceModel.ChannelFactory%601> -Klasse mit einer Dienstvertragschnittstelle muss diese in eine <xref:System.ServiceModel.IClientChannel> -Schnittstelle umgewandelt werden, um den Kanal explizit zu öffnen, zu schließen oder abzubrechen. Zum Erleichtern der Arbeit generiert das Tool Svcutil.exe auch eine Hilfsschnittstelle, die die Dienstvertragschnittstelle und <xref:System.ServiceModel.IClientChannel> implementiert, wodurch die Interaktion mit der Clientkanalinfrastruktur ohne Umwandlung ermöglicht wird. Im folgenden Code wird die Definition eines Hilfsclientkanals, der den vorangehenden Dienstvertrag implementiert, veranschaulicht.  
  
 [!code-csharp[C_GeneratedCodeFiles#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#13)]  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>Erstellen eines neuen WCF-Clientkanalobjekts  

 Wenn Sie einen Clientkanal zum Verbinden mit einem `ISampleService`-Dienst verwenden möchten, verwenden Sie die generierte Vertragsschnittstelle (oder die Hilfsversion) direkt mit einer Kanalfactory, wobei Sie den Typ der Vertragsschnittstelle als Typparameter übergeben. Sobald Sie eine Kanalfactory für einen bestimmten Vertrag erstellt und konfiguriert haben, können Sie die <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType>-Methode aufrufen, um die Clientkanalobjekte zurückzugeben, die Sie für die Kommunikation mit einem `ISampleService`-Dienst verwenden können.  
  
 Die Clientkanalobjekte implementieren bei ihrer Erstellung <xref:System.ServiceModel.IClientChannel> sowie die Vertragsschnittstelle. Deshalb können Sie diese direkt zum Aufrufen von Vorgängen verwenden, die mit einem Dienst interagieren, der diesen Vertrag unterstützt.  
  
 Der Unterschied zwischen der Verwendung von Clientobjekten und Clientkanalobjekten liegt einfach in der Form der Steuerung und der Einfachheit der Verwendung für die Entwickler. Viele Entwickler, die gerne mit Klassen und Objekten arbeiten, bevorzugen die Verwendung des WCF-Client Objekts anstelle des WCF-Client Kanals.  
  
 Ein Beispiel finden Sie unter Gewusst [wie: Verwenden der ChannelFactory](how-to-use-the-channelfactory.md).

---
title: Clientarchitektur
ms.date: 03/30/2017
ms.assetid: 02624403-0d77-41cb-9a86-ab55e98c7966
ms.openlocfilehash: 4ced24f370e2ab54528c6adb2b3617d3d849e745
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="client-architecture"></a>Clientarchitektur
Anwendungen verwenden Windows Communication Foundation (WCF)-Clientobjekte, um Dienstvorgänge aufzurufen. In diesem Thema werden WCF-Clientobjekten, WCF-Clientkanäle und ihre Beziehungen zu der zugrunde liegenden Kanalarchitektur erläutert. Eine grundlegende Übersicht über WCF-Clientobjekten finden Sie unter [Überblick über WCF-Client](../../../../docs/framework/wcf/wcf-client-overview.md). Weitere Informationen über die Kanalschicht finden Sie unter [Erweitern der Kanalschicht](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md).  
  
## <a name="overview"></a>Übersicht  
 Die dienstmodelllaufzeit erstellt WCF-Clients, die aus folgendem bestehen:  
  
-   Eine automatisch generierte Clientimplementierung eines Dienstvertrags, der Aufrufe Ihres Anwendungscodes in ausgehende Nachrichten umwandelt und Antwortnachrichten in Ausgabeparameter und Rückgabewerte, die von Ihrer Anwendung abgerufen werden können.  
  
-   Eine Implementierung der Steuerungsschnittstelle (<xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>), die verschiedene Schnittstellen gruppiert und Zugriff auf die Steuerungsfunktionalität bietet, vor allem die Möglichkeit, die Clientsitzung zu schließen und den Kanal zu verwerfen.  
  
-   Ein Clientkanal, der auf Grundlage der von der verwendeten Bindung angegebenen Konfigurationseinstellungen erstellt wird.  
  
 Anwendungen können solche Clients nach Bedarf, entweder durch Erstellen einer <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> oder durch Erstellen einer Instanz von einer <xref:System.ServiceModel.ClientBase%601> abgeleitete Klasse, wie sie von generiert die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Diese vorgefertigten Clientklassen kapseln und delegieren an eine Clientkanalimplementierung, die durch eine <xref:System.ServiceModel.ChannelFactory> dynamisch erstellt wird. Deshalb stehen der Clientkanal und die Kanalfactory, die diese hervorbringen, bei dieser Erläuterung im Zentrum des Interesses.  
  
## <a name="client-objects-and-client-channels"></a>Clientobjekte und Clientkanäle  
 Die Basisschnittstelle des WCF-Clients ist die <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> -Schnittstelle, die clientkernfunktionen als auch die grundlegenden kommunikationsobjektfunktionen von macht <xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>, die kontextfunktionen von <xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType>, sowie das erweiterbare Verhalten von <xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>.  
  
 Die <xref:System.ServiceModel.IClientChannel>-Schnittstelle definiert jedoch keinen Dienstvertrag. Diese werden von der dienstvertragschnittstelle deklariert (i. d. r. aus Dienstmetadaten mithilfe eines Tools wie generiert die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)). WCF-Clienttypen erweitern sowohl <xref:System.ServiceModel.IClientChannel> und zieldienstvertragsschnittstelle So aktivieren Sie die Vorgänge direkt und auch aufrufen, Zugriff auf clientseitige Laufzeitfunktionen haben. Erstellen einen WCF-Client bietet WCF<xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> Objekte mit den Informationen zum Erstellen einer Laufzeit erforderlich sind, die eine Verbindung herstellen und mit dem konfigurierten Dienstendpunkt interagieren können.  
  
 Wie bereits erwähnt, müssen die beiden Typen des WCF-Client konfiguriert werden, bevor Sie sie verwenden können. Die einfachsten WCF-Clienttypen sind Objekte, die Ableitung <xref:System.ServiceModel.ClientBase%601> (oder <xref:System.ServiceModel.DuplexClientBase%601> , wenn die Dienstvertrag einen Duplexvertrag handelt). Sie können diese Typen mithilfe eines Konstruktors erstellen, der programmgesteuert konfiguriert wird, oder durch Verwenden einer Konfigurationsdatei, die direkt aufgerufen wird, um Dienstvorgänge aufzurufen. Für eine grundlegende Übersicht über <xref:System.ServiceModel.ClientBase%601> anzuzeigen, [Überblick über WCF-Client](../../../../docs/framework/wcf/wcf-client-overview.md).  
  
 Der zweite Typ wird zur Laufzeit von einem Aufruf der <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>-Methode generiert. Anwendungen strikte Kontrolle der Kommunikationsdetails unterliegen, in der Regel verwenden diesen Clienttyp, bezeichnet einen *clientkanalobjekt*, weil dadurch eine direktere Interaktion möglich ist als dem zugrunde liegenden Laufzeit für Client und dem Kanal System.  
  
## <a name="channel-factories"></a>Kanalfactorys  
 Die Klasse, die für das Erstellen der zugrunde liegenden Laufzeit verantwortlich ist, die Clientaufrufe unterstützt, ist die <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>-Klasse. WCF-Clientobjekten und WCF-Client-channel-Objekte verwenden eine <xref:System.ServiceModel.ChannelFactory%601> Objekt zum Erstellen von Instanzen; die <xref:System.ServiceModel.ClientBase%601> abgeleiteten Clientobjekt kapselt die Verarbeitung der Kanalfactory, aber für eine Reihe von Szenarien ist es angebracht, verwenden Sie die Kanalfactory direkt. Das am häufigsten vorkommende Szenario ist, wenn Sie wiederholt aus einer bereits vorhandenen Factory neue Clientkanäle erstellen möchten. Wenn Sie ein Clientobjekt verwenden, können Sie die zugrunde liegende Kanalfactory aus einem WCF-Clientobjekts abrufen, durch Aufrufen der <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A?displayProperty=nameWithType> Eigenschaft.  
  
 Bei Kanalfactorys muss beachtet werden, dass sie neue Instanzen von Clientkanälen für die ihnen zur Verfügung stehende Konfiguration erstellen, bevor sie <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> aufrufen. Sobald Sie rufen <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> (oder <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.ClientBase%601.CreateChannel%2A?displayProperty=nameWithType>, oder einem Vorgang für eine WCF-Clientobjekts), nicht der Kanalfactory ebenfalls geändert, und erwarten können, dass die Kanäle für verschiedene Dienstinstanzen, auch wenn Sie lediglich die zielendpunktadresse ändern. Wenn Sie ein Clientobjekt oder einen Clientkanal mit einer anderen Konfiguration erstellen möchten, müssen Sie zunächst eine neue Kanalfactory erstellen.  
  
 Weitere Informationen zu verschiedenen Problemen mit WCF-Clientobjekten und WCF-Clientkanäle finden Sie unter [beim Zugriff auf Dienste, die mithilfe eines WCF-Clients](../../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md).  
  
 Die folgenden beiden Abschnitten werden die Erstellung und Verwendung von WCF-clientkanalobjekten beschrieben.  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>Erstellen eines neuen WCF-Clientkanalobjekts  
 Um die Verwendung eines Clientkanals zu illustrieren, wird davon ausgegangen, dass der folgende Dienstvertrag generiert wurde.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Um eine Verbindung mit einem `ISampleService`-Dienst herzustellen, verwenden Sie die generierte Vertragsschnittstelle direkt mit einer Kanalfactory (<xref:System.ServiceModel.ChannelFactory%601>). Sobald Sie eine Kanalfactory für einen bestimmten Vertrag erstellt und konfiguriert haben, können Sie die <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>-Methode aufrufen, um die Clientkanalobjekte zurückzugeben, die Sie für die Kommunikation mit einem `ISampleService`-Dienst verwenden können.  
  
 Beim Verwenden der <xref:System.ServiceModel.ChannelFactory%601>-Klasse mit einer Dienstvertragschnittstelle muss diese in eine <xref:System.ServiceModel.IClientChannel>-Schnittstelle umgewandelt werden, um den Kanal explizit zu öffnen, zu schließen oder abzubrechen. Zum Erleichtern der Arbeit generiert das Tool Svcutil.exe auch eine Hilfsschnittstelle, die die Dienstvertragschnittstelle und <xref:System.ServiceModel.IClientChannel> implementiert, wodurch die Interaktion mit der Clientkanalinfrastruktur ohne Umwandlung ermöglicht wird. Im folgenden Code wird die Definition eines Hilfsclientkanals, der den vorangehenden Dienstvertrag implementiert, veranschaulicht.  
  
 [!code-csharp[C_GeneratedCodeFiles#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#13)]  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>Erstellen eines neuen WCF-Clientkanalobjekts  
 Wenn Sie einen Clientkanal zum Verbinden mit einem `ISampleService`-Dienst verwenden möchten, verwenden Sie die generierte Vertragsschnittstelle (oder die Hilfsversion) direkt mit einer Kanalfactory, wobei Sie den Typ der Vertragsschnittstelle als Typparameter übergeben. Sobald Sie eine Kanalfactory für einen bestimmten Vertrag erstellt und konfiguriert haben, können Sie die <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType>-Methode aufrufen, um die Clientkanalobjekte zurückzugeben, die Sie für die Kommunikation mit einem `ISampleService`-Dienst verwenden können.  
  
 Die Clientkanalobjekte implementieren bei ihrer Erstellung <xref:System.ServiceModel.IClientChannel> sowie die Vertragsschnittstelle. Deshalb können Sie diese direkt zum Aufrufen von Vorgängen verwenden, die mit einem Dienst interagieren, der diesen Vertrag unterstützt.  
  
 Der Unterschied zwischen der Verwendung von Clientobjekten und Clientkanalobjekten liegt einfach in der Form der Steuerung und der Einfachheit der Verwendung für die Entwickler. Viele Entwickler, die Arbeiten mit Klassen und Objekten vertraut sind bevorzugt des WCF-Clientobjekts anstelle der WCF-Client-Kanal verwendet.  
  
 Ein Beispiel finden Sie unter [Vorgehensweise: Verwenden der ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md).

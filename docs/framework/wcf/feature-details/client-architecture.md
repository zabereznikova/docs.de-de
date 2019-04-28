---
title: Clientarchitektur
ms.date: 03/30/2017
ms.assetid: 02624403-0d77-41cb-9a86-ab55e98c7966
ms.openlocfilehash: 4ced24f370e2ab54528c6adb2b3617d3d849e745
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781523"
---
# <a name="client-architecture"></a>Clientarchitektur
Anwendungen verwenden Windows Communication Foundation (WCF)-Clientobjekte, um Dienstvorgänge aufzurufen. In diesem Thema wird die WCF-Clientobjekten, WCF-Clientkanäle und ihre Beziehungen zu der zugrunde liegenden Kanalarchitektur erläutert. Eine grundlegende Übersicht über WCF-Clientobjekten, finden Sie unter [WCF Client Overview](../../../../docs/framework/wcf/wcf-client-overview.md). Weitere Informationen über die Kanalschicht finden Sie unter [Erweitern der Kanalschicht](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md).  
  
## <a name="overview"></a>Übersicht  
 Die dienstmodelllaufzeit erstellt WCF-Clients, die der folgenden bestehen:  
  
- Eine automatisch generierte Clientimplementierung eines Dienstvertrags, der Aufrufe Ihres Anwendungscodes in ausgehende Nachrichten umwandelt und Antwortnachrichten in Ausgabeparameter und Rückgabewerte, die von Ihrer Anwendung abgerufen werden können.  
  
- Eine Implementierung der Steuerungsschnittstelle (<xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>), die verschiedene Schnittstellen gruppiert und Zugriff auf die Steuerungsfunktionalität bietet, vor allem die Möglichkeit, die Clientsitzung zu schließen und den Kanal zu verwerfen.  
  
- Ein Clientkanal, der auf Grundlage der von der verwendeten Bindung angegebenen Konfigurationseinstellungen erstellt wird.  
  
 Anwendungen können solche Clients bei Bedarf, entweder durch Erstellen einer <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> oder durch Erstellen einer Instanz von einer <xref:System.ServiceModel.ClientBase%601> abgeleitete Klasse, wie Sie generiert wurde die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Diese vorgefertigten Clientklassen kapseln und delegieren an eine Clientkanalimplementierung, die durch eine <xref:System.ServiceModel.ChannelFactory> dynamisch erstellt wird. Deshalb stehen der Clientkanal und die Kanalfactory, die diese hervorbringen, bei dieser Erläuterung im Zentrum des Interesses.  
  
## <a name="client-objects-and-client-channels"></a>Clientobjekte und Clientkanäle  
 Die Basisschnittstelle des WCF-Clients ist die <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> -Schnittstelle, die sowohl die clientkernfunktionen als auch die grundlegenden kommunikationsobjektfunktionen von macht <xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>, die kontextfunktionen von <xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType>, sowie das erweiterbare Verhalten von <xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>.  
  
 Die <xref:System.ServiceModel.IClientChannel>-Schnittstelle definiert jedoch keinen Dienstvertrag. Die von der dienstvertragschnittstelle deklariert werden (aus Metadaten des Diensts mit einem Tool wie in der Regel generiert die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)). WCF-Clienttypen erweitern sowohl <xref:System.ServiceModel.IClientChannel> und die zieldienstvertragsschnittstelle, damit Anwendungen Vorgänge direkt "und" auch aufrufen Zugriff auf clientseitige Laufzeitfunktionen haben. Erstellen einen WCF-Client bietet WCF<xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType> Objekte mit den Informationen zum Erstellen einer Laufzeit, die eine Verbindung herstellen und der konfigurierte Dienstendpunkt interagieren können.  
  
 Wie bereits erwähnt, müssen die beiden Typen von WCF-Client konfiguriert werden, bevor Sie sie verwenden können. Die einfachste WCF-Clienttypen sind Objekte, die abgeleitet <xref:System.ServiceModel.ClientBase%601> (oder <xref:System.ServiceModel.DuplexClientBase%601> , wenn die Dienstvertrag einen Duplexvertrag handelt). Sie können diese Typen mithilfe eines Konstruktors erstellen, der programmgesteuert konfiguriert wird, oder durch Verwenden einer Konfigurationsdatei, die direkt aufgerufen wird, um Dienstvorgänge aufzurufen. Für eine grundlegende Übersicht über <xref:System.ServiceModel.ClientBase%601> Objekten finden Sie [WCF Client Overview](../../../../docs/framework/wcf/wcf-client-overview.md).  
  
 Der zweite Typ wird zur Laufzeit von einem Aufruf der <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>-Methode generiert. Anwendungen, die in der Regel mit einer detaillierten Kontrolle der Kommunikationsdetails unterliegen hinsichtlich verwenden diesen Clienttyp, der Namen einer *clientkanalobjekt*, weil dadurch eine direktere Interaktion möglich als die zugrunde liegenden Client-Laufzeit und der Kanal System.  
  
## <a name="channel-factories"></a>Kanalfactorys  
 Die Klasse, die für das Erstellen der zugrunde liegenden Laufzeit verantwortlich ist, die Clientaufrufe unterstützt, ist die <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>-Klasse. Sowohl WCF-Clientobjekten und WCF-Client Kanals Objekte verwenden eine <xref:System.ServiceModel.ChannelFactory%601> Objekt, das Erstellen von Instanzen; der <xref:System.ServiceModel.ClientBase%601> abgeleiteten Clientobjekt kapselt die Verarbeitung der Kanalfactory, aber für eine Reihe von Szenarien ist es durchaus sinnvoll, verwenden Sie die Kanalfactory direkt. Das am häufigsten vorkommende Szenario ist, wenn Sie wiederholt aus einer bereits vorhandenen Factory neue Clientkanäle erstellen möchten. Wenn Sie ein Clientobjekt verwenden, können Sie die zugrunde liegende Kanalfactory aus einem WCF-Client-Objekt abrufen, durch den Aufruf der <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A?displayProperty=nameWithType> Eigenschaft.  
  
 Bei Kanalfactorys muss beachtet werden, dass sie neue Instanzen von Clientkanälen für die ihnen zur Verfügung stehende Konfiguration erstellen, bevor sie <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> aufrufen. Wenn Sie aufrufen <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> (oder <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.ClientBase%601.CreateChannel%2A?displayProperty=nameWithType>, oder einem Vorgang auf einem WCF-Objekt), nicht ändern Sie die Kanalfactory und erwarten, Kanäle für verschiedene Dienstinstanzen zu erhalten, selbst wenn Sie lediglich die zielendpunktadresse ändern. Wenn Sie ein Clientobjekt oder einen Clientkanal mit einer anderen Konfiguration erstellen möchten, müssen Sie zunächst eine neue Kanalfactory erstellen.  
  
 Weitere Informationen zu verschiedenen Problemen mit WCF-Clientobjekten und WCF-Clientkanäle, finden Sie unter [Zugriff auf Dienste, die mithilfe eines WCF-Clients](../../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md).  
  
 Die folgenden beiden Abschnitte beschreiben die Erstellung und Verwendung von WCF-Client Kanals-Objekte.  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>Erstellen eines neuen WCF-Clientkanalobjekts  
 Um die Verwendung eines Clientkanals zu illustrieren, wird davon ausgegangen, dass der folgende Dienstvertrag generiert wurde.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Um eine Verbindung mit einem `ISampleService`-Dienst herzustellen, verwenden Sie die generierte Vertragsschnittstelle direkt mit einer Kanalfactory (<xref:System.ServiceModel.ChannelFactory%601>). Sobald Sie eine Kanalfactory für einen bestimmten Vertrag erstellt und konfiguriert haben, können Sie die <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>-Methode aufrufen, um die Clientkanalobjekte zurückzugeben, die Sie für die Kommunikation mit einem `ISampleService`-Dienst verwenden können.  
  
 Beim Verwenden der <xref:System.ServiceModel.ChannelFactory%601> -Klasse mit einer Dienstvertragschnittstelle muss diese in eine <xref:System.ServiceModel.IClientChannel> -Schnittstelle umgewandelt werden, um den Kanal explizit zu öffnen, zu schließen oder abzubrechen. Zum Erleichtern der Arbeit generiert das Tool Svcutil.exe auch eine Hilfsschnittstelle, die die Dienstvertragschnittstelle und <xref:System.ServiceModel.IClientChannel> implementiert, wodurch die Interaktion mit der Clientkanalinfrastruktur ohne Umwandlung ermöglicht wird. Im folgenden Code wird die Definition eines Hilfsclientkanals, der den vorangehenden Dienstvertrag implementiert, veranschaulicht.  
  
 [!code-csharp[C_GeneratedCodeFiles#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#13)]  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>Erstellen eines neuen WCF-Clientkanalobjekts  
 Wenn Sie einen Clientkanal zum Verbinden mit einem `ISampleService`-Dienst verwenden möchten, verwenden Sie die generierte Vertragsschnittstelle (oder die Hilfsversion) direkt mit einer Kanalfactory, wobei Sie den Typ der Vertragsschnittstelle als Typparameter übergeben. Sobald Sie eine Kanalfactory für einen bestimmten Vertrag erstellt und konfiguriert haben, können Sie die <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType>-Methode aufrufen, um die Clientkanalobjekte zurückzugeben, die Sie für die Kommunikation mit einem `ISampleService`-Dienst verwenden können.  
  
 Die Clientkanalobjekte implementieren bei ihrer Erstellung <xref:System.ServiceModel.IClientChannel> sowie die Vertragsschnittstelle. Deshalb können Sie diese direkt zum Aufrufen von Vorgängen verwenden, die mit einem Dienst interagieren, der diesen Vertrag unterstützt.  
  
 Der Unterschied zwischen der Verwendung von Clientobjekten und Clientkanalobjekten liegt einfach in der Form der Steuerung und der Einfachheit der Verwendung für die Entwickler. Viele Entwickler, die Arbeiten mit Klassen und Objekten vertraut sind werden lieber das WCF-Client-Objekt anstelle der WCF-Client-Kanal.  
  
 Ein Beispiel finden Sie unter [Gewusst wie: Verwenden Sie die ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md).

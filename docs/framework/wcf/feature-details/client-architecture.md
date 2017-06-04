---
title: "Clientarchitektur | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 02624403-0d77-41cb-9a86-ab55e98c7966
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Clientarchitektur
Anwendungen verwenden [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Clientobjekte, um Dienstvorgänge aufzurufen.In diesem Thema werden [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientobjekte, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientkanäle und ihre Beziehungen mit der zugrunde liegenden Kanalarchitektur erläutert.Eine grundlegende Übersicht über [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientobjekte finden Sie unter [Übersicht über den WCF\-Client](../../../../docs/framework/wcf/wcf-client-overview.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] über die Kanalschicht finden Sie unter [Erweitern der Kanalschicht](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md).  
  
## Übersicht  
 Die Dienstmodelllaufzeit erstellt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clients, die aus Folgendem zusammengesetzt sind:  
  
-   Eine automatisch generierte Clientimplementierung eines Dienstvertrags, der Aufrufe Ihres Anwendungscodes in ausgehende Nachrichten umwandelt und Antwortnachrichten in Ausgabeparameter und Rückgabewerte, die von Ihrer Anwendung abgerufen werden können.  
  
-   Eine Implementierung der Steuerungsschnittstelle \(<xref:System.ServiceModel.IClientChannel?displayProperty=fullName>\), die verschiedene Schnittstellen gruppiert und Zugriff auf die Steuerungsfunktionalität bietet, vor allem die Möglichkeit, die Clientsitzung zu schließen und den Kanal zu verwerfen.  
  
-   Ein Clientkanal, der auf Grundlage der von der verwendeten Bindung angegebenen Konfigurationseinstellungen erstellt wird.  
  
 Anwendungen können solche Clients auf Bedarf erstellen oder über eine <xref:System.ServiceModel.ChannelFactory?displayProperty=fullName> oder durch Erstellen einer Instanz einer abgeleiteten <xref:System.ServiceModel.ClientBase%601>\-Klasse, die vom [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) generiert wird.Diese vorgefertigten Clientklassen kapseln und delegieren an eine Clientkanalimplementierung, die durch eine <xref:System.ServiceModel.ChannelFactory> dynamisch erstellt wird.Deshalb stehen der Clientkanal und die Kanalfactory, die diese hervorbringen, bei dieser Erläuterung im Zentrum des Interesses.  
  
## Clientobjekte und Clientkanäle  
 Die Basisschnittstelle von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clients ist die <xref:System.ServiceModel.IClientChannel?displayProperty=fullName>\-Schnittstelle, die sowohl die Clientkernfunktionen als auch die grundlegenden Kommunikationsobjektfunktionen von <xref:System.ServiceModel.ICommunicationObject?displayProperty=fullName>, die Kontextfunktionen von <xref:System.ServiceModel.IContextChannel?displayProperty=fullName> sowie das erweiterbare Verhalten von <xref:System.ServiceModel.IExtensibleObject%601?displayProperty=fullName> verfügbar macht.  
  
 Die <xref:System.ServiceModel.IClientChannel>\-Schnittstelle definiert jedoch keinen Dienstvertrag.Dienstverträge werden von der Dienstvertragschnittstelle \(in der Regel mit einem Tool wie [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) aus Dienstmetadaten generiert wird\) deklariert.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clienttypen erweitern sowohl <xref:System.ServiceModel.IClientChannel> als auch die Dienstvertrag\-Zielschnittstelle, damit Anwendungen Vorgänge direkt aufrufen können und Zugriff auf clientseitige Laufzeitfunktionen haben.Aus der Erstellung eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clients resultieren [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-<xref:System.ServiceModel.ChannelFactory?displayProperty=fullName>\-Objekte, die die Informationen enthalten, die zum Erstellen einer Laufzeit erforderlich sind, die mit dem konfigurierten Dienstendpunkt verbunden werden und mit ihm interagieren kann.  
  
 Wie bereits zuvor erwähnt, müssen die beiden [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clienttypen konfiguriert werden, bevor Sie sie verwenden können.Die einfachsten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clienttypen sind Objekte, die von <xref:System.ServiceModel.ClientBase%601> hergeleitet werden \(oder <xref:System.ServiceModel.DuplexClientBase%601>, falls es sich bei dem Dienstvertrag um einen Duplexvertrag handelt\).Sie können diese Typen mithilfe eines Konstruktors erstellen, der programmgesteuert konfiguriert wird, oder durch Verwenden einer Konfigurationsdatei, die direkt aufgerufen wird, um Dienstvorgänge aufzurufen.Eine grundlegende Übersicht über <xref:System.ServiceModel.ClientBase%601>\-Objekte finden Sie unter [Übersicht über den WCF\-Client](../../../../docs/framework/wcf/wcf-client-overview.md).  
  
 Der zweite Typ wird zur Laufzeit von einem Aufruf der <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>\-Methode generiert.Anwendungen, die einer strengen Kontrolle der Kommunikationsdetails unterliegen, verwenden diesen Clienttyp, der als *Clientkanalobjekt* bezeichnet wird, da damit eine direktere Interaktion möglich ist als mit dem zugrunde liegenden Clientlaufzeit\- und Kanalsystem.  
  
## Kanalfactorys  
 Die Klasse, die für das Erstellen der zugrunde liegenden Laufzeit verantwortlich ist, die Clientaufrufe unterstützt, ist die <xref:System.ServiceModel.ChannelFactory%601?displayProperty=fullName>\-Klasse.Sowohl [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientobjekte als auch [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientkanalobjekte verwenden ein <xref:System.ServiceModel.ChannelFactory%601>\-Objekt zum Erstellen von Instanzen. Das abgeleitete <xref:System.ServiceModel.ClientBase%601>\-Clientobjekt kapselt die Verarbeitung der Kanalfactory. Für viele Szenarien ist es jedoch angebracht, die Kanalfactory direkt zu verwenden.Das am häufigsten vorkommende Szenario ist, wenn Sie wiederholt aus einer bereits vorhandenen Factory neue Clientkanäle erstellen möchten.Wenn Sie ein Clientobjekt verwenden, können Sie die zugrunde liegende Kanalfactory aus einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientobjekt erhalten, indem Sie die <xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A?displayProperty=fullName>\-Eigenschaft aufrufen.  
  
 Bei Kanalfactorys muss beachtet werden, dass sie neue Instanzen von Clientkanälen für die ihnen zur Verfügung stehende Konfiguration erstellen, bevor sie <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=fullName> aufrufen.Sobald Sie <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> \(oder <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=fullName>, <xref:System.ServiceModel.ClientBase%601.CreateChannel%2A?displayProperty=fullName> oder einen anderen Vorgang eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientobjekts\) aufrufen, können Sie die Kanalfactory nicht ändern oder erwarten, Kanäle für verschiedene Dienstinstanzen zu erhalten, auch dann nicht, wenn Sie lediglich die Zielendpunktadresse ändern.Wenn Sie ein Clientobjekt oder einen Clientkanal mit einer anderen Konfiguration erstellen möchten, müssen Sie zunächst eine neue Kanalfactory erstellen.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] über verschiedene Probleme mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientobjekten und [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientkanälen finden Sie unter [Zugreifen auf Dienste mithilfe eines WCF\-Clients](../../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md).  
  
 In den folgenden beiden Abschnitten werden die Erstellung und die Verwendung von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientkanalobjekten beschrieben.  
  
#### Erstellen eines neuen WCF\-Clientkanalobjekts  
 Um die Verwendung eines Clientkanals zu illustrieren, wird davon ausgegangen, dass der folgende Dienstvertrag generiert wurde.  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 Um eine Verbindung mit einem `ISampleService`\-Dienst herzustellen, verwenden Sie die generierte Vertragsschnittstelle direkt mit einer Kanalfactory \(<xref:System.ServiceModel.ChannelFactory%601>\).Sobald Sie eine Kanalfactory für einen bestimmten Vertrag erstellt und konfiguriert haben, können Sie die <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>\-Methode aufrufen, um die Clientkanalobjekte zurückzugeben, die Sie für die Kommunikation mit einem `ISampleService`\-Dienst verwenden können.  
  
 Beim Verwenden der <xref:System.ServiceModel.ChannelFactory%601>\-Klasse mit einer Dienstvertragschnittstelle muss diese in eine <xref:System.ServiceModel.IClientChannel>\-Schnittstelle umgewandelt werden, um den Kanal explizit zu öffnen, zu schließen oder abzubrechen.Zum Erleichtern der Arbeit generiert das Tool Svcutil.exe auch eine Hilfsschnittstelle, die die Dienstvertragschnittstelle und <xref:System.ServiceModel.IClientChannel> implementiert, wodurch die Interaktion mit der Clientkanalinfrastruktur ohne Umwandlung ermöglicht wird.Im folgenden Code wird die Definition eines Hilfsclientkanals veranschaulicht, der den vorangehenden Dienstvertrag implementiert.  
  
 [!code-csharp[C_GeneratedCodeFiles#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#13)]  
  
#### Erstellen eines neuen WCF\-Clientkanalobjekts  
 Wenn Sie einen Clientkanal zum Verbinden mit einem `ISampleService`\-Dienst verwenden möchten, verwenden Sie die generierte Vertragsschnittstelle \(oder die Hilfsversion\) direkt mit einer Kanalfactory, wobei Sie den Typ der Vertragsschnittstelle als Typparameter übergeben.Sobald Sie eine Kanalfactory für einen bestimmten Vertrag erstellt und konfiguriert haben, können Sie die <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=fullName>\-Methode aufrufen, um die Clientkanalobjekte zurückzugeben, die Sie für die Kommunikation mit einem `ISampleService`\-Dienst verwenden können.  
  
 Die Clientkanalobjekte implementieren bei ihrer Erstellung <xref:System.ServiceModel.IClientChannel> sowie die Vertragsschnittstelle.Deshalb können Sie diese direkt zum Aufrufen von Vorgängen verwenden, die mit einem Dienst interagieren, der diesen Vertrag unterstützt.  
  
 Der Unterschied zwischen der Verwendung von Clientobjekten und Clientkanalobjekten liegt einfach in der Form der Steuerung und der Einfachheit der Verwendung für die Entwickler.Viele Entwickler, die gerne mit Klassen und Objekten arbeiten, bevorzugen wahrscheinlich die Verwendung des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientobjekts gegenüber dem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientkanal.  
  
 Ein Beispiel finden Sie unter [Vorgehensweise: Verwenden der ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md).
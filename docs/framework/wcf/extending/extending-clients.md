---
title: Erweitern von Clients
ms.date: 03/30/2017
helpviewer_keywords:
- proxy extensions [WCF]
ms.assetid: 1328c61c-06e5-455f-9ebd-ceefb59d3867
ms.openlocfilehash: 99b4dd5e4acfce8bea4d3c2cae3a53152585675d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074754"
---
# <a name="extending-clients"></a>Erweitern von Clients
Die Dienstmodellebene ist dafür verantwortlich, Methodenaufrufe per Anwendungscode in ausgehende Nachrichten zu übersetzen, sie in den zugrunde liegenden Kanälen abzulegen, die Ergebnisse zurück in Rückgabewerte und out-Parameter in Anwendungscode zu übersetzen sowie die Ergebnisse an den Aufrufer zurückzugeben. Dienstmodellerweiterungen ändern bzw. implementieren Ausführungs- oder Kommunikationsverhalten und Funktionen wie Verteileroptionen, benutzerdefiniertes Verhalten, Nachrichten- oder Parameterinterceptoren und andere Erweiterbarkeitsfunktionen.  
  
 In diesem Thema wird beschrieben, wie Sie mit der <xref:System.ServiceModel.Dispatcher.ClientRuntime> und <xref:System.ServiceModel.Dispatcher.ClientOperation> Klassen in einer Windows Communication Foundation (WCF)-Clientanwendung, ändern das Standardverhalten für die Ausführung eines WCF-Clients zum Abfangen, oder Ändern von Nachrichten, Parameter oder Rückgabewerte vor oder nach dem Senden oder Abrufen von Verbindungszeichenfolgen aus der Kanalschicht. Weitere Informationen zur Ausdehnung der Dienstlaufzeit finden Sie unter [Erweitern von Verteilern](../../../../docs/framework/wcf/extending/extending-dispatchers.md). Weitere Informationen zu den Verhaltensweisen, die ändern, und fügen Sie anpassungsobjekte in die Clientlaufzeit, finden Sie unter [konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="clients"></a>Clients  
 Auf einem Client konvertiert ein WCF-Client-Objekt oder -Clientkanal Methodenaufrufe in ausgehende Nachrichten und eingehende Nachrichten in Vorgangsergebnisse, die an die aufrufende Anwendung zurückgegeben werden. (Weitere Informationen über Clienttypen finden Sie unter [WCF-Clientarchitektur](../../../../docs/framework/wcf/feature-details/client-architecture.md).)  
  
 WCF-Clienttypen weisen Laufzeittypen auf, die diese Funktionen auf Endpunkt und Vorgang zu verarbeiten. Wenn ein Vorgang von einer Anwendung aufgerufen wird, übersetzt <xref:System.ServiceModel.Dispatcher.ClientOperation> die ausgehenden Objekte in eine Nachricht, verarbeitet Interceptoren, bestätigt, dass der ausgehende Aufruf dem Zielvertrag entspricht, und übergibt die ausgehende Nachricht an <xref:System.ServiceModel.Dispatcher.ClientRuntime>, die für das Erstellen und Verwalten von ausgehenden Kanälen (und eingehenden Kanälen im Falle von Duplexdiensten), das Verarbeiten von zusätzlichen ausgehenden Nachrichten (wie Headeränderungen), die Verarbeitung von Nachrichteninterceptoren in beide Richtungen sowie das Leiten von eingehenden Duplexaufrufen an das entsprechende clientseitige <xref:System.ServiceModel.Dispatcher.DispatchRuntime>-Objekt verantwortlich ist. Sowohl <xref:System.ServiceModel.Dispatcher.ClientOperation> als auch <xref:System.ServiceModel.Dispatcher.ClientRuntime> stellen ähnliche Dienste bereit, wenn dem Client Nachrichten (einschließlich Fehler) zurückgegeben werden.  
  
 Diese beiden Laufzeitklassen sind die haupterweiterung dar, die Verarbeitung von WCF-Clientobjekten und Kanälen anpassen. Die <xref:System.ServiceModel.Dispatcher.ClientRuntime>-Klasse ermöglicht Benutzern, die Clientausführung über alle Nachrichten im Vertrag hinweg abzufangen und zu erweitern. Die <xref:System.ServiceModel.Dispatcher.ClientOperation>-Klasse ermöglicht Benutzern, die Clientausführung für alle Nachrichten eines bestimmten Vorgangs abzufangen und zu erweitern.  
  
 Das Ändern der Eigenschaften oder Einfügen von Anpassungen wird auf der Grundlage von Vertrags-, Endpunkt- und Vorgangsverhalten durchgeführt. Weitere Informationen zur Verwendung dieser Verhaltenstypen zum Durchführen von clientlaufzeitanpassungen finden Sie unter [konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="scenarios"></a>Szenarien  
 Es gibt viele Gründe, das Clientsystem zu erweitern:  
  
-   Benutzerdefinierte Nachrichtenvalidierung. Ein Benutzer möchte durchsetzen, dass eine Nachricht für ein bestimmtes Schema gültig ist. Dies kann durch Implementieren der <xref:System.ServiceModel.Dispatcher.IClientMessageInspector>-Schnittstelle und Zuweisen der Implementierung an die <xref:System.ServiceModel.Dispatcher.DispatchRuntime.MessageInspectors%2A>-Eigenschaft erfolgen. Beispiele hierzu finden Sie unter [Vorgehensweise: Überprüfen oder Ändern von Nachrichten auf dem Client](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-messages-on-the-client.md) und [Vorgehensweise: Überprüfen oder Ändern von Nachrichten auf dem Client](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-messages-on-the-client.md).  
  
-   Benutzerdefinierte Nachrichtenprotokollierung. Ein Benutzer möchte eventuell einige Anwendungsnachrichten prüfen und protokollieren, die durch einen Endpunkt fließen. Dies kann ebenfalls mit den Nachrichteninterceptorschnittstellen erreicht werden.  
  
-   Benutzerdefinierte Nachrichtentransformationen. Anstatt den Anwendungscode zu ändern, möchte der Benutzer vielleicht bestimmte Transformationen (wie Versionsverwaltung) auf die Nachricht in der Laufzeit anwenden. Auch dies kann mit den Nachrichteninterceptorschnittstellen erreicht werden.  
  
-   Benutzerdefiniertes Datenmodell. Ein Benutzer möchte eventuell ein Daten- oder Serialisierungsmodell Modell als diejenigen, die standardmäßig in WCF unterstützt (d. h., <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>, <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>, und <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType> Objekte). Dies kann über die Implementierung der Nachrichtenformatierungsschnittstellen erreicht werden. Weitere Informationen finden Sie in der <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=nameWithType>-Eigenschaft und in der <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A?displayProperty=nameWithType>-Eigenschaft.  
  
-   Benutzerdefinierte Parametervalidierung. Ein Benutzer möchte durchsetzen, dass typisierte Parameter gültig sind (im Gegensatz zu XML). Dies kann mit den Parameterinspektorschnittstellen erreicht werden. Ein Beispiel finden Sie unter [Gewusst wie: Überprüfen oder Ändern von Parametern](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-parameters.md) oder [Clientvalidierung](../../../../docs/framework/wcf/samples/client-validation.md).  
  
### <a name="using-the-clientruntime-class"></a>Verwenden der ClientRuntime-Klasse  
 Die <xref:System.ServiceModel.Dispatcher.ClientRuntime>-Klasse ist ein Erweiterungspunkt, an den Sie Erweiterungsobjekte anhängen können, die Nachrichten abfangen und das Clientverhalten ausdehnen. Abfangobjekte können alle Nachrichten in einem bestimmten Vertrag verarbeiten, nur Nachrichten für bestimmte Vorgänge verarbeiten, eine benutzerdefinierte Kanalinitialisierung durchführen und sonstiges benutzerdefiniertes Verhalten von Clientanwendungen implementieren.  
  
-   Die <xref:System.ServiceModel.Dispatcher.ClientRuntime.CallbackDispatchRuntime%2A>-Eigenschaft gibt das DispatchRuntime-Objekt für durch Dienste initiierte Rückrufvorgangsclients zurück.  
  
-   Die <xref:System.ServiceModel.Dispatcher.ClientRuntime.OperationSelector%2A>-Eigenschaft akzeptiert ein benutzerdefiniertes Vorgangsauswahlobjekt.  
  
-   Die <xref:System.ServiceModel.Dispatcher.ClientRuntime.ChannelInitializers%2A>-Eigenschaft ermöglicht das Hinzufügen eines Kanalinitialisierers, der den Clientkanal prüfen oder abändern kann.  
  
-   Die <xref:System.ServiceModel.Dispatcher.ClientRuntime.Operations%2A>-Eigenschaft ruft eine Auflistung von <xref:System.ServiceModel.Dispatcher.ClientOperation>-Objekten ab, denen Sie benutzerdefinierte Nachrichteninterceptoren hinzufügen können, die spezielle Funktionen für die Nachrichten dieses Vorgangs bereitstellen.  
  
-   Die <xref:System.ServiceModel.Dispatcher.ClientRuntime.ManualAddressing%2A>-Eigenschaft ermöglicht einer Anwendung, bestimmte automatische Adressierungsheader zu deaktivieren, um die Adressierung direkt zu steuern.  
  
-   Die <xref:System.ServiceModel.Dispatcher.ClientRuntime.Via%2A>-Eigenschaft legt den Wert des Ziels der Nachricht auf der Transportebene fest, um Vermittler und andere Szenarien zu unterstützen.  
  
-   Die <xref:System.ServiceModel.Dispatcher.ClientRuntime.MessageInspectors%2A> Eigenschaft ruft eine Auflistung von <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> Objekte, die Sie benutzerdefinierte nachrichteninterceptoren für alle Nachrichten über einen WCF-Client hinzufügen können.  
  
 Außerdem gibt es eine Reihe weiterer Eigenschaften, die die Clientvertragsinformationen abrufen:  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.ContractName%2A>  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.ContractNamespace%2A>  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.ContractClientType%2A>  
  
 Wenn der WCF-Client einen WCF-duplexclient handelt, rufen die folgenden Eigenschaften auch des Rückrufs WCF-Client-Informationen:  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.CallbackClientType%2A>  
  
-   <xref:System.ServiceModel.Dispatcher.ClientRuntime.CallbackDispatchRuntime%2A>  
  
 Um WCF-clientausführung über eine gesamte WCF-Client zu erweitern, überprüfen Sie die Eigenschaften, die auf die <xref:System.ServiceModel.Dispatcher.ClientRuntime> Klasse, um festzustellen, ob durch Ändern einer Eigenschaft oder das Implementieren einer Schnittstelle und Hinzufügen zu einer Eigenschaft die Funktionalität Sie gewährleistet. Sobald Sie eine bestimmte Erweiterung ausgewählt haben, müssen Sie Ihre Erweiterung in die geeignete <xref:System.ServiceModel.Dispatcher.ClientRuntime>-Eigenschaft einfügen, indem Sie ein Clientverhalten implementieren, das Zugriff auf die <xref:System.ServiceModel.Dispatcher.ClientRuntime>-Klasse bietet, sobald diese aufgerufen wird.  
  
 Sie können benutzerdefinierte Erweiterungsobjekte in eine Auflistung einfügen. Verwenden Sie dazu ein Vorgangsverhalten (ein Objekt, das <xref:System.ServiceModel.Description.IOperationBehavior> implementiert), ein Vertragsverhalten (ein Objekt, das <xref:System.ServiceModel.Description.IContractBehavior> implementiert) oder ein Endpunktverhalten (ein Objekt, das <xref:System.ServiceModel.Description.IEndpointBehavior> implementiert). Das installierende Verhaltensobjekt wird der entsprechenden Auflistung der Verhalten entweder programmatisch, deklarativ (durch Implementierung eines benutzerdefinierten Attributs) oder durch Implementierung eines benutzerdefinierten <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>-Objekts hinzugefügt, um das Verhalten, das eingefügt werden soll, anhand einer Anwendungskonfigurationsdatei zu aktivieren. Weitere Informationen finden Sie unter [konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
 Beispiele, in denen abfangen über einem WCF-Client veranschaulicht, finden Sie unter [Vorgehensweise: Überprüfen oder Ändern von Nachrichten auf dem Client](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-messages-on-the-client.md).  
  
### <a name="using-the-clientoperation-class"></a>Verwenden der ClientOperation-Klasse  
 Die <xref:System.ServiceModel.Dispatcher.ClientOperation>-Klasse ist der Ort für Änderungen an der Clientlaufzeit und die Einfügemarke für benutzerdefinierte Erweiterungen, die nur auf einen Dienstvorgang abzielen. (Um das Clientlaufzeitverhalten für alle Nachrichten in einem Vertrag zu ändern, verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientRuntime>-Klasse.)  
  
 Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientRuntime.Operations%2A>-Eigenschaft, um das <xref:System.ServiceModel.Dispatcher.ClientOperation>-Objekt zu suchen, das einen bestimmten Dienstvorgang darstellt. Die folgenden Eigenschaften ermöglichen Ihnen, benutzerdefinierte Objekte in der WCF-Clientsystem einzufügen:  
  
-   Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A>-Eigenschaft, um eine benutzerdefinierte <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>-Implementierung für einen Vorgang einzufügen oder das aktuelle Formatierungsprogramm zu ändern.  
  
-   Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A>-Eigenschaft, um eine benutzerdefinierte <xref:System.ServiceModel.Dispatcher.IParameterInspector>-Implementierung einzufügen oder die aktuelle Implementierung zu ändern.  
  
 Mit den folgenden Eigenschaften können Sie das System in Interaktion mit dem Formatierungsprogramm und benutzerdefinierten Parameterinspektoren ändern:  
  
-   Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.SerializeRequest%2A>-Eigenschaft, um die Serialisierung einer ausgehenden Nachricht zu steuern.  
  
-   Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.DeserializeReply%2A>-Eigenschaft, um die Deserialisierung einer eingehenden Nachricht zu steuern.  
  
-   Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.Action%2A>-Eigenschaft, um die WS-Adressierungsaktion der Anforderungsnachricht zu steuern.  
  
-   Verwenden der <xref:System.ServiceModel.Dispatcher.ClientOperation.BeginMethod%2A> und <xref:System.ServiceModel.Dispatcher.ClientOperation.EndMethod%2A> angeben, welche Methoden der WCF-Client mit einem asynchronen Vorgang zugeordnet sind.  
  
-   Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.FaultContractInfos%2A>-Eigenschaft, um eine Auflistung der angegebenen Typen abzurufen, die als Detailtyp in SOAP-Fehlern erscheinen können.  
  
-   Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.IsInitiating%2A>-Eigenschaft und die <xref:System.ServiceModel.Dispatcher.ClientOperation.IsTerminating%2A>-Eigenschaft, um zu steuern, ob eine Sitzung initiiert bzw. abgebrochen wird, wenn der Vorgang aufgerufen wird.  
  
-   Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.IsOneWay%2A>-Eigenschaft, um zu steuern, ob es sich bei dem Vorgang um einen unidirektionalen Vorgang handelt.  
  
-   Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.Parent%2A>-Eigenschaft, um das darin enthaltene <xref:System.ServiceModel.Dispatcher.ClientRuntime>-Objekt zu ermitteln.  
  
-   Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.Name%2A>-Eigenschaft, um den Namen des Vorgangs abzurufen.  
  
-   Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.SyncMethod%2A>-Eigenschaft, um zu steuern, welche Methode dem Vorgang zugeordnet wird.  
  
 Um WCF-clientausführung über nur einen Dienstvorgang zu erweitern, überprüfen Sie die Eigenschaften, die auf die <xref:System.ServiceModel.Dispatcher.ClientOperation> Klasse, um festzustellen, ob durch Ändern einer Eigenschaft oder das Implementieren einer Schnittstelle und Hinzufügen zu einer Eigenschaft die Funktionalität Sie gewährleistet. Sobald Sie eine bestimmte Erweiterung ausgewählt haben, müssen Sie Ihre Erweiterung in die geeignete <xref:System.ServiceModel.Dispatcher.ClientOperation>-Eigenschaft einfügen, indem Sie ein Clientverhalten implementieren, das Zugriff auf die <xref:System.ServiceModel.Dispatcher.ClientOperation>-Klasse bietet, sobald diese aufgerufen wird. In diesem Verhalten können Sie dann die <xref:System.ServiceModel.Dispatcher.ClientRuntime>-Eigenschaft ändern, um sie Ihren Anforderungen anzupassen.  
  
 In der Regel reicht die Implementierung eines Vorgangsverhaltens (ein Objekt, das die <xref:System.ServiceModel.Description.IOperationBehavior>-Schnittstelle implementiert) aus, Sie können jedoch auch Endpunktverhalten und Vertragsverhalten verwenden, um dasselbe zu erreichen, indem Sie <xref:System.ServiceModel.Description.OperationDescription> für einen bestimmten Vorgang suchen und dort das Verhalten anfügen. Weitere Informationen finden Sie unter [konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
 Um das benutzerdefinierte Verhalten der Konfiguration zu verwenden, installieren Sie das Verhalten mit einem benutzerdefinierten Verhaltenskonfigurationsabschnitts-Handler. Sie können auch das Verhalten installieren, indem Sie ein benutzerdefiniertes Attribut erstellen.  
  
 Beispiele, in denen abfangen über einem WCF-Client veranschaulicht, finden Sie unter [Vorgehensweise: Überprüfen oder Ändern von Parametern](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-parameters.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Dispatcher.ClientRuntime>
- <xref:System.ServiceModel.Dispatcher.ClientOperation>
- [Vorgehensweise: Überprüfen oder Ändern von Nachrichten auf dem Client](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-messages-on-the-client.md)
- [Vorgehensweise: Überprüfen oder Ändern von Parametern](../../../../docs/framework/wcf/extending/how-to-inspect-or-modify-parameters.md)

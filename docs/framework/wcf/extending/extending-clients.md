---
title: Erweitern von Clients
ms.date: 03/30/2017
helpviewer_keywords:
- proxy extensions [WCF]
ms.assetid: 1328c61c-06e5-455f-9ebd-ceefb59d3867
ms.openlocfilehash: b3bbbdb895576b4a6d9167bcf321a99d10d378cc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249292"
---
# <a name="extending-clients"></a>Erweitern von Clients

Die Dienstmodellebene ist dafür verantwortlich, Methodenaufrufe per Anwendungscode in ausgehende Nachrichten zu übersetzen, sie in den zugrunde liegenden Kanälen abzulegen, die Ergebnisse zurück in Rückgabewerte und out-Parameter in Anwendungscode zu übersetzen sowie die Ergebnisse an den Aufrufer zurückzugeben. Dienstmodellerweiterungen ändern bzw. implementieren Ausführungs- oder Kommunikationsverhalten und Funktionen wie Verteileroptionen, benutzerdefiniertes Verhalten, Nachrichten- oder Parameterinterceptoren und andere Erweiterbarkeitsfunktionen.  
  
 In diesem Thema wird beschrieben, wie <xref:System.ServiceModel.Dispatcher.ClientRuntime> Sie die-Klasse und die- <xref:System.ServiceModel.Dispatcher.ClientOperation> Klasse in einer Windows Communication Foundation (WCF)-Client Anwendung verwenden, um das Standard Ausführungs Verhalten eines WCF-Clients zu ändern oder um Nachrichten, Parameter oder Rückgabewerte abzufangen oder zu ändern, bevor Sie von der Kanal Schicht gesendet oder abgerufen werden. Weitere Informationen zum Erweitern der Dienst Laufzeit finden Sie unter [Erweitern von Dispatchern](extending-dispatchers.md). Weitere Informationen zu den Verhaltensweisen, die Anpassungs Objekte in der Client Laufzeit ändern und einfügen, finden Sie unter [Konfigurieren und Erweitern der Laufzeit mit Verhalten](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="clients"></a>Clients  

 Auf einem Client konvertiert ein WCF-Client Objekt oder Client Kanal Methodenaufrufe in ausgehende Nachrichten und eingehende Nachrichten in Vorgangs Ergebnisse, die an die aufrufende Anwendung zurückgegeben werden. (Weitere Informationen zu Client Typen finden Sie unter [WCF-Client Architektur](../feature-details/client-architecture.md).)  
  
 WCF-Client Typen verfügen über Lauf Zeit Typen, die diese Funktionen auf Endpunkt-und Vorgangs Ebene verarbeiten. Wenn ein Vorgang von einer Anwendung aufgerufen wird, übersetzt <xref:System.ServiceModel.Dispatcher.ClientOperation> die ausgehenden Objekte in eine Nachricht, verarbeitet Interceptoren, bestätigt, dass der ausgehende Aufruf dem Zielvertrag entspricht, und übergibt die ausgehende Nachricht an <xref:System.ServiceModel.Dispatcher.ClientRuntime>, die für das Erstellen und Verwalten von ausgehenden Kanälen (und eingehenden Kanälen im Falle von Duplexdiensten), das Verarbeiten von zusätzlichen ausgehenden Nachrichten (wie Headeränderungen), die Verarbeitung von Nachrichteninterceptoren in beide Richtungen sowie das Leiten von eingehenden Duplexaufrufen an das entsprechende clientseitige <xref:System.ServiceModel.Dispatcher.DispatchRuntime>-Objekt verantwortlich ist. Sowohl <xref:System.ServiceModel.Dispatcher.ClientOperation> als auch <xref:System.ServiceModel.Dispatcher.ClientRuntime> stellen ähnliche Dienste bereit, wenn dem Client Nachrichten (einschließlich Fehler) zurückgegeben werden.  
  
 Diese beiden Lauf Zeit Klassen sind die Haupt Erweiterung zum Anpassen der Verarbeitung von WCF-Client Objekten und-Kanälen. Die <xref:System.ServiceModel.Dispatcher.ClientRuntime>-Klasse ermöglicht Benutzern, die Clientausführung über alle Nachrichten im Vertrag hinweg abzufangen und zu erweitern. Die <xref:System.ServiceModel.Dispatcher.ClientOperation>-Klasse ermöglicht Benutzern, die Clientausführung für alle Nachrichten eines bestimmten Vorgangs abzufangen und zu erweitern.  
  
 Das Ändern der Eigenschaften oder Einfügen von Anpassungen wird auf der Grundlage von Vertrags-, Endpunkt- und Vorgangsverhalten durchgeführt. Weitere Informationen zur Verwendung dieser Verhaltenstypen zum Ausführen von Client Lauf Zeit Anpassungen finden Sie unter [Konfigurieren und Erweitern der Laufzeit mit Verhalten](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="scenarios"></a>Szenarien  

 Es gibt viele Gründe, das Clientsystem zu erweitern:  
  
- Benutzerdefinierte Nachrichtenvalidierung. Ein Benutzer möchte durchsetzen, dass eine Nachricht für ein bestimmtes Schema gültig ist. Dies kann durch Implementieren der <xref:System.ServiceModel.Dispatcher.IClientMessageInspector>-Schnittstelle und Zuweisen der Implementierung an die <xref:System.ServiceModel.Dispatcher.DispatchRuntime.MessageInspectors%2A>-Eigenschaft erfolgen. Beispiele finden Sie unter Gewusst [wie: Überprüfen oder Ändern von Nachrichten auf dem](how-to-inspect-or-modify-messages-on-the-client.md) Client und Gewusst [wie: Überprüfen oder Ändern von Nachrichten auf dem Client](how-to-inspect-or-modify-messages-on-the-client.md).  
  
- Benutzerdefinierte Nachrichtenprotokollierung. Ein Benutzer möchte eventuell einige Anwendungsnachrichten prüfen und protokollieren, die durch einen Endpunkt fließen. Dies kann ebenfalls mit den Nachrichteninterceptorschnittstellen erreicht werden.  
  
- Benutzerdefinierte Nachrichtentransformationen. Anstatt den Anwendungscode zu ändern, möchte der Benutzer vielleicht bestimmte Transformationen (wie Versionsverwaltung) auf die Nachricht in der Laufzeit anwenden. Auch dies kann mit den Nachrichteninterceptorschnittstellen erreicht werden.  
  
- Benutzerdefiniertes Datenmodell. Ein Benutzer möchte möglicherweise ein Daten-oder Serialisierungsmodell aufweisen, das nicht standardmäßig in WCF unterstützt wird (nämlich,, <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> und- <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType> Objekte). Dies kann über die Implementierung der Nachrichtenformatierungsschnittstellen erreicht werden. Weitere Informationen finden Sie in der <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=nameWithType>-Eigenschaft und in der <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A?displayProperty=nameWithType>-Eigenschaft.  
  
- Benutzerdefinierte Parametervalidierung. Ein Benutzer möchte durchsetzen, dass typisierte Parameter gültig sind (im Gegensatz zu XML). Dies kann mit den Parameterinspektorschnittstellen erreicht werden. Ein Beispiel finden Sie unter Gewusst [wie: Überprüfen oder Ändern von Parametern](how-to-inspect-or-modify-parameters.md) oder [Client Validierung](../samples/client-validation.md).  
  
### <a name="using-the-clientruntime-class"></a>Verwenden der ClientRuntime-Klasse  

 Die <xref:System.ServiceModel.Dispatcher.ClientRuntime>-Klasse ist ein Erweiterungspunkt, an den Sie Erweiterungsobjekte anhängen können, die Nachrichten abfangen und das Clientverhalten ausdehnen. Abfangobjekte können alle Nachrichten in einem bestimmten Vertrag verarbeiten, nur Nachrichten für bestimmte Vorgänge verarbeiten, eine benutzerdefinierte Kanalinitialisierung durchführen und sonstiges benutzerdefiniertes Verhalten von Clientanwendungen implementieren.  
  
- Die <xref:System.ServiceModel.Dispatcher.ClientRuntime.CallbackDispatchRuntime%2A>-Eigenschaft gibt das DispatchRuntime-Objekt für durch Dienste initiierte Rückrufvorgangsclients zurück.  
  
- Die <xref:System.ServiceModel.Dispatcher.ClientRuntime.OperationSelector%2A>-Eigenschaft akzeptiert ein benutzerdefiniertes Vorgangsauswahlobjekt.  
  
- Die <xref:System.ServiceModel.Dispatcher.ClientRuntime.ChannelInitializers%2A>-Eigenschaft ermöglicht das Hinzufügen eines Kanalinitialisierers, der den Clientkanal prüfen oder abändern kann.  
  
- Die <xref:System.ServiceModel.Dispatcher.ClientRuntime.Operations%2A>-Eigenschaft ruft eine Auflistung von <xref:System.ServiceModel.Dispatcher.ClientOperation>-Objekten ab, denen Sie benutzerdefinierte Nachrichteninterceptoren hinzufügen können, die spezielle Funktionen für die Nachrichten dieses Vorgangs bereitstellen.  
  
- Die <xref:System.ServiceModel.Dispatcher.ClientRuntime.ManualAddressing%2A>-Eigenschaft ermöglicht einer Anwendung, bestimmte automatische Adressierungsheader zu deaktivieren, um die Adressierung direkt zu steuern.  
  
- Die <xref:System.ServiceModel.Dispatcher.ClientRuntime.Via%2A>-Eigenschaft legt den Wert des Ziels der Nachricht auf der Transportebene fest, um Vermittler und andere Szenarien zu unterstützen.  
  
- Die- <xref:System.ServiceModel.Dispatcher.ClientRuntime.MessageInspectors%2A> Eigenschaft ruft eine Auflistung von-Objekten ab <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> , denen Sie benutzerdefinierte nachrichteninterceptors für alle Nachrichten hinzufügen können, die über einen WCF-Client laufen.  
  
 Außerdem gibt es eine Reihe weiterer Eigenschaften, die die Clientvertragsinformationen abrufen:  
  
- <xref:System.ServiceModel.Dispatcher.ClientRuntime.ContractName%2A>  
  
- <xref:System.ServiceModel.Dispatcher.ClientRuntime.ContractNamespace%2A>  
  
- <xref:System.ServiceModel.Dispatcher.ClientRuntime.ContractClientType%2A>  
  
 Wenn der WCF-Client ein Duplex-WCF-Client ist, rufen die folgenden Eigenschaften auch die Rückruf-WCF-Client Informationen ab:  
  
- <xref:System.ServiceModel.Dispatcher.ClientRuntime.CallbackClientType%2A>  
  
- <xref:System.ServiceModel.Dispatcher.ClientRuntime.CallbackDispatchRuntime%2A>  
  
 Wenn Sie die Ausführung des WCF-Clients auf einem gesamten WCF-Client erweitern möchten, überprüfen Sie die in der-Klasse verfügbaren Eigenschaften, <xref:System.ServiceModel.Dispatcher.ClientRuntime> um festzustellen, ob das Ändern einer Eigenschaft oder das Implementieren einer Schnittstelle und hinzufügen zu einer Eigenschaft die von Ihnen gesuchte Sobald Sie eine bestimmte Erweiterung ausgewählt haben, müssen Sie Ihre Erweiterung in die geeignete <xref:System.ServiceModel.Dispatcher.ClientRuntime>-Eigenschaft einfügen, indem Sie ein Clientverhalten implementieren, das Zugriff auf die <xref:System.ServiceModel.Dispatcher.ClientRuntime>-Klasse bietet, sobald diese aufgerufen wird.  
  
 Sie können benutzerdefinierte Erweiterungsobjekte in eine Auflistung einfügen. Verwenden Sie dazu ein Vorgangsverhalten (ein Objekt, das <xref:System.ServiceModel.Description.IOperationBehavior> implementiert), ein Vertragsverhalten (ein Objekt, das <xref:System.ServiceModel.Description.IContractBehavior> implementiert) oder ein Endpunktverhalten (ein Objekt, das <xref:System.ServiceModel.Description.IEndpointBehavior> implementiert). Das installierende Verhaltensobjekt wird der entsprechenden Auflistung der Verhalten entweder programmatisch, deklarativ (durch Implementierung eines benutzerdefinierten Attributs) oder durch Implementierung eines benutzerdefinierten <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>-Objekts hinzugefügt, um das Verhalten, das eingefügt werden soll, anhand einer Anwendungskonfigurationsdatei zu aktivieren. Weitere Informationen finden Sie unter [Konfigurieren und Erweitern der Laufzeit mit Verhalten](configuring-and-extending-the-runtime-with-behaviors.md).  
  
 Beispiele zur Veranschaulichung der Abfang Funktion für einen WCF-Client finden Sie unter Vorgehens [Weise: Überprüfen oder Ändern von Nachrichten auf dem Client](how-to-inspect-or-modify-messages-on-the-client.md).  
  
### <a name="using-the-clientoperation-class"></a>Verwenden der ClientOperation-Klasse  

 Die <xref:System.ServiceModel.Dispatcher.ClientOperation>-Klasse ist der Ort für Änderungen an der Clientlaufzeit und die Einfügemarke für benutzerdefinierte Erweiterungen, die nur auf einen Dienstvorgang abzielen. (Um das Clientlaufzeitverhalten für alle Nachrichten in einem Vertrag zu ändern, verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientRuntime>-Klasse.)  
  
 Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientRuntime.Operations%2A>-Eigenschaft, um das <xref:System.ServiceModel.Dispatcher.ClientOperation>-Objekt zu suchen, das einen bestimmten Dienstvorgang darstellt. Die folgenden Eigenschaften ermöglichen es Ihnen, benutzerdefinierte Objekte in das WCF-Client System einzufügen:  
  
- Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A>-Eigenschaft, um eine benutzerdefinierte <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>-Implementierung für einen Vorgang einzufügen oder das aktuelle Formatierungsprogramm zu ändern.  
  
- Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A>-Eigenschaft, um eine benutzerdefinierte <xref:System.ServiceModel.Dispatcher.IParameterInspector>-Implementierung einzufügen oder die aktuelle Implementierung zu ändern.  
  
 Mit den folgenden Eigenschaften können Sie das System in Interaktion mit dem Formatierungsprogramm und benutzerdefinierten Parameterinspektoren ändern:  
  
- Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.SerializeRequest%2A>-Eigenschaft, um die Serialisierung einer ausgehenden Nachricht zu steuern.  
  
- Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.DeserializeReply%2A>-Eigenschaft, um die Deserialisierung einer eingehenden Nachricht zu steuern.  
  
- Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.Action%2A>-Eigenschaft, um die WS-Adressierungsaktion der Anforderungsnachricht zu steuern.  
  
- Verwenden <xref:System.ServiceModel.Dispatcher.ClientOperation.BeginMethod%2A> Sie und <xref:System.ServiceModel.Dispatcher.ClientOperation.EndMethod%2A> , um anzugeben, welche WCF-Client Methoden einem asynchronen Vorgang zugeordnet sind.  
  
- Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.FaultContractInfos%2A>-Eigenschaft, um eine Auflistung der angegebenen Typen abzurufen, die als Detailtyp in SOAP-Fehlern erscheinen können.  
  
- Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.IsInitiating%2A>-Eigenschaft und die <xref:System.ServiceModel.Dispatcher.ClientOperation.IsTerminating%2A>-Eigenschaft, um zu steuern, ob eine Sitzung initiiert bzw. abgebrochen wird, wenn der Vorgang aufgerufen wird.  
  
- Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.IsOneWay%2A>-Eigenschaft, um zu steuern, ob es sich bei dem Vorgang um einen unidirektionalen Vorgang handelt.  
  
- Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.Parent%2A>-Eigenschaft, um das darin enthaltene <xref:System.ServiceModel.Dispatcher.ClientRuntime>-Objekt zu ermitteln.  
  
- Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.Name%2A>-Eigenschaft, um den Namen des Vorgangs abzurufen.  
  
- Verwenden Sie die <xref:System.ServiceModel.Dispatcher.ClientOperation.SyncMethod%2A>-Eigenschaft, um zu steuern, welche Methode dem Vorgang zugeordnet wird.  
  
 Um die Ausführung des WCF-Clients über nur einen Dienst Vorgang zu erweitern, überprüfen Sie die in der-Klasse verfügbaren Eigenschaften, <xref:System.ServiceModel.Dispatcher.ClientOperation> um festzustellen, ob das Ändern einer Eigenschaft oder das Implementieren einer Schnittstelle und das Hinzufügen zu einer Eigenschaft die von Ihnen gesuchte Funktionalität Sobald Sie eine bestimmte Erweiterung ausgewählt haben, müssen Sie Ihre Erweiterung in die geeignete <xref:System.ServiceModel.Dispatcher.ClientOperation>-Eigenschaft einfügen, indem Sie ein Clientverhalten implementieren, das Zugriff auf die <xref:System.ServiceModel.Dispatcher.ClientOperation>-Klasse bietet, sobald diese aufgerufen wird. In diesem Verhalten können Sie dann die <xref:System.ServiceModel.Dispatcher.ClientRuntime>-Eigenschaft ändern, um sie Ihren Anforderungen anzupassen.  
  
 In der Regel reicht die Implementierung eines Vorgangsverhaltens (ein Objekt, das die <xref:System.ServiceModel.Description.IOperationBehavior>-Schnittstelle implementiert) aus, Sie können jedoch auch Endpunktverhalten und Vertragsverhalten verwenden, um dasselbe zu erreichen, indem Sie <xref:System.ServiceModel.Description.OperationDescription> für einen bestimmten Vorgang suchen und dort das Verhalten anfügen. Weitere Informationen finden Sie unter [Konfigurieren und Erweitern der Laufzeit mit Verhalten](configuring-and-extending-the-runtime-with-behaviors.md).  
  
 Um das benutzerdefinierte Verhalten der Konfiguration zu verwenden, installieren Sie das Verhalten mit einem benutzerdefinierten Verhaltenskonfigurationsabschnitts-Handler. Sie können auch das Verhalten installieren, indem Sie ein benutzerdefiniertes Attribut erstellen.  
  
 Beispiele zur Veranschaulichung der Abfang Funktion für einen WCF-Client finden Sie unter Gewusst [wie: Überprüfen oder Ändern von Parametern](how-to-inspect-or-modify-parameters.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Dispatcher.ClientRuntime>
- <xref:System.ServiceModel.Dispatcher.ClientOperation>
- [Vorgehensweise: Überprüfen oder Ändern von Nachrichten auf dem Client](how-to-inspect-or-modify-messages-on-the-client.md)
- [Vorgehensweise: Überprüfen oder Ändern von Parametern](how-to-inspect-or-modify-parameters.md)

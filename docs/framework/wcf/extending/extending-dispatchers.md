---
title: Erweitern von Verteilern
ms.date: 03/30/2017
helpviewer_keywords:
- dispatcher extensions [WCF]
ms.assetid: d0ad15ac-fa12-4f27-80e8-7ac2271e5985
ms.openlocfilehash: fa9d5c40c2ae813493b3643048fa7eaba00c431d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273229"
---
# <a name="extending-dispatchers"></a>Erweitern von Verteilern

Verteiler sind dafür verantwortlich, eingehende Nachrichten aus den zugrunde liegenden Kanälen abzufangen, sie in Methodenaufrufe im Anwendungscode zu übersetzen und die Ergebnisse zurück an den Aufrufer zu senden. Verteilererweiterungen versetzen Sie in die Lage, diese Verarbeitung zu ändern.  Sie können Nachrichten- oder Parameterinspektoren implementieren, die den Inhalt von Nachrichten oder Parametern überprüfen bzw. ändern.  Sie können die Weiterleitung von Nachrichten an Vorgänge ändern oder andere Funktionalität bereitstellen.

In diesem Thema wird beschrieben, wie <xref:System.ServiceModel.Dispatcher.DispatchRuntime> Sie die-Klasse und die- <xref:System.ServiceModel.Dispatcher.DispatchOperation> Klasse in einer Windows Communication Foundation (WCF)-Dienst Anwendung verwenden, um das Standard Ausführungs Verhalten eines Verteilers zu ändern oder um Nachrichten, Parameter oder Rückgabewerte abzufangen oder zu ändern, bevor Sie von der Kanal Schicht gesendet oder abgerufen werden. Weitere Informationen zur entsprechenden Client Lauf Zeit Nachrichtenverarbeitung finden Sie unter [Erweitern von Clients](extending-clients.md). Informationen über die Rolle, die <xref:System.ServiceModel.IExtensibleObject%601> Typen beim Zugriff auf den gemeinsamen Zustand zwischen verschiedenen Lauf Zeit Anpassungs Objekten spielen, finden Sie unter [erweiterbare Objekte](extensible-objects.md).

## <a name="dispatchers"></a>Verteiler

Die Dienstmodellebene führt die Konvertierung zwischen dem Programmiermodell des Entwicklers und dem zugrunde liegenden Nachrichtenaustausch, gewöhnlich als Kanalschicht bezeichnet, durch. In WCF sind die Kanal-und Endpunkt Verteiler <xref:System.ServiceModel.Dispatcher.ChannelDispatcher> ( <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> bzw.) die Dienst Komponenten, die für das akzeptieren neuer Kanäle, das Empfangen von Nachrichten, die Verteilung und den Aufruf von Vorgängen sowie die Verarbeitung von Antworten zuständig sind. Verteilerobjekte sind empfangende Objekte, aber auch Rückrufvertragsimplementierungen in Duplexdiensten machen ihre Verteilerobjekte für Überprüfung, Änderung oder Erweiterung verfügbar.

Der Kanalverteiler (und der zugehörige <xref:System.ServiceModel.Channels.IChannelListener>) fangen eingehende Nachrichten aus den zugrunde liegenden Kanälen ab und übergeben diese Nachrichten ihren jeweiligen Endpunktverteilern. Jeder Endpunktverteiler hat eine <xref:System.ServiceModel.Dispatcher.DispatchRuntime>, die die Nachrichten an die entsprechende <xref:System.ServiceModel.Dispatcher.DispatchOperation> weiterleitet, die für den Aufruf der Methode verantwortlich ist, die den Vorgang implementiert. Dabei werden verschiedene optionale und notwendige Erweiterungsklassen aufgerufen. In diesem Thema wird erklärt, wie diese Elemente zusammenpassen, und wie Sie deren Eigenschaften ändern und eigenen Code schreiben, um die Basisfunktionalität zu erweitern.

Verteilereigenschaften und geänderte Anpassungsobjekte werden mithilfe von Dienst-, Endpunkt-, Vertrags- und Vorgangsverhaltensobjekten eingefügt. In diesem Thema wird nicht beschrieben, wie Verhaltensobjekte verwendet werden. Weitere Informationen zu den Typen, die zum Einfügen von Verteiler-Änderungen verwendet werden, finden Sie unter [Konfigurieren und Erweitern der Laufzeit mit Verhalten](configuring-and-extending-the-runtime-with-behaviors.md).

Die folgende Grafik bietet einen Überblick über die architektonischen Elemente in einem Dienst.

![Die Dispatchlaufzeit-Architektur](./media/wcfc-dispatchruntimearchc.gif "wcfc_DispatchRuntimeArchc")

### <a name="channel-dispatchers"></a>Kanalverteiler

Ein <xref:System.ServiceModel.Dispatcher.ChannelDispatcher>-Objekt wird erstellt, um einen <xref:System.ServiceModel.Channels.IChannelListener> an einem bestimmten URI (als Abhör-URI bezeichnet) einer Instanz eines Diensts zuzuordnen. Jedes <xref:System.ServiceModel.ServiceHost>-Objekt kann über viele <xref:System.ServiceModel.Dispatcher.ChannelDispatcher>-Objekte verfügen, die jeweils einem Listener und einem Abhör-URI zugeordnet sind. Wenn eine Nachricht eingeht, fragt der <xref:System.ServiceModel.Dispatcher.ChannelDispatcher> jedes der zugeordneten <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>-Objekte ab, ob der Endpunkt die Nachricht akzeptieren kann, und leitet die Nachricht an den Endpunkt weiter, der dies kann.

Alle Eigenschaften, die die Lebensdauer und das Verhalten einer Kanalsitzung steuern, sind zur Überprüfung oder Änderung im <xref:System.ServiceModel.Dispatcher.ChannelDispatcher>-Objekt verfügbar. Dies schließt benutzerdefinierte Kanalinitialisierer, den Kanallistener, den Host, den zugeordneten <xref:System.ServiceModel.InstanceContext> usw. ein.

### <a name="endpoint-dispatchers"></a>Endpunktverteiler

Das <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>-Objekt ist verantwortlich für das Verarbeiten von Nachrichten von einem <xref:System.ServiceModel.Dispatcher.ChannelDispatcher>, wenn die Zieladresse einer Nachricht mit der <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A>-Eigenschaft übereinstimmt und die Nachrichtenaktion mit der <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>-Eigenschaft übereinstimmt. Wenn zwei <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>-Objekte eine Nachricht akzeptieren können, bestimmt der Wert der <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.FilterPriority%2A>-Eigenschaft den Endpunkt mit höherer Priorität.

Verwenden Sie das <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>-Objekt, um die beiden Haupterweiterungspunkte des Dienstmodells &#8211; die <xref:System.ServiceModel.Dispatcher.DispatchRuntime>-Klasse und die <xref:System.ServiceModel.Dispatcher.DispatchOperation>-Klasse &#8211; abzurufen, die Sie verwenden können, um die Verarbeitung durch den Verteiler anzupassen. Die <xref:System.ServiceModel.Dispatcher.DispatchRuntime>-Klasse ermöglicht Benutzern, den Verteiler im Vertragsbereich (also für alle Nachrichten in einem Vertrag) abzufangen und zu erweitern. Die <xref:System.ServiceModel.Dispatcher.DispatchOperation>-Klasse ermöglicht Benutzern, den Verteiler im Vorgangsbereich (also für alle Nachrichten in einem Vorgang) abzufangen und zu erweitern.

## <a name="scenarios"></a>Szenarien

Es gibt eine Reihe von Gründen, den Verteiler zu erweitern:

- Benutzerdefinierte Nachrichtenvalidierung. Benutzer können durchsetzen, dass eine Nachricht für ein bestimmtes Schema gültig ist. Dies kann über die Implementierung der Nachrichteninterceptorschnittstellen erreicht werden. Ein Beispiel finden Sie unter [Nachrichten Inspektoren](../samples/message-inspectors.md).

- Benutzerdefinierte Nachrichtenprotokollierung. Benutzer können einige Anwendungsnachrichten prüfen und protokollieren, die durch einen Endpunkt fließen. Dies kann ebenfalls mit den Nachrichteninterceptorschnittstellen erreicht werden.

- Benutzerdefinierte Nachrichtentransformationen. Benutzer können bestimmte Transformationen (beispielsweise die Versionsverwaltung) auf die Nachricht in der Laufzeit anwenden. Auch dies kann mit den Nachrichteninterceptorschnittstellen erreicht werden.

- Benutzerdefiniertes Datenmodell. Benutzer können ein anderes Datenserialisierungsmodell als die standardmäßig in WCF unterstützten Daten (,, und unformatierte <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> Nachrichten) haben. Dies kann über die Implementierung der Nachrichtenformatierungsschnittstellen erreicht werden. Ein Beispiel finden Sie unter [Vorgangs Formatierer und Vorgangs Auswahl](../samples/operation-formatter-and-operation-selector.md).

- Benutzerdefinierte Parametervalidierung. Benutzer können durchsetzen, dass typisierte Parameter gültig sind (im Gegensatz zu XML). Dies kann mit den Parameterinspektorschnittstellen erreicht werden.

- Benutzerdefinierte Vorgangsverteilung. Benutzer können die Verteilung an etwas anderes als an eine Aktion implementieren &#8211; beispielsweise an das Textelement oder an eine benutzerdefinierte Nachrichteneigenschaft. Dies kann über die Verwendung der <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>-Schnittstelle erreicht werden. Ein Beispiel finden Sie unter [Vorgangs Formatierer und Vorgangs Auswahl](../samples/operation-formatter-and-operation-selector.md).

- Objektpooling. Benutzer können Instanzen zusammenlegen, statt für jeden Aufruf eine neue Instanz zuzuordnen. Dies kann über die Implementierung der Instanzanbieterschnittstellen erreicht werden. Ein Beispiel finden Sie unter [Pooling](../samples/pooling.md).

- Instanzleasing. Benutzer können ein Leasingmuster ähnlich dem von .NET&#160;Framework Remoting für die Lebensdauer der Instanz implementieren. Dies kann mit den Instanzkontextlebensdauer-Schnittstellen erreicht werden.

- Benutzerdefinierte Fehlerbehandlung. Benutzer können steuern, wie lokale Fehler verarbeitet werden und wie Clients über Fehler unterrichtet werden. Dies kann mithilfe der <xref:System.ServiceModel.Dispatcher.IErrorHandler>-Schnittstellen implementiert werden.

- Benutzerdefiniertes Autorisierungsverhalten Benutzer können eine benutzerdefinierte Zugriffssteuerung implementieren, indem sie die Vertrags- und Vorgangslaufzeitelemente erweitern und auf in der Nachricht enthaltenen Tokens basierende Sicherheitsüberprüfungen hinzufügen. Dies kann entweder mit den Nachrichteninterceptor- oder den Parameterinterceptorschnittstellen erreicht werden. Beispiele finden Sie unter [Sicherheits Erweiterbarkeit](../samples/security-extensibility.md).

  > [!CAUTION]
  > Da das Ändern von Sicherheitseigenschaften eine Gefährdung der Sicherheit von WCF-Anwendungen hat, wird dringend empfohlen, sicherheitsrelevante Änderungen mit Sorgfalt durchzuführen und vor der Bereitstellung gründlich zu testen.

- Benutzerdefinierte WCF-Laufzeitvalidierungs-Steuerelemente. Sie können benutzerdefinierte Validierungs Steuerelemente installieren, die Dienste, Verträge und Bindungen untersuchen, um Richtlinien auf Unternehmensebene in Bezug auf WCF-Anwendungen zu erzwingen. (Informationen hierzu finden Sie beispielsweise unter Vorgehens [Weise: Sperren von Endpunkten im Unternehmen](how-to-lock-down-endpoints-in-the-enterprise.md).)

### <a name="using-the-dispatchruntime-class"></a>Verwenden der DispatchRuntime-Klasse

Verwenden Sie die <xref:System.ServiceModel.Dispatcher.DispatchRuntime>-Klasse, um entweder das Standardverhalten eines Diensts oder eines einzelnen Endpunkts zu ändern, oder um Objekte einzufügen, die benutzerdefinierte Änderungen für einen oder für beide der folgenden Dienstprozesse implementieren (oder für Clientprozesse im Fall eines Duplexclients):

- Die Transformation eingehender Nachrichten in Objekte und die Freigabe dieser Objekte als Methodenaufrufe in einem Dienstobjekt.

- Die Transformation von Objekten, die von der Antwort auf einen Dienstvorgangsaufruf empfangen wurden, in ausgehende Nachrichten.

Die <xref:System.ServiceModel.Dispatcher.DispatchRuntime>-Klasse ermöglicht Ihnen, den Kanal- oder Endpunktverteiler für alle Nachrichten in einem bestimmten Vertrag auch dann abzufangen und zu erweitern, wenn eine Nachricht nicht erkannt wurde. Wenn eine Nachricht eintrifft, die mit keinem im Vertrag deklarierten Vorgang übereinstimmt, wird sie an den Vorgang geleitet, der von der <xref:System.ServiceModel.Dispatcher.DispatchRuntime.UnhandledDispatchOperation%2A>-Eigenschaft zurückgegeben wird. Informationen dazu, wie ein Verteiler erweitert wird, der alle Nachrichten für einen bestimmten Vorgang abfängt, finden Sie unter der <xref:System.ServiceModel.Dispatcher.DispatchOperation>-Klasse.

Es gibt vier Hauptbereiche der Verteilererweiterbarkeit, die von der <xref:System.ServiceModel.Dispatcher.DispatchRuntime>-Klasse verfügbar gemacht werden:

1. Kanalkomponenten verwenden Eigenschaften der <xref:System.ServiceModel.Dispatcher.DispatchRuntime>-Klasse sowie jene des zugeordneten Kanalverteilers, der von der <xref:System.ServiceModel.Dispatcher.DispatchRuntime.ChannelDispatcher%2A>-Eigenschaft zurückgegeben wird, um festzulegen, wie der Kanalverteiler Kanäle akzeptiert und schließt. Dazu gehören die Eigenschaften <xref:System.ServiceModel.Dispatcher.ChannelDispatcher.ChannelInitializers%2A> und <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InputSessionShutdownHandlers%2A>.

2. Nachrichtenkomponenten werden für jede verarbeitete Nachricht angepasst. Dazu gehören die Eigenschaften <xref:System.ServiceModel.Dispatcher.DispatchRuntime.MessageInspectors%2A>, <xref:System.ServiceModel.Dispatcher.DispatchRuntime.OperationSelector%2A>, <xref:System.ServiceModel.Dispatcher.DispatchRuntime.Operations%2A> und <xref:System.ServiceModel.Dispatcher.ChannelDispatcher.ErrorHandlers%2A>.

3. Instanzkomponenten passen die Erstellung, Lebensdauer und Freigabe von Instanzen des Diensttyps an. Weitere Informationen zur Lebensdauer von Dienstobjekten finden Sie in den Ausführungen zur <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>-Eigenschaft. Dazu gehören die Eigenschaften <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextInitializers%2A> und <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>.

4. Sicherheitsrelevante Komponenten können die folgenden Eigenschaften verwenden:

    - <xref:System.ServiceModel.Dispatcher.DispatchRuntime.SecurityAuditLogLocation%2A> gibt an, wohin Überwachungsereignisse geschrieben werden.

    - <xref:System.ServiceModel.Dispatcher.DispatchRuntime.ImpersonateCallerForAllOperations%2A> steuert, ob der Dienst versucht, mithilfe der Anmeldeinformationen der eingehenden Nachricht einen Identitätswechsel durchzuführen.

    - <xref:System.ServiceModel.Dispatcher.DispatchRuntime.MessageAuthenticationAuditLevel%2A> steuert, ob Ereignisse für erfolgreiche Nachrichtenauthentifizierung in das Ereignisprotokoll geschrieben werden, das von <xref:System.ServiceModel.Dispatcher.DispatchRuntime.SecurityAuditLogLocation%2A> angegeben wird.

    - <xref:System.ServiceModel.Dispatcher.DispatchRuntime.PrincipalPermissionMode%2A> steuert, wie die <xref:System.Threading.Thread.CurrentPrincipal%2A>-Eigenschaft festgelegt wird.

    - <xref:System.ServiceModel.Dispatcher.DispatchRuntime.ServiceAuthorizationAuditLevel%2A> gibt an, wie die Überwachung von Autorisierungsereignissen durchgeführt wird.

    - <xref:System.ServiceModel.Dispatcher.DispatchRuntime.SuppressAuditFailure%2A> gibt an, ob während des Protokollierungsprozesses auftretende nicht schwerwiegende Ausnahmen unterdrückt werden sollen.

In der Regel werden benutzerdefinierte Erweiterungsobjekte einer <xref:System.ServiceModel.Dispatcher.DispatchRuntime>-Eigenschaft zugewiesen oder durch ein Dienstverhalten (ein Objekt, das <xref:System.ServiceModel.Description.IServiceBehavior> implementiert), durch ein Vertragsverhalten (ein Objekt, das <xref:System.ServiceModel.Description.IContractBehavior> implementiert) oder durch ein Endpunktverhalten (ein Objekt, das <xref:System.ServiceModel.Description.IEndpointBehavior> implementiert) in eine Auflistung eingefügt. Das installierende Verhaltensobjekt wird dann der entsprechenden Verhaltensauflistung entweder programmgesteuert oder durch Implementierung eines benutzerdefinierten <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>-Objekts hinzugefügt, um das Verhalten, das eingefügt werden soll, mithilfe einer Anwendungskonfigurationsdatei zu aktivieren.

Duplexclients (Clients, die den durch einen Duplexdienst angegebenen Rückrufvertrag implementieren) verfügen auch über ein <xref:System.ServiceModel.Dispatcher.DispatchRuntime>-Objekt, auf das mithilfe der <xref:System.ServiceModel.Dispatcher.ClientRuntime.CallbackDispatchRuntime%2A>-Eigenschaft zugegriffen werden kann.

### <a name="using-the-dispatchoperation-class"></a>Verwenden der DispatchOperation-Klasse

Die <xref:System.ServiceModel.Dispatcher.DispatchOperation>-Klasse ist der Speicherort für Laufzeitänderungen und die Einfügemarke für benutzerdefinierte Erweiterungen, die nur auf einen Dienstvorgang abzielen. (Um das Dienstlaufzeit-Verhalten für alle Nachrichten in einem Vertrag zu ändern, verwenden Sie die <xref:System.ServiceModel.Dispatcher.DispatchRuntime>-Klasse.)

Installieren Sie <xref:System.ServiceModel.Dispatcher.DispatchOperation>-Änderungen mithilfe eines benutzerdefinierten Dienstverhaltensobjekts.

Verwenden Sie die <xref:System.ServiceModel.Dispatcher.DispatchRuntime.Operations%2A>-Eigenschaft, um das <xref:System.ServiceModel.Dispatcher.DispatchOperation>-Objekt zu suchen, das einen bestimmten Dienstvorgang darstellt.

Die folgenden Eigenschaften kontrollieren die Laufzeitausführung auf Vorgangsebene:

- Die Eigenschaften <xref:System.ServiceModel.Dispatcher.DispatchOperation.Action%2A>, <xref:System.ServiceModel.Dispatcher.DispatchOperation.ReplyAction%2A>, <xref:System.ServiceModel.Dispatcher.DispatchOperation.FaultContractInfos%2A>, <xref:System.ServiceModel.Dispatcher.DispatchOperation.IsOneWay%2A>, <xref:System.ServiceModel.Dispatcher.DispatchOperation.IsTerminating%2A> und <xref:System.ServiceModel.Dispatcher.DispatchOperation.Name%2A> erhalten die jeweiligen Werte für den Vorgang.

- Die Eigenschaften <xref:System.ServiceModel.Dispatcher.DispatchOperation.TransactionAutoComplete%2A> und <xref:System.ServiceModel.Dispatcher.DispatchOperation.TransactionRequired%2A> geben das Transaktionsverhalten an.

- Die Eigenschaften <xref:System.ServiceModel.Dispatcher.DispatchOperation.ReleaseInstanceBeforeCall%2A> und <xref:System.ServiceModel.Dispatcher.DispatchOperation.ReleaseInstanceAfterCall%2A> steuern die Lebensdauer des benutzerdefinierten Dienstobjekts bezogen auf den <xref:System.ServiceModel.InstanceContext>.

- Die Eigenschaften <xref:System.ServiceModel.Dispatcher.DispatchOperation.DeserializeRequest%2A>, <xref:System.ServiceModel.Dispatcher.DispatchOperation.SerializeReply%2A> und <xref:System.ServiceModel.Dispatcher.DispatchOperation.Formatter%2A> ermöglichen die explizite Steuerung der Konvertierung von Nachrichten in Objekte und von Objekten in Nachrichten.

- Die <xref:System.ServiceModel.Dispatcher.DispatchOperation.Impersonation%2A>-Eigenschaft gibt die Ebene des Identitätswechsels des Vorgangs an.

- Die <xref:System.ServiceModel.Dispatcher.DispatchOperation.CallContextInitializers%2A>-Eigenschaft fügt benutzerdefinierte Erweiterungen des Aufrufkontexts für den Vorgang ein.

- Die <xref:System.ServiceModel.Dispatcher.DispatchOperation.AutoDisposeParameters%2A>-Eigenschaft steuert, wann Parameterobjekte gelöscht werden.

- Die <xref:System.ServiceModel.Dispatcher.DispatchOperation.Invoker%2A>-Eigenschaft ist für das Einfügen eines benutzerdefinierten aufrufenden Objekts.

- Die <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A>-Eigenschaft ermöglicht es Ihnen, einen benutzerdefinierten Parameterinspektor einzufügen, den Sie verwenden können, um Parameter und Rückgabewerte zu überprüfen oder zu ändern.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Dispatcher.DispatchRuntime>
- <xref:System.ServiceModel.Dispatcher.DispatchOperation>
- [Vorgehensweise: Überprüfen und Ändern von Nachrichten auf dem Dienst](how-to-inspect-and-modify-messages-on-the-service.md)
- [Vorgehensweise: Überprüfen oder Ändern von Parametern](how-to-inspect-or-modify-parameters.md)
- [Vorgehensweise: Sperren von Endpunkten im Unternehmen](how-to-lock-down-endpoints-in-the-enterprise.md)

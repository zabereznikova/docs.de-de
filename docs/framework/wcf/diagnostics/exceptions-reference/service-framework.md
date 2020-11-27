---
title: Dienstframework
ms.date: 03/30/2017
ms.assetid: 75f60b87-f80e-4377-ba7c-8e6becaa2b28
ms.openlocfilehash: 1fb39f2106e027cc5d4125cfb0bc89f3e5983cec
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285719"
---
# <a name="service-framework"></a>Dienstframework

In diesem Thema sind alle von Dienstframeworkdaten erzeugten Ausnahmen aufgeführt.  
  
## <a name="exception-list"></a>Ausnahmeliste  
  
|Ressourcencode|Ressourcenzeichenfolge|  
|-------------------|---------------------|  
|ABindingInstanceHasAlreadyBeenAssociatedTo1|Es wurde bereits eine Bindungsinstanz zugeordnet, um den angegebenen URI (Uniform Resource Identifier) abzuhören. Wenn zwei Endpunkte den gleichen Resource Indicator zum Abhören verwenden möchten, müssen sie auch die gleiche Bindungsobjektinstanz verwenden. Die zwei in Konflikt stehenden Endpunkte wurden in Aufrufen von AddServiceEndpoint(), in einer Konfigurationsdatei oder in einer Kombination aus AddServiceEndpoint() und Konfiguration angegeben.|  
|AChannelServiceEndpointIsNull0|Ein Kanal- oder ein Dienstendpunkt sind NULL.|  
|AChannelServiceEndpointSContractSNameIsNull0|Der Name des Endpunktvertrags für einen Dienst/Kanal ist NULL oder leer.|  
|AChannelServiceEndpointSContractSNamespace0|Der Namespace des Endpunktvertrags für einen Dienst/Kanal ist NULL.|  
|BaseAddressCannotHaveFragment|Eine Basisadresse kann kein URI-Fragment enthalten.|  
|BaseAddressCannotHaveQuery|Eine Basisadresse kann keine URI-Abfragezeichenfolge enthalten.|  
|BaseAddressCannotHaveUserInfo|Eine Basisadresse kann keinen Abschnitt mit Benutzerinformationen für einen URI enthalten.|  
|BaseAddressDuplicateScheme|Diese Auflistung enthält bereits eine Adresse mit dem angegebenen Schema. Jedes Schema in dieser Auflistung darf nur eine Adresse enthalten.|  
|BaseAddressMustBeAbsolute|Es kann nur ein absoluter URI als Basisadresse verwendet werden.|  
|BindingDoesnTSupportAnyChannelTypes1|Die angegebene Bindung unterstützt das Erstellen von Kanaltypen nicht. Die Bindungselemente in einer benutzerdefinierten Bindung werden falsch oder in der falschen Reihenfolge gestapelt. Am unteren Rand ist ein Transport für den Stapel erforderlich. Die empfohlene Reihenfolge für Bindungselemente ist: TransactionFlow, ReliableSession, Security, CompositeDuplex, OneWay, StreamSecurity, MessageEncoding, Transport.|  
|BindingDoesnTSupportDuplexButContractRequires1|Vertrag erfordert Duplex. Die angegebene Bindung bietet hierfür keine Unterstützung oder wurde nicht ordnungsgemäß für eine Unterstützung konfiguriert.|  
|BindingDoesnTSupportOneWayButContractRequires1|Vertrag erfordert OneWay. Die angegebene Bindung bietet hierfür keine Unterstützung oder wurde nicht ordnungsgemäß für eine Unterstützung konfiguriert.|  
|BindingDoesnTSupportRequestReplyButContract1|Vertrag erfordert Anforderung/Antwort. Die angegebene Bindung bietet hierfür keine Unterstützung oder wurde nicht ordnungsgemäß für eine Unterstützung konfiguriert.|  
|BindingDoesnTSupportSessionButContractRequires1|Vertrag erfordert Sitzung.  Die angegebene Bindung bietet hierfür keine Unterstützung oder wurde nicht ordnungsgemäß für eine Unterstützung konfiguriert.|  
|BindingDoesnTSupportTwoWayButContractRequires1|Vertrag erfordert TwoWay (entweder Anforderung-Antwort oder Duplex). Die angegebene Bindung bietet hierfür keine Unterstützung oder wurde nicht ordnungsgemäß für eine Unterstützung konfiguriert.|  
|BindingRequirementsAttributeDisallowsQueuedDelivery1|DeliveryRequirementsAttribute lässt QueuedDelivery nicht zu. Die Bindung für den Endpunkt mit dem angegebenen Vertrag bietet entsprechende Unterstützung.|  
|BindingRequirementsAttributeRequiresQueuedDelivery1|DeliveryRequirementsAttribute erfordert QueuedDelivery. Die Bindung für den Endpunkt mit dem angegebenen Vertrag bietet hierfür keine Unterstützung oder wurde nicht ordnungsgemäß für die Unterstützung konfiguriert.|  
|channelDoesNotHaveADuplexSession0|Der aktuelle Kanal unterstützt das Schließen der Ausgabesitzung nicht. ISessionChannel wird von diesem Kanal nicht implementiert \<IDuplexSession> .|  
|ClientRuntimeRequiresFormatter0|Die angegebene ClientOperation erfordert ein Formatierungsprogramm, da SerializeRequest und DeserializeReply nicht beide False sind.|  
|CommunicationObjectAborted1|Das angegebene Kommunikationsobjekt kann nicht für die Kommunikation verwendet werden, da es beendet wurde.|  
|CommunicationObjectAbortedStack2|Das angegebene Kommunikations Objekt kann nicht für die Kommunikation verwendet werden, da es beendet wurde: {1}|  
|CommunicationObjectBaseClassMethodNotCalled|Das angegebene Kommunikations Objekt hat die virtuelle Funktion überschrieben, {1} ruft jedoch nicht die in der Basisklasse definierte Version auf.|  
|ContractIsNotSelfConsistentItHasOneOrMore2|Der angegebene Vertrag weist einen oder mehrere IsTerminating- oder Nicht-IsInitiating-Vorgänge auf. Die SessionMode-Eigenschaft wurde nicht auf SessionMode.Required festgelegt. Das IsInitiating-Attribut und das IsTerminating-Attribut können nur im Kontext einer Sitzung verwendet werden.|  
|CouldnTCreateChannelForChannelType2|Der angegebene Kanaltyp wurde angefordert, die angegebene Bindung bietet hierfür jedoch keine Unterstützung oder wurde nicht ordnungsgemäß für eine Unterstützung konfiguriert.|  
|DispatchRuntimeRequiresFormatter0|Die angegebene DispatchOperation erfordert ein Formatierungsprogramm, da DeserializeRequest und SerializeReply nicht beide False sind.|  
|EndMethodsCannotBeDecoratedWithOperationContractAttribute|Wenn Sie das IAsyncResult-Entwurfsmuster verwenden, kann die End-Methode nicht mit dem OperationContractAttribute verwendet werden. Nur die entsprechende Begin-Methode kann mit dem OperationContractAttribute verwendet werden. Dieses Attribut gilt für das Begin/End-Methodenpaar.|  
|EndpointListenerRequirementsCannotBeMetBy3|Die ChannelDispatcher-Anforderungen können vom IChannelListener für die angegebene Bindung nicht erfüllt werden, da der Vertrag die Unterstützung eines der angegebenen Kanaltypen erfordert. Die Bindung unterstützt jedoch nur die angegebenen Kanaltypen.|  
|EndpointsMustHaveAValidBinding0|Endpunkte müssen eine gültige Bindung haben.|  
|InvalidOrUnrecognizedAction|Die Nachricht kann nicht verarbeitet werden, da die angegebene Aktion ungültig ist oder nicht erkannt wurde.|  
|MultipleMebesInParameters|In den BindingParameters des BindingContext wurde mehr als ein MessageEncodingBindingElement gefunden. CustomBinding kann nicht mehrere MessageEncodingBindingElements aufweisen. Entfernen Sie alle Elemente bis auf eins.|  
|MultipleStreamUpgradeProvidersInParameters|In den BindingParameters des BindingContext wurde mehr als ein IStreamUpgradeProviderElement gefunden. CustomBinding kann nicht mehrere IStreamUpgradeProviderElements aufweisen. Entfernen Sie alle Elemente bis auf eins.|  
|NoChannelBuilderAvailable|Mit der Bindung können keine Kanalfactory oder kein Kanallistener erstellt werden, da kein TransportBindingElement vorhanden ist. Jede Bindung muss über mindestens ein Bindungselement verfügen, das von TransportBindingElement abgeleitet wird.|  
|NotAllBindingElementsBuilt|Einige Elemente in dieser Bindung wurden beim Erstellen der Kanalfactory und des Kanallisteners nicht verwendet. Die Bindungselemente sind nicht ordnungsgemäß angeordnet. Die empfohlene Reihenfolge für Bindungselemente ist: TransactionFlow, ReliableSession, Security, CompositeDuplex, OneWay, StreamSecurity, MessageEncoding, Transport.  Das TransportBindingElement muss an letzter Stelle stehen. Die angegebenen Bindungselemente wurden nicht erstellt.|  
|RuntimeRequiresInvoker0|Der Verteilvorgang erfordert eine aufrufende Instanz.|  
|ServiceHasZeroAppEndpoints|Der angegebene Dienst verfügt über keine Anwendungsendpunkte (keine Infrastrukturendpunkte). Dies kann folgende Ursachen haben: Es wurde keine Konfigurationsdatei für die Anwendung gefunden, in der Konfigurationsdatei wurde kein mit dem Dienstnamen übereinstimmendes Dienstelement gefunden oder im Dienstelement wurden keine Endpunkte definiert.|  
|SFxActionMismatch|Aufgrund der nicht übereinstimmenden Aktionen kann keine typisierte Nachricht erstellt werden. Die angegebene Aktion wurde erwartet, es trat jedoch eine andere Aktion auf.|  
|SFxAnonymousTypeNotSupported|Der angegebene Teil in der angegebenen Nachricht kann nicht mit RPC exportiert oder codiert werden, da es sich um einen anonymen Typ handelt.|  
|SFxBadMetadataLocationNoAppropriateBaseAddress|Die für ServiceMetadataBehavior über die ExternalMetadataLocation-Eigenschaft oder das externalMetadataLocation-Attribut im serviceMetadata-Abschnitt der Konfigurationsdatei bereitgestellte URL war eine relative URL. Es ist keine Basisadresse vorhanden, um die URL aufzulösen.|  
|SFxBadMetadataMustBePolicy|Es muss ein Richtlinien-XmlElement mit dem angegebenen Namespace und dem angegebenen Namen bereitgestellt werden. Dieses XmlElement weist den angegebenen Namespace und den angegebenen Namen auf.|  
|SFxBodyObjectTypeCannotBeInherited|Der angegebene Typ kann von keiner anderen Klasse als der Klasse des Objekts erben, das als Body-Objekt im RPC-Format verwendet wird.|  
|SFxBodyObjectTypeCannotBeInterface|Der angegebene Typ implementiert die angegebene Schnittstelle, die für das Body-Objekt im RPC-Format nicht unterstützt wird.|  
|SFxCallbackBehaviorAttributeOnlyOnDuplex|Das CallbackBehaviorAttribute kann nur als Verhalten für einen Endpunkt mit einem Duplexvertrag ausgeführt werden. Der angegebene Vertrag ist kein Duplexvertrag und enthält keine Rückrufvorgänge.|  
|SFxCallbackRequestReplyInOrder1|Die Antwort kann nicht empfangen werden, bevor die Verarbeitung der aktuellen Nachricht abgeschlossen ist. Wenn Sie die Verarbeitung von Nachrichten außerhalb der normalen Reihenfolge (Out-of-Order) zulassen möchten, geben Sie ConcurrencyMode von Reentrant oder von Multiple für das angegebene Element an.|  
|SfxCallbackTypeCannotBeNull|Um den angegebenen Vertrag mit DuplexChannelFactory zu verwenden, muss der Vertrag einen gültigen Rückrufvertrag enthalten. Verwenden Sie ChannelFactory anstelle von DuplexChannelFactory, wenn der Vertrag einen Rückrufvertrag aufweist.|  
|SFxCannotGetMetadataFromLocation|Der MetadataExchangeClient kann nur Metadaten von HTTP- und HTTPS-MetadataLocations abrufen. Er kann keine Metadaten von der angegebenen Position abrufen.|  
|SFxCannotHttpGetMetadataFromAddress|Der MetadataExchangeClient kann nur Metadaten von HTTP- oder HTTPS-Adressen abrufen, wenn MetadataExchangeClientMode-HttpGet verwendet wird. Er kann keine Metadaten von der angegebenen Position abrufen.|  
|SFxCannotImportAsParameters_Bare|Der Nachrichtenvertrag wird generiert, da der angegebene Vorgang weder in RPC noch in einem Dokument eingeschlossen ist.|  
|SFxCannotImportAsParameters_DifferentWrapperName|Der Nachrichtenvertrag wird generiert, da der Wrappername der angegebenen Nachricht nicht mit dem Standardwert übereinstimmt.|  
|SFxCannotImportAsParameters_DifferentWrapperName|Der Nachrichtenvertrag wird generiert, da der Wrappernamespace der angegebenen Nachricht nicht mit dem Standardwert übereinstimmt.|  
|SFxCannotImportAsParameters_ElementIsNotNillable|Der Nachrichtenvertrag wird generiert, da der angegebene Elementname aus dem angegebenen Namespace nicht als "nillable" (nullwertfähig) gekennzeichnet ist.|  
|SFxCannotImportAsParameters_HeadersAreUnsupported|Der Nachrichtenvertrag wird generiert, da die angegebene Nachricht Header aufweist.|  
|SFxCannotImportAsParameters_Message|Der Nachrichtenvertrag wird generiert, da der angegebene Vorgang eine nicht typisierte Nachricht als Argument oder Rückgabetyp aufweist.|  
|SFxCannotImportAsParameters_MessageHasProtectionLevel|Der Nachrichtenvertrag wird generiert, da die angegebene Nachricht Schutz erfordert.|  
|SFxCannotImportAsParameters_NamespaceMismatch|Der Nachrichtenvertrag wird generiert, da der angegebene Nachrichtenteilnamespace nicht mit dem Standardwert übereinstimmt.|  
|SFxCannotRequireBothSessionAndDatagram3|Der angegebene Vertrag gibt SessionMode.NotAllowed an, und der angegebene Vertrag gibt SessionMode.Required an. Ändern Sie einen der SessionMode-Werte, oder geben Sie eine andere Adresse oder einen anderen ListenURI für jeden Endpunkt an.|  
|SFxCannotSetExtensionsByIndex|Diese Sammlung unterstützt das Festlegen von Erweiterungen nach Index nicht. Verwenden Sie die InsertItem-Methode oder die RemoveItem-Methode.|  
|SFxChannelDispatcherDifferentHost0|Der ChannelDispatcher ist derzeit nicht an den bereitgestellten ServiceHost angefügt.|  
|SFxChannelDispatcherMultipleHost0|Der ChannelDispatcher kann nur einem ServiceHost hinzugefügt werden.|  
|SFxChannelDispatcherNoHost0|Der ChannelDispatcher kann nicht geöffnet werden, da er nicht an einen ServiceHost angefügt ist.|  
|SfxChannelFactoryDisposed|Diese ChannelFactory kann nicht geöffnet werden, da die ChannelFactory bereits verworfen wurde. Erstellen Sie die ChannelFactory erneut, bevor Sie sie verwenden.|  
|SFxChannelFactoryNoBinding|Die ChannelFactory kann nicht geöffnet werden, da keine Bindung mit dem Endpunkt verknüpft ist. Geben Sie eine Bindung mit dem Konstruktor oder mit der Endpunkteigenschaft an.|  
|SFxChannelTerminated0|Ein als IsTerminating gekennzeichneter Vorgang wurde für diesen Kanal bereits aufgerufen. Dies führt dazu, dass die Kanalverbindung beendet wird. Über diesen Kanal können keine weiteren Vorgänge aufgerufen werden. Erstellen Sie den Kanal erneut, um die Kommunikation fortzusetzen.|  
|SFxCloseTimedOut1|Der ServiceHost-Schließvorgang wurde nach dem angegebenen Element beendet. Möglicherweise wurde ein sitzungsbasierter Kanal vom Client nicht innerhalb der erforderlichen Zeit geschlossen. Die zulässige Zeit für diesen Vorgang ist möglicherweise Teil eines längeren Timeouts.|  
|SfxCloseTimedOutWaitingForDispatchToComplete|Timeout beim Schließen-Prozess beim Warten auf den Abschluss der Dienstverteilung.|  
|SFxCodeGenIsNotAssignableFrom|Das angegebene Element kann nicht zugewiesen werden.|  
|SFxConfigChannelConfigurationNotFound|Das Endpunktelement mit dem angegebenen Namen und dem angegebenen Vertrag im Konfigurationsabschnitt des ServiceModel-Clients kann nicht gefunden werden.|  
|SFxConflictingGlobalElement|Das XML-Element mit dem angegebenen Namen im angegebenen Namespace kann nicht auf den angegebenen Typ verweisen. Es verweist bereits auf einen anderen Typ. Verwenden Sie einen anderen Vorgangsnamen oder ein anderes MessageBodyAttribute, um einen anderen Namen für die Nachricht oder die Nachrichtenteile zu verwenden.|  
|SFxContractHasZeroInitiatingOperations|Ein Vertrag muss mindestens einen IsInitiating=true-Vorgang aufweisen.|  
|SFxContractHasZeroOperations|Ein Vertrag muss mindestens einen Vorgang aufweisen.|  
|SFxContractInheritanceRequiresInterfaces|Die Dienstklasse des angegebenen Typs definiert einen ServiceContract und erbt einen ServiceContract vom angegebenen Typ. Eine Vertragsvererbung kann nur zwischen Schnittstellentypen verwendet werden. Wenn eine Klasse mit ServiceContractAttribute gekennzeichnet ist, muss es sich um den einzigen Typ in der Hierarchie mit ServiceContractAttribute handeln.  Verschieben Sie das ServiceContractAttribute für den angegebenen Typ in eine separate Schnittstelle, die vom angegebenen Typ implementiert wird.|  
|SFxCreateDuplexChannel1|Der Rückrufvertrag des angegebenen Vertrags ist entweder nicht vorhanden oder definiert keine Vorgänge. Wenn es sich nicht um einen Duplexvertrag handelt, verwenden Sie ChannelFactory anstelle von DuplexChannelFactory.|  
|SFxCreateDuplexChannelNoCallback|Diese CreateChannel-Überladung kann nicht für diese Instanz von DuplexChannelFactory aufgerufen werden. Die DuplexChannelFactory wurde nicht mit einem InstanceContext initialisiert. Rufen Sie die CreateChannel-Überladung auf, die einen InstanceContext aufnimmt.|  
|SFxCreateDuplexChannelNoCallback1|Diese CreateChannel-Überladung kann nicht für diese Instanz von DuplexChannelFactory aufgerufen werden. Die DuplexChannelFactory wurde mit einem Typ initialisiert, und es wurde kein gültiger InstanceContext bereitgestellt. Rufen Sie die CreateChannel-Überladung auf, die einen InstanceContext aufnimmt.|  
|SFxCreateDuplexChannelNoCallbackUserObject|Diese CreateChannel-Überladung kann nicht für diese Instanz von DuplexChannelFactory aufgerufen werden. Der an DuplexChannelFactory übergebene InstanceContext enthält kein gültiges UserObject.|  
|SFxCreateNonDuplexChannel1|ChannelFactory unterstützt den angegebenen Vertrag nicht. ChannelFactory definiert einen Rückrufvertrag mit mindestens einem Vorgang. Verwenden Sie DuplexChannelFactory anstelle von ChannelFactory.|  
|SFxCustomBindingNeedsTransport1|In der CustomBinding für den ServiceEndpoint mit dem angegebenen Vertrag fehlt ein TransportBindingElement. Jede Bindung muss über mindestens ein Bindungselement verfügen, das von TransportBindingElement abgeleitet wird.|  
|SFxCustomBindingWithoutTransport|Das Schema kann für diese benutzerdefinierte Bindung nicht berechnet werden, da es kein TransportBindingElement aufweist. Jede Bindung muss über mindestens ein Bindungselement verfügen, das von TransportBindingElement abgeleitet wird.|  
|SFxDataContractSerializerDoesNotSupportBareArray|DataContractSerializer unterstützt die für das angegebene Element angegebene Auflistung nicht.|  
|SFxDictionaryIsEmpty|Der Vorgang kann nicht ausgeführt werden, da das Wörterbuch leer ist.|  
|SFxDocEncodedNotSupported|Fehler beim Reflektieren des angegebenen Elements. Document-Encoded wird nicht unterstützt. Ändern Sie "Use" in Literal oder "Style" in RPC.|  
|SFxDuplicateInitiatingActionAtSameVia|Dieser Dienst weist mehrere Endpunkte auf, die das angegebene Element abhören. Diese Endpunkte teilen die gleiche angegebene einleitende Aktion. Da der Verteiler den richtigen Endpunkt zum Verarbeiten der Nachricht nicht bestimmen könnte, werden Nachrichten mit dieser Aktion verworfen.|  
|SFXEndpointBehaviorUsedOnWrongSide|Das angegebene IEndpointBehavior kann nicht für den Server verwendet werden. Dieses Verhalten kann nur für Clients verwendet werden.|  
|SFxEndpointNoMatchingScheme|Die Basisadresse, die dem angegebenen Schema für den Endpunkt mit der angegebenen Bindung entspricht, kann nicht gefunden werden. Registrierte Basisadressenschemas wurden angegeben.|  
|SFxErrorCreatingMtomReader|Fehler beim Erstellen eines Readers für die Nachricht bezüglich des Optimierungsmechanismus zur Nachrichtenübertragung.|  
|SFxErrorDeserializingFault|Der Server hat einen ungültigen SOAP (Simple Object Access Protocol)-Fehler zurückgegeben. Weitere Details finden Sie unter "InnerException".“|  
|SFxErrorDeserializingHeader|Fehler beim Deserialisieren eines Headers in der angegebenen Nachricht. Weitere Informationen finden Sie in der InnerException.|  
|SFxErrorReflectingOnMethod3|Fehler beim Laden des angegebenen Attributs für die angegebene Methode im angegebenen Typ.  Weitere Details finden Sie unter "InnerException".“|  
|SFxErrorReflectingOnParameter4|Fehler beim Laden des angegebenen Attributs für den angegebenen Parameter der angegebenen Methode im angegebenen Typ. Weitere Details finden Sie unter "InnerException".“|  
|SFxErrorReflectingOnType2|Fehler beim Laden des angegebenen Attributs für den angegebenen Typ.  Weitere Details finden Sie unter "InnerException".“|  
|SFxErrorSerializingBody|Fehler beim Serialisieren des Texts der angegebenen Nachricht. Weitere Details finden Sie unter "InnerException".“|  
|SFxErrorSerializingHeader|Fehler beim Serialisieren eines Headers in der angegebenen Nachricht. Weitere Details finden Sie unter "InnerException".“|  
|SFxExpectedIMethodCallMessage|Interner Fehler. Die Nachricht muss eine gültige IMethodCallMessage sein.|  
|SFxExportMustHaveType|Der angegebene Teil im angegebenen Vorgang kann nicht exportiert werden, da kein gültiger CLR-Typ vorhanden ist.|  
|SFxHeaderNotUnderstood|Die Nachricht wurde nicht verarbeitet. Der angegebene Header des angegebenen Namespace konnte vom Empfänger dieser Nachricht nicht interpretiert werden. Dieser Fehler weist im Allgemeinen darauf hin, dass der Sender dieser Nachricht ein Kommunikationsprotokoll aktiviert hat, das der Empfänger nicht verarbeiten kann. Stellen Sie sicher, dass die Konfiguration der Bindung des Clients mit der Bindung des Diensts übereinstimmt.|  
|SFxHeadersAreNotSupportedInEncoded|Die angegebene Nachricht darf keine Header aufweisen, die im Remoteprozeduraufruf-Format verwendet werden sollen.|  
|SFxInconsistentWsdlOperationStyleInMessageParts|Alle Teile dieser Nachricht im angegebenen Vorgang müssen entweder einen Typ oder ein Element enthalten.|  
|SFxInconsistentWsdlOperationStyleInOperationMessages|Das angegebene Format, das von Nachrichten im angegebenen Vorgang geerbt wurde, stimmt nicht mit dem erwarteten Format überein, das mit Bindungen angegeben wurde.|  
|SFxInvalidCallbackIAsyncResult|IAsyncResult wird nicht bereitgestellt oder weist den falschen Typ auf.|  
|SFxInvalidMessageBody|Der OperationFormatter hat einen ungültigen Nachrichtentext gefunden. Der "Element"-Knotentyp mit dem angegebenen Namen und dem angegebenen Namespace wurde erwartet. Der angegebene Knotentyp mit dem angegebenen Namen und dem angegebenen Namespace wurde gefunden.|  
|SFxInvalidMessageBodyEmptyMessage|Der OperationFormatter konnte keine Informationen aus der Nachricht deserialisieren, da die Nachricht leer ist.|  
|SFxInvalidMessageBodyErrorDeserializingParameter|Fehler beim Versuch, den angegebenen Parameter zu deserialisieren. Weitere Informationen finden Sie in der InnerException.|  
|SFxInvalidMessageBodyErrorSerializingParameter|Fehler beim Versuch, den angegebenen Parameter zu serialisieren. Die InnerException-Nachricht wurde angegeben.  Weitere Details finden Sie unter "InnerException".“|  
|SFxInvalidMessageBodyUnexpectedNode|Beim Deserialisieren von Parametern wurde der angegebene unerwartete Knoten des angegebenen Namespaces gefunden.|  
|SFxInvalidMessageContractSignature|Der angegebene Vorgang weist entweder einen Parameter oder einen Rückgabetyp auf, der mit MessageContractAttribute attributiert ist. Um die Anforderungsnachricht mit einem MessageContract darzustellen, muss der Vorgang über einen einzelnen Parameter verfügen, der mit MessageContractAttribute attributiert ist. Um die Antwortnachricht mit einem MessageContract darzustellen, muss der Rückgabewert des Vorgangs einen Typ aufweisen, der mit MessageContractAttribute markiert ist. Der Vorgang kann über keinen 'out'-Parameter oder 'ref'-Parameter verfügen.|  
|SFxInvalidReplyAction|Die ausgehende Antwortnachricht für den Vorgang weist die angegebene Aktion auf, der Vertrag für den Vorgang gibt jedoch eine andere ReplyAction an. Die in der Nachricht angegebene Aktion muss mit der ReplyAction im Vertrag übereinstimmen, oder der Vertrag muss ReplyAction='*' angeben.|  
|SFxInvalidRequestAction|Die ausgehende Anforderungsnachricht für den Vorgang weist die angegebene Aktion auf, der Vertrag für den Vorgang gibt jedoch eine andere RequestAction an. Die in der Nachricht angegebene Aktion muss mit der RequestAction im Vertrag übereinstimmen, oder der Vertrag muss RequestAction='*' angeben.|  
|SFxInvalidStaticOverloadCalledForDuplexChannelFactory1|Die statische CreateChannel-Methode kann nicht mit dem angegebenen Vertrag verwendet werden, da der Vertrag einen Rückrufvertrag definiert. Verwenden Sie eine der statischen "aliatechannel"-über Ladungen für DuplexChannelFactory \<TChannel> .|  
|SFxInvalidStreamInRequest|Damit die Anforderung im angegebenen Vorgang einen Stream darstellen kann, muss der Vorgang einen Parameter vom Typ Stream aufweisen.|  
|SFxInvalidStreamInResponse|Damit die Antwort im angegebenen Vorgang einen Stream darstellen kann, muss der Vorgang einen Out-Parameter oder einen Rückgabewert vom Typ Stream aufweisen.|  
|SFxInvalidStreamInTypedMessage|Um Streams mit dem Programmiermodell für den Nachrichtenvertrag verwenden zu können, muss der angegebene Typ einen MessageBody-Member vom Typ Stream aufweisen.|  
|SFxInvalidUseOfPrimitiveOperationFormatter|An den PrimitiveOperationFormatter wurde ein nicht unterstützter Parameter oder ein nicht unterstützter Rückgabetyp übergeben.|  
|SFxMessageContractBaseTypeNotValid|Der angegebene Typ definiert einen MessageContract und wird von einem angegebenen Typ abgeleitet, der keinen MessageContract definiert. Alle Objekte in der angegebenen Vererbungshierarchie müssen einen MessageContract definieren.|  
|SFxMethodNotSupported1|Die angegebene Methode wird für dieses Objekt nicht unterstützt. Dies kann geschehen, wenn die Methode nicht mit dem OperationContractAttribute gekennzeichnet ist oder der Schnittstellentyp nicht mit dem ServiceContractAttribute gekennzeichnet ist.|  
|SFxMethodNotSupportedByType2|Der angegebene Dienstvertrag wird vom angegebenen ServiceHost-Implementierungstyp nicht implementiert.|  
|SFxMethodNotSupportedOnCallback1|Die angegebene Rückrufmethode wird nicht unterstützt. Dies kann geschehen, wenn die Methode nicht mit dem OperationContractAttribute gekennzeichnet ist oder wenn der Schnittstellentyp nicht das Ziel des ServiceContractAttribute-CallbackContracts darstellt.|  
|SFxMismatchedOperationParent|Eine DispatchOperation oder eine ClientOperation können nur der übergeordneten DispatchRuntime oder der übergeordneten ClientRuntime hinzugefügt werden.|  
|SFxNameCannotBeEmpty|Die Name-Eigenschaft kann keine leere Zeichenfolge sein.|  
|SfxNoTypeSpecifiedForParameter|Es wurde kein CLR-Typ für den Parameter angegeben, sodass kein Vorgang generiert werden kann.|  
|SFxOperationBehaviorAttributeOnlyOnServiceClass|OperationBehaviorAttribute kann nur an die Dienstklasse weitergegeben werden. Es kann nicht auf die ServiceContract-Schnittstelle angewendet werden. Die angegebene Methode für den angegebenen Typ verstößt gegen diese Regel.|  
|SFxOperationContractOnNonServiceContract|Die angegebene Methode ist mit dem OperationContractAttribute gekennzeichnet, der angegebene einschließende Typ ist jedoch nicht mit dem ServiceContractAttribute gekennzeichnet. Das OperationContractAttribute kann nur für Methoden in ServiceContractAttribute-Typen oder für deren CallbackContract-Typen verwendet werden.|  
|SFxParameterCountMismatch|Fehlende Übereinstimmung zwischen der Anzahl der bereitgestellten Argumente und der Anzahl der erwarteten Argumente. Insbesondere verfügt das angegebene Argument über die angegebene Anzahl von Elementen, während das erwartete Argument über die angegebene Anzahl von Elementen verfügt.|  
|SFxPartNameMustBeUniqueInRpc|Der angegebene Nachrichtenteilname ist kein eindeutiger Name in einer Remoteprozeduraufruf-Nachricht.|  
|SFxReplyActionMismatch3|Eine Antwortnachricht für den angegebenen Vorgang mit der angegebenen Aktion wurde empfangen. Der Clientcode erfordert jedoch die angegebene Aktion.|  
|SFxRequestReplyNone|Es wurde eine Nachricht mit einem ReplyTo- oder FaultTo-Header der WS-Adressierung empfangen, die an die Adresse "None" gerichtet ist. Diese Werte sind für Anforderung-Antwort-Vorgänge nicht gültig. Verwenden Sie einen unidirektionalen Vorgang, oder aktivieren Sie ManualAddressing, wenn Sie die ReplyTo- oder FaultTo-Werte von "None" unterstützen müssen.|  
|SFxRequestTimedOut1|Dieser Anforderungsvorgang hat keine Antwort innerhalb der konfigurierten Zeit erhalten. Die zulässige Zeit ist möglicherweise Teil eines längeren Timeouts. Möglicherweise wird der Vorgang noch vom Dienst verarbeitet, oder es konnte keine Antwortnachricht vom Dienst gesendet werden.|  
|SFxRequestTimedOut2|Der Anforderungsvorgang, der an die angegebene Position gesendet wurde, hat keine Antwort innerhalb der konfigurierten Zeit erhalten. Die zulässige Zeit ist möglicherweise Teil eines längeren Timeouts. Möglicherweise wird der Vorgang noch vom Dienst verarbeitet, oder es konnte keine Antwortnachricht vom Dienst gesendet werden.|  
|SFxSchemaDoesNotContainType|Das Schema mit dem angegebenen Zielnamespace enthält keinen Typ mit dem angegebenen Namen.|  
|SfxServiceContractAttributeNotFound|Der angegebene Vertragstyp ist mit ServiceContractAttribute nicht attributiert. Um einen gültigen Vertrag zu definieren, muss der angegebene Typ mit ServiceContractAttribute attributiert sein. Der Typ kann entweder eine Vertragsschnittstelle oder eine Dienstklasse sein.|  
|SFxServiceContractGeneratorConfigRequired|Zum Generieren von Konfigurationsinformationen mithilfe der GenerateServiceEndpoint-Methode muss die ServiceContractGenerator-Instanz mit einem gültigen Konfigurationsobjekt initialisiert worden sein.|  
|SFxServiceHostBaseCannotAddEndpointAfterOpen|Endpunkte können nicht hinzugefügt werden, wenn der ServiceHost einen der folgenden Status aufweist:<br /><br /> -Geöffnet<br />-Faulted<br />-Beendet<br />-Geschlossen|  
|SFxServiceHostBaseCannotAddEndpointWithoutDescription|Endpunkte können erst hinzugefügt werden, wenn die Description-Eigenschaft initialisiert wurde.|  
|SFxServiceMetadataBehaviorNoHttpBaseAddress|Die HttpGetEnabled-Eigenschaft von ServiceMetadataBehavior ist auf True festgelegt, und die HttpGetUrl-Eigenschaft ist eine relative Adresse, aber es ist keine HTTP-Basisadresse verfügbar. Stellen Sie entweder eine HTTP-Basisadresse bereit, oder legen Sie die HttpGetUrl auf eine absolute Adresse fest.|  
|SFxServiceMetadataBehaviorNoHttpsBaseAddress|Die HttpsGetEnabled-Eigenschaft von ServiceMetadataBehavior ist auf True festgelegt, und die HttpsGetUrl-Eigenschaft ist eine relative Adresse, aber es ist keine HTTPS-Basisadresse verfügbar. Stellen Sie entweder eine HTTPS-Basisadresse bereit, oder legen Sie die HttpsGetUrl auf eine absolute Adresse fest.|  
|SFxServiceMetadataBehaviorUrlMustBeHttpOrRelative|Die URL für das Verhalten muss ein relativer URI oder ein absoluter URI mit dem angegebenen Schema sein. Die angegebene Url ist ein absoluter URI mit dem angegebenen Schema.|  
|SFxStreamRequestMessageClosed|Die Nachricht mit dem Datenstrom wurde geschlossen. Auf Anforderungsstreams kann nach Rückgabe des Dienstvorgangs nicht mehr zugegriffen werden.|  
|SFxStreamResponseMessageClosed|Die Nachricht mit dem Datenstrom wurde geschlossen.|  
|SFxTerminateRequestProcessingException|Die Verarbeitung dieser Nachricht muss durch eine Erweiterung in der Vorgangspipeline beendet werden.|  
|SFxTerminatingOperationAlreadyCalled1|Dieser Kanal kann keine weiteren Nachrichten senden, da der IsTerminating-Vorgang aufgerufen wurde.|  
|SFxThrottleLimitMustBeGreaterThanZero0|Die Drosselungsgrenze muss größer als 0 (null) sein. Legen Sie den Wert auf Int32.MaxValue fest, um die Drosselungsgrenze zu deaktivieren.|  
|SFxTypedOrUntypedMessageCannotBeMixedWithVoidInRpc|Bei Verwendung des RPC-Encoded-Formats können die Nachrichtenvertragstypen oder der System.ServiceModel.Channels.Message-Typ nicht verwendet werden, wenn der Vorgang keine Parameter oder einen leeren Rückgabewert besitzt. Fügen Sie dem angegebenen Vorgang einen leeren Nachrichtenvertragstyp als Parameter oder als Rückgabetyp hinzu.|  
|SFxUserCodeThrewException|Der angegebene Benutzervorgang hat eine Ausnahme ausgelöst, die im Benutzercode nicht behandelt wird. Wenn dieses Problem wiederholt auftritt, kann dies auf einen Fehler in der Implementierung der angegebenen Methode hinweisen.|  
|SfxUseTypedMessageForCustomAttributes|Der angegebene Parameter kann dem Vorgangsparameter nicht zugeordnet werden, da zusätzliche Attribute erforderlich sind.|  
|SFxVersionMismatchInOperationContextAndMessage2|Der Nachricht können keine ausgehenden Header hinzugefügt werden, da MessageVersion in OperationContext.Current nicht mit der Headerversion der verarbeiteten Nachricht übereinstimmt.|  
|SFxWellKnownNonSingleton0|Um einen der ServiceHost-Konstruktoren zu verwenden, der eine Dienstinstanz annimmt, muss der InstanceContextMode des Diensts auf InstanceContextMode.Single festgelegt sein. Dies kann über das ServiceBehaviorAttribute konfiguriert werden. Andernfalls sollten Sie erwägen, die ServiceHost-Konstruktoren zu verwenden, die ein Typargument annehmen.|  
|SFxWrapperTypeHasMultipleNamespaces|Der Wrappertyp für die angegebene Nachricht kann nicht als Datenvertragstyp projiziert werden, da er mehrere Namespaces aufweist. Verwenden Sie den XmlSerializer.|  
|UriMustBeAbsolute|Der URI muss absolut sein.|

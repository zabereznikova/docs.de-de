---
title: ServiceDescription und WSDL-Verweis
ms.date: 03/30/2017
ms.assetid: eedc025d-abd9-46b1-bf3b-61d2d5c95fd6
ms.openlocfilehash: e70d653519c13d2f40fa2a579b674893e1b7ab02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33507355"
---
# <a name="servicedescription-and-wsdl-reference"></a>ServiceDescription und WSDL-Verweis
In diesem Thema wird beschrieben, wie Windows Communication Foundation (WCF) Web Services Description Language (WSDL)-Dokumente in und aus zugeordnet <xref:System.ServiceModel.Description.ServiceDescription> Instanzen.  
  
## <a name="how-servicedescription-maps-to-wsdl-11"></a>Zuordnen von ServiceDescription zu WSDL 1.1  
 Verwenden Sie WCF zum Exportieren von WSDL-Dokumente aus einem <xref:System.ServiceModel.Description.ServiceDescription> Instanz für Ihren Dienst. WSDL-Dokumente werden automatisch für den Dienst generiert, wenn Metadatenendpunkte veröffentlicht werden.  
  
 Mithilfe des <xref:System.ServiceModel.Description.ServiceEndpoint>-Typs können auch <xref:System.ServiceModel.Description.ContractDescription>-Instanzen <xref:System.ServiceModel.Channels.Binding>-Instanzen und `WsdlImporter`-Instanzen aus WSDL-Dokumenten importiert werden.  
  
 WCF, exportierten WSDL-Dokumente importieren alle XML-Schemadefinitionen aus externen XML-Schema-Dokumenten verwendet. Ein separates XML-Schemadokument wird für jeden Zielnamespace exportiert, der von den Datentypen im Dienst verwendet wird. Ebenso wird ein separates WSDL-Dokument für jeden Zielnamespace exportiert, der von den Dienstverträgen verwendet wird.  
  
### <a name="servicedescription"></a>ServiceDescription  
 Einem <xref:System.ServiceModel.Description.ServiceDescription>-Element wird eine `wsdl:service`-Instanz zugeordnet. Eine <xref:System.ServiceModel.Description.ServiceDescription>-Instanz enthält eine Auflistung von <xref:System.ServiceModel.Description.ServiceEndpoint>-Instanzen, die jeweils einzelnen `wsdl:port`-Elementen zugeordnet werden.  
  
|Eigenschaften|WSDL-Zuordnung|  
|----------------|------------------|  
|`Name`|Die `wsdl:service` /@name Wert für den Dienst.|  
|`Namespace`|Der targetNamespace für die `wsdl:service`-Definition des Diensts.|  
|`Endpoints`|Die `wsdl:port`-Definitionen für den Dienst.|  
  
### <a name="serviceendpoint"></a>ServiceEndpoint  
 Einem <xref:System.ServiceModel.Description.ServiceEndpoint>-Element wird eine `wsdl:port`-Instanz zugeordnet. Eine <xref:System.ServiceModel.Description.ServiceEndpoint>-Instanz enthält eine Adresse, eine Bindung und einen Vertrag.  
  
 Endpunktverhalten, die die <xref:System.ServiceModel.Description.IWsdlExportExtension>-Schnittstelle implementieren, können das `wsdl:port`-Element für den Endpunkt ändern, an den sie angehängt sind.  
  
|Eigenschaften|WSDL-Zuordnung|  
|----------------|------------------|  
|`Name`|Die `wsdl:port` /@name Wert für den Endpunkt und die `wsdl:binding` /@name Wert für die endpunktbindung.|  
|`Address`|Die Adresse für die `wsdl:port`-Definition des Endpunkts.<br /><br /> Der Transport für den Endpunkt bestimmt das Format der Adresse. Z. B. für Transporte WCF unterstützt möglich es eine SOAP-Adresse oder einen Endpunktverweis.|  
|`Binding`|Die `wsdl:binding`-Definition für den Endpunkt.<br /><br /> Im Gegensatz zu `wsdl:binding` Definitionen, die Bindungen in WCF an keinen Vertrag gebunden.|  
|`Contract`|Die `wsdl:portType`-Definition für den Endpunkt.|  
|`Behaviors`|Endpunktverhalten, die die <xref:System.ServiceModel.Description.IWsdlExportExtension>-Schnittstelle implementieren, können `wsdl:port` für den Endpunkt ändern.|  
  
### <a name="bindings"></a>Bindungen  
 Die Bindungsinstanz für eine `ServiceEndpoint`-Instanz wird einer `wsdl:binding`-Definition zugeordnet. Im Gegensatz zu `wsdl:binding` Definitionen, die einen bestimmten zugeordnet werden müssen `wsdl:portType` Definition der WCF-Bindungen werden vertragsunabhängig.  
  
 Eine Bindung besteht aus einer Auflistung von Bindungselementen. Jedes Element beschreibt einige Aspekte der Kommunikation zwischen dem Endpunkt und den Clients. Darüber hinaus besitzt eine Bindung eine <xref:System.ServiceModel.Channels.MessageVersion>, die die <xref:System.ServiceModel.EnvelopeVersion> und die <xref:System.ServiceModel.Channels.AddressingVersion> für den Endpunkt angibt.  
  
|Eigenschaften|WSDL-Zuordnung|  
|----------------|------------------|  
|`Name`|Wird im Standardnamen eines Endpunkts verwendet, bei dem es sich um den Bindungsnamen handelt, an den der Vertragsname durch einen Unterstrich abgetrennt angefügt ist.|  
|`Namespace`|`targetNamespace` für die `wsdl:binding`-Definition.<br /><br /> Ist eine Richtlinie an den WSDL-Anschluss angehängt, wird der importierte Bindungsnamespace dem `targetNamespace` für die `wsdl:port`-Definition zugeordnet.|  
|`BindingElementCollection` entsprechend der Rückgabe durch die `CreateBindingElements`()-Methode.|Verschiedene domänenspezifische Erweiterungen der `wsdl:binding`-Definition, in der Regel Richtlinienassertionen.|  
|`MessageVersion`|`EnvelopeVersion` und `AddressingVersion` für den Endpunkt.<br /><br /> Bei Angabe von `MessageVersion.None` enthält die WSDL-Bindung keine SOAP-Bindung, und der WSDL-Anschluss weist keinen WS-Adressierungsinhalt auf. Diese Einstellung wird in der Regel für Plain Old XML (POX)-Endpunkte verwendet.|  
  
#### <a name="bindingelements"></a>BindingElements  
 Die Bindungselemente für eine Endpunktbindung werden verschiedenen WSDL-Erweiterungen in `wsdl:binding` zugeordnet, beispielsweise Richtlinienassertionen.  
  
 Das <xref:System.ServiceModel.Channels.TransportBindingElement> für die Bindung bestimmt den für Transporte verwendeten Uniform Resource Identifier (URI) für eine SOAP-Bindung.  
  
#### <a name="addressingversion"></a>AddressingVersion  
 Die `AddressingVersion` einer Bindung wird der Version der in `wsd:port` verwendeten Adressierung zugeordnet. WCF unterstützt SOAP 1.1- und SOAP 1.2-Adressen und WS-Adressierung 08/2004 und WS-Adressierung 1.0 Endpunktverweise.  
  
#### <a name="envelopeversion"></a>EnvelopeVersion  
 Die `EnvelopeVersion` einer Bindung wird der der in `wsdl:binding` verwendeten SOAP-Version zugeordnet. WCF unterstützt SOAP 1.1- und SOAP 1.2-Bindungen.  
  
### <a name="contracts"></a>Verträge  
 Die <xref:System.ServiceModel.Description.ContractDescription>-Instanz für eine `ServiceEndpoint`-Instanz wird `wsdl:portType` zugeordnet. Eine `ContractDescription`-Instanz beschreibt alle Vorgänge für einen angegebenen Vertrag.  
  
|Eigenschaften|WSDL-Zuordnung|  
|----------------|------------------|  
|`Name`|Die `wsdl:portType` /@name Wert für den Vertrag.|  
|`Namespace`|Der targetNamespace für die `wsdl:portType`-Definition.|  
|`SessionMode`|Die `wsdl:portType` /@msc:usingSession Wert für den Vertrag. Dieses Attribut ist ein WCF-Erweiterung für WSDL 1.1.|  
|`Operations`|Die `wsdl:operation`-Definitionen für den Vertrag.|  
  
### <a name="operations"></a>Vorgänge  
 Ein <xref:System.ServiceModel.Description.OperationDescription> Instanz ordnet eine `wsdl:portType` / `wsdl:operation`. `OperationDescription` beinhaltet eine Auflistung von `MessageDescription`-Instanzen, die die Nachrichten für den Vorgang beschreiben.  
  
 Zwei Vorgangsverhalten besitzen einen großen Einfluss auf die Zuordnung von `OperationDescription` zu einem WSDL-Dokument: `DataContractSerializerOperationBehavior` und `XmlSerializerOperationBehavior`.  
  
|Eigenschaften|WSDL-Zuordnung|  
|----------------|------------------|  
|`Name`|Die `wsdl:portType` / `wsdl:operation` /@name Wert für den Vorgang.|  
|`ProtectionLevel`|Schutzassertionen in der Sicherheitsrichtlinie, die an die `wsdl:binding/wsdl:operation`-Nachrichten für diesen Vorgang angehängt ist.|  
|`IsInitiating`|Die `wsdl:portType` / `wsdl:operation` /@msc:isInitiating Wert für den Vorgang. Dieses Attribut ist ein WCF-Erweiterung für WSDL 1.1.|  
|`IsTerminating`|Die `wsdl:portType` / `wsdl:operation` /@msc:isTerminating Wert für den Vorgang. Dieses Attribut ist ein WCF-Erweiterung für WSDL 1.1.|  
|`Messages`|Die `wsdl:portType` / `wsdl:operation` / `wsdl:input` und `wsdl:portType` / `wsdl:operation` / `wsdl:output` Nachrichten für den Vorgang.|  
|`Faults`|Die `wsdl:portType` / `wsdl:operation` / `wsdl:fault` Definitionen für den Vorgang.|  
|`Behaviors`|`DataContractSerializerOperationBehavior` und `XmlSerializerOperationBehavior` dienen dem Umgang mit der Vorgangsbindung und den Vorgangsnachrichten.|  
  
#### <a name="the-datacontractserializeroperationbehavior"></a>DataContractSerializerOperationBehavior  
 Das `DataContractSerializerOperationBehavior` für einen Vorgang ist eine `IWsdlExportExtension`-Implementierung, die die WSDL-Nachrichten und die Bindung für diesen Vorgang exportiert. Die XML-Schematypen werden mithilfe von `XsdDataContractExporter` exportiert. `DataContractSerializerOperationBehavior` bestimmt auch die Verwendung, das Format sowie das Schemaexport- und -importprogramm, die für diesen Vorgang zu verwenden sind.  
  
|Eigenschaften|WSDL-Zuordnung|  
|----------------|------------------|  
|`DataContractFormatAttribute`|Die `Style` -Eigenschaft für dieses Attribut wird der `wsdl:binding` / `wsdl:operation` / `soap:operation` /@style Wert für den Vorgang.<br /><br /> `DataContractSerializerOperationBehavior` unterstützt nur die literale Verwendung der Schematypen in WSDL.|  
  
#### <a name="the-xmlserializeroperationbehavior"></a>XmlSerializerOperationBehavior  
 Das `XmlSerializerOperationBehavior` für einen Vorgang ist eine `IWsdlExportExtension`-Implementierung, die die WSDL-Nachrichten und die Bindung für diesen Vorgang exportiert. Die XML-Schematypen werden mithilfe von `XmlSchemaExporter` exportiert. `XmlSerializerOperationBehavior` bestimmt auch die Verwendung, das Format sowie das Schemaexport- und -importprogramm, die für diesen Vorgang zu verwenden sind.  
  
|Eigenschaften|WSDL-Zuordnung|  
|----------------|------------------|  
|`XmlSerializerFormatAttribute`|Die `Style` -Eigenschaft für dieses Attribut wird der `wsdl:binding` / `wsdl:operation` / `soap:operation` /@style Wert für den Vorgang.<br /><br /> Die `Use` -Eigenschaft für dieses Attribut wird der `wsdl:binding` / `wsdl:operation` / `soap:operation`/ */@use Werte für alle Nachrichten in den Vorgang.|  
  
### <a name="messages"></a>Mitteilungen  
 Ein `MessageDescription` Instanz ordnet eine `wsdl:message` , verweist eine `wsdl:portType` / `wsdl:operation` / `wsdl:input` oder eine `wsdl:portType` / `wsdl:operation` / `wsdl:output`Nachricht in einem Vorgang. `MessageDescription` besitzt einen Text und Header.  
  
|Eigenschaften|WSDL-Zuordnung|  
|----------------|------------------|  
|`Action`|Die SOAP- oder WS-Adressierungsaktion für die Nachricht.<br /><br /> Beachten Sie, dass Vorgänge, die die Aktionszeichenfolge "*" verwenden, nicht in WSDL dargestellt werden.|  
|`Direction`|`MessageDirection.Input` wird `wsdl:input` zugeordnet.<br /><br /> `MessageDirection.Output` wird `wsdl:output` zugeordnet.|  
|`ProtectionLevel`|Schutzassertionen in der Sicherheitsrichtlinie, die an die `wsdl:message`-Definition für diese Nachricht angehängt sind.|  
|`Body`|Der Text der Nachricht.|  
|`Headers`|Die Header für die Nachricht.|  
|`ContractDescription.Name`, `OperationContract.Name`|Beim Export zum Ableiten der `wsdl:message` /@name Wert.|  
  
#### <a name="message-body"></a>Nachrichtentext  
 Ein `MessageBodyDescription` Instanz ordnet die `wsdl:message` / `wsdl:part` Definitionen für den Textteil einer Nachricht. Der Nachrichtentext wird möglicherweise umgebrochen oder ist leer.  
  
|Eigenschaften|WSDL-Zuordnung|  
|----------------|------------------|  
|`WrapperName`|Wenn das Format nicht RPC, wird die `WrapperName` Maps an den Elementnamen verweist die `wsdl:message` / `wsdl:part` mit @name auf "Parameters" festgelegt.|  
|`WrapperNamespace`|Wenn das Format nicht RPC, wird die `WrapperNamespace` ordnet dem Elementnamespace für die `wsdl:message` / `wsdl:part` mit @name auf "Parameters" festgelegt.|  
|`Parts`|Die nachrichtenbezogenen Teile dieses Nachrichtentexts.|  
|`ReturnValue`|Das untergeordnete Element des Wrapperelements, sofern ein Wrapperelement (Dokument mit Umbruch oder RPC-Format), besteht der erste `wsdl:message` / `wsdl:part` in der Nachricht.|  
  
#### <a name="message-parts"></a>Nachrichtenteile  
 Ein `MessagePartDescription` Instanz ordnet eine `wsdl:message` / `wsdl:part` und XML-Schematyp oder Elements, das der Nachrichtenteil verweist.  
  
|Eigenschaften|WSDL-Zuordnung|  
|----------------|------------------|  
|`Name`|Die `wsd:message` / `wsdl:part` /@name Wert für den Nachrichtenteil und der Name des Elements, das das der Nachrichtenteil verweist.|  
|`Namespace`|Der Namespace des Elements, auf das der Nachrichtenteil verweist.|  
|`Index`|Der Index des der `wsdl:message` / `wsdl:part` für die Nachricht.|  
|`ProtectionLevel`|Schutzassertionen in der Sicherheitsrichtlinie, die an die `wsdl:message`-Definition für diesen Nachrichtenteil angehängt sind. Die Richtlinie wird parametrisiert, um auf den bestimmten Nachrichtenteil zu verweisen.|  
|`MessageType`|Der XML-Schematyp des Elements, auf das der Nachrichtenteil verweist.|  
  
#### <a name="message-headers"></a>Nachrichtenheader  
 Eine `MessageHeaderDescription`-Instanz ist ein Nachrichtenteil, der auch einer `soap:header`-Bindung für den Nachrichtenteil zugeordnet wird.  
  
### <a name="faults"></a>Fehler  
 Ein `FaultDescription` Instanz ordnet eine `wsdl:portType` / `wsdl:operation` / `wsdl:fault` Definition und die zugehörigen `wsdl:message` Definition. `wsdl:message` wird demselben Zielnamespace wie der zugewiesene WSDL-Anschlusstyp hinzugefügt. `wsdl:message` besitzt einen einzelnen Nachrichtenteil mit der Bezeichnung "detail", der auf das XML-Schemaelement verweist, das dem `DefaultType`-Eigenschaftswert für die `FaultDescription`-Instanz entspricht.  
  
|Eigenschaften|WSDL-Zuordnung|  
|----------------|------------------|  
|`Name`|Die `wsdl:portType` / `wsdl:operation` / `wsdl:fault` /@name Wert für den Fehler.|  
|`Namespace`|Der Namespace des XML-Schemaelements, auf das der Nachrichtenteil mit den Fehlerdetails verweist.|  
|`Action`|Die SOAP- oder WS-Adressierungsaktion für den Fehler.|  
|`ProtectionLevel`|Schutzassertionen in der Sicherheitsrichtlinie, die an die `wsdl:message`-Definition für diesen Fehler angehängt sind.|  
|`DetailType`|Der XML-Schematyp des Elements, auf das der Nachrichtenteil mit den Details verweist.|  
|`Name, ContractDescription.Name, OperationDescription.Name,`|Verwendet zum Ableiten der `wsdl:message` /@name Wert für die Fehlermeldung.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Description>

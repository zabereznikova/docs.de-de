---
title: "ServiceDescription und WSDL-Verweis | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eedc025d-abd9-46b1-bf3b-61d2d5c95fd6
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# ServiceDescription und WSDL-Verweis
In diesem Thema wird beschrieben, wie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web Services Description Language \(WSDL\)\-Dokumente <xref:System.ServiceModel.Description.ServiceDescription>\-Instanzen zuordnet bzw. die Dokumente von diesen Instanzen zuordnet.  
  
## Zuordnen von ServiceDescription zu WSDL 1.1  
 Sie können [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwenden, um WSDL\-Dokumente von einer <xref:System.ServiceModel.Description.ServiceDescription>\-Instanz für den Dienst zu exportieren.  WSDL\-Dokumente werden automatisch für den Dienst generiert, wenn Metadatenendpunkte veröffentlicht werden.  
  
 Mithilfe des `WsdlImporter`\-Typs können auch <xref:System.ServiceModel.Description.ServiceEndpoint>\-Instanzen <xref:System.ServiceModel.Description.ContractDescription>\-Instanzen und <xref:System.ServiceModel.Channels.Binding>\-Instanzen aus WSDL\-Dokumenten importiert werden.  
  
 Die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] exportierten WSDL\-Dokumente importieren alle verwendeten XML\-Schemadefinitionen aus externen XML\-Schemadokumenten.  Ein separates XML\-Schemadokument wird für jeden Zielnamespace exportiert, der von den Datentypen im Dienst verwendet wird.  Ebenso wird ein separates WSDL\-Dokument für jeden Zielnamespace exportiert, der von den Dienstverträgen verwendet wird.  
  
### ServiceDescription  
 Einem `wsdl:service`\-Element wird eine <xref:System.ServiceModel.Description.ServiceDescription>\-Instanz zugeordnet.  Eine <xref:System.ServiceModel.Description.ServiceDescription>\-Instanz enthält eine Auflistung von <xref:System.ServiceModel.Description.ServiceEndpoint>\-Instanzen, die jeweils einzelnen `wsdl:port`\-Elementen zugeordnet werden.  
  
|Eigenschaften|WSDL\-Zuordnung|  
|-------------------|---------------------|  
|`Name`|Der `wsdl:service`\/@name\-Wert für den Dienst.|  
|`Namespace`|Der targetNamespace für die `wsdl:service`\-Definition des Diensts.|  
|`Endpoints`|Die `wsdl:port`\-Definitionen für den Dienst.|  
  
### ServiceEndpoint  
 Einem `wsdl:port`\-Element wird eine <xref:System.ServiceModel.Description.ServiceEndpoint>\-Instanz zugeordnet.  Eine <xref:System.ServiceModel.Description.ServiceEndpoint>\-Instanz enthält eine Adresse, eine Bindung und einen Vertrag.  
  
 Endpunktverhalten, die die <xref:System.ServiceModel.Description.IWsdlExportExtension>\-Schnittstelle implementieren, können das `wsdl:port`\-Element für den Endpunkt ändern, an den sie angehängt sind.  
  
|Eigenschaften|WSDL\-Zuordnung|  
|-------------------|---------------------|  
|`Name`|Der `wsdl:port`\/@name\-Wert für den Endpunkt und den `wsdl:binding`\/@name\-Wert für die Endpunktbindung.|  
|`Address`|Die Adresse für die `wsdl:port`\-Definition des Endpunkts.<br /><br /> Der Transport für den Endpunkt bestimmt das Format der Adresse.  Für von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützte Transporte kann es sich dabei zum Beispiel um eine SOAP\-Adresse oder einen Endpunktverweis handeln.|  
|`Binding`|Die `wsdl:binding`\-Definition für den Endpunkt.<br /><br /> Im Gegensatz zu `wsdl:binding`\-Definitionen werden Bindungen in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] an keinen Vertrag gebunden.|  
|`Contract`|Die `wsdl:portType`\-Definition für den Endpunkt.|  
|`Behaviors`|Endpunktverhalten, die die <xref:System.ServiceModel.Description.IWsdlExportExtension>\-Schnittstelle implementieren, können `wsdl:port` für den Endpunkt ändern.|  
  
### Bindungen  
 Die Bindungsinstanz für eine `ServiceEndpoint`\-Instanz wird einer `wsdl:binding`\-Definition zugeordnet.  Im Gegensatz zu `wsdl:binding`\-Definitionen, die einer bestimmten `wsdl:portType`\-Definition zugewiesen werden müssen, sind [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Bindungen vertragsunabhängig.  
  
 Eine Bindung besteht aus einer Auflistung von Bindungselementen.  Jedes Element beschreibt einige Aspekte der Kommunikation zwischen dem Endpunkt und den Clients.  Darüber hinaus besitzt eine Bindung eine <xref:System.ServiceModel.Channels.MessageVersion>, die die <xref:System.ServiceModel.EnvelopeVersion> und die <xref:System.ServiceModel.Channels.AddressingVersion> für den Endpunkt angibt.  
  
|Eigenschaften|WSDL\-Zuordnung|  
|-------------------|---------------------|  
|`Name`|Wird im Standardnamen eines Endpunkts verwendet, bei dem es sich um den Bindungsnamen handelt, an den der Vertragsname durch einen Unterstrich abgetrennt angefügt ist.|  
|`Namespace`|`targetNamespace` für die `wsdl:binding`\-Definition.<br /><br /> Ist eine Richtlinie an den WSDL\-Anschluss angehängt, wird der importierte Bindungsnamespace dem `targetNamespace` für die `wsdl:port`\-Definition zugeordnet.|  
|`BindingElementCollection` entsprechend der Rückgabe durch die `CreateBindingElements`\(\)\-Methode.|Verschiedene domänenspezifische Erweiterungen der `wsdl:binding`\-Definition, in der Regel Richtlinienassertionen.|  
|`MessageVersion`|`EnvelopeVersion` und `AddressingVersion` für den Endpunkt.<br /><br /> Bei Angabe von `MessageVersion.None` enthält die WSDL\-Bindung keine SOAP\-Bindung, und der WSDL\-Anschluss weist keinen WS\-Adressierungsinhalt auf.  Diese Einstellung wird in der Regel für Plain Old XML \(POX\)\-Endpunkte verwendet.|  
  
#### BindingElements  
 Die Bindungselemente für eine Endpunktbindung werden verschiedenen WSDL\-Erweiterungen in `wsdl:binding` zugeordnet, beispielsweise Richtlinienassertionen.  
  
 Das <xref:System.ServiceModel.Channels.TransportBindingElement> für die Bindung bestimmt den für Transporte verwendeten Uniform Resource Identifier \(URI\) für eine SOAP\-Bindung.  
  
#### AddressingVersion  
 Die `AddressingVersion` einer Bindung wird der Version der in `wsd:port` verwendeten Adressierung zugeordnet.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt SOAP 1.1\- und SOAP 1.2\-Adressen sowie Endpunktverweise für WS\-Adressierung 08\/2004 und WS\-Adressierung 1.0.  
  
#### EnvelopeVersion  
 Die `EnvelopeVersion` einer Bindung wird der der in `wsdl:binding` verwendeten SOAP\-Version zugeordnet.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt SOAP 1.1\- und SOAP 1.2\-Bindungen.  
  
### Verträge  
 Die <xref:System.ServiceModel.Description.ContractDescription>\-Instanz für eine `ServiceEndpoint`\-Instanz wird `wsdl:portType` zugeordnet.  Eine `ContractDescription`\-Instanz beschreibt alle Vorgänge für einen angegebenen Vertrag.  
  
|Eigenschaften|WSDL\-Zuordnung|  
|-------------------|---------------------|  
|`Name`|Der `wsdl:portType`\/@name\-Wert für den Vertrag.|  
|`Namespace`|Der targetNamespace für die `wsdl:portType`\-Definition.|  
|`SessionMode`|Der `wsdl:portType`\/@msc:usingSession\-Wert für den Vertrag.  Dieses Attribut ist eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Erweiterung für WSDL 1.1.|  
|`Operations`|Die `wsdl:operation`\-Definitionen für den Vertrag.|  
  
### Vorgänge  
 Eine <xref:System.ServiceModel.Description.OperationDescription>\-Instanz wird `wsdl:portType`\/`wsdl:operation` zugeordnet.  `OperationDescription` beinhaltet eine Auflistung von `MessageDescription`\-Instanzen, die die Nachrichten für den Vorgang beschreiben.  
  
 Zwei Vorgangsverhalten besitzen einen großen Einfluss auf die Zuordnung von `OperationDescription` zu einem WSDL\-Dokument: `DataContractSerializerOperationBehavior` und `XmlSerializerOperationBehavior`.  
  
|Eigenschaften|WSDL\-Zuordnung|  
|-------------------|---------------------|  
|`Name`|Der `wsdl:portType`\/`wsdl:operation`\/@name\-Wert für den Vorgang.|  
|`ProtectionLevel`|Schutzassertionen in der Sicherheitsrichtlinie, die an die `wsdl:binding/wsdl:operation`\-Nachrichten für diesen Vorgang angehängt ist.|  
|`IsInitiating`|Der `wsdl:portType`\/`wsdl:operation`\/@msc:isInitiating\-Wert für den Vorgang.  Dieses Attribut ist eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Erweiterung für WSDL 1.1.|  
|`IsTerminating`|Der `wsdl:portType`\/`wsdl:operation`\/@ msc:isTerminating\-Wert für den Vorgang.  Dieses Attribut ist eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Erweiterung für WSDL 1.1.|  
|`Messages`|Die `wsdl:portType`\/`wsdl:operation`\/`wsdl:input`\-Nachrichten und die `wsdl:portType`\/`wsdl:operation`\/`wsdl:output`\-Nachrichten für den Vorgang.|  
|`Faults`|Die `wsdl:portType`\/`wsdl:operation`\/`wsdl:fault`\-Definitionen für den Vorgang.|  
|`Behaviors`|`DataContractSerializerOperationBehavior` und `XmlSerializerOperationBehavior` dienen dem Umgang mit der Vorgangsbindung und den Vorgangsnachrichten.|  
  
#### DataContractSerializerOperationBehavior  
 Das `DataContractSerializerOperationBehavior` für einen Vorgang ist eine `IWsdlExportExtension`\-Implementierung, die die WSDL\-Nachrichten und die Bindung für diesen Vorgang exportiert.  Die XML\-Schematypen werden mithilfe von `XsdDataContractExporter` exportiert.  `DataContractSerializerOperationBehavior` bestimmt auch die Verwendung, das Format sowie das Schemaexport\- und \-importprogramm, die für diesen Vorgang zu verwenden sind.  
  
|Eigenschaften|WSDL\-Zuordnung|  
|-------------------|---------------------|  
|`DataContractFormatAttribute`|Die `Style`\-Eigenschaft für dieses Attribut wird dem `wsdl:binding`\/`wsdl:operation`\/`soap:operation`\/@style\-Wert für den Vorgang zugeordnet.<br /><br /> `DataContractSerializerOperationBehavior` unterstützt nur die literale Verwendung der Schematypen in WSDL.|  
  
#### XmlSerializerOperationBehavior  
 Das `XmlSerializerOperationBehavior` für einen Vorgang ist eine `IWsdlExportExtension`\-Implementierung, die die WSDL\-Nachrichten und die Bindung für diesen Vorgang exportiert.  Die XML\-Schematypen werden mithilfe von `XmlSchemaExporter` exportiert.  `XmlSerializerOperationBehavior` bestimmt auch die Verwendung, das Format sowie das Schemaexport\- und \-importprogramm, die für diesen Vorgang zu verwenden sind.  
  
|Eigenschaften|WSDL\-Zuordnung|  
|-------------------|---------------------|  
|`XmlSerializerFormatAttribute`|Die `Style`\-Eigenschaft für dieses Attribut wird dem `wsdl:binding`\/`wsdl:operation`\/`soap:operation`\/@style\-Wert für den Vorgang zugeordnet.<br /><br /> Die `Use`\-Eigenschaft für dieses Attribut wird den `wsdl:binding`\/`wsdl:operation`\/`soap:operation`\/\*\/@use\-Werten für alle Nachrichten im Vorgang zugeordnet.|  
  
### Meldungen  
 Eine `MessageDescription`\-Instanz wird einer `wsdl:message` zugeordnet, auf die von einer `wsdl:portType`\/`wsdl:operation`\/`wsdl:input`\-Nachricht oder einer `wsdl:portType`\/`wsdl:operation`\/`wsdl:output`\-Nachricht in einem Vorgang verwiesen wird.  `MessageDescription` besitzt einen Text und Header.  
  
|Eigenschaften|WSDL\-Zuordnung|  
|-------------------|---------------------|  
|`Action`|Die SOAP\- oder WS\-Adressierungsaktion für die Nachricht.<br /><br /> Beachten Sie, dass Vorgänge, die die Aktionszeichenfolge "\*" verwenden, nicht in WSDL dargestellt werden.|  
|`Direction`|`MessageDirection.Input` wird `wsdl:input` zugeordnet.<br /><br /> `MessageDirection.Output` wird `wsdl:output` zugeordnet.|  
|`ProtectionLevel`|Schutzassertionen in der Sicherheitsrichtlinie, die an die `wsdl:message`\-Definition für diese Nachricht angehängt sind.|  
|`Body`|Der Text der Nachricht.|  
|`Headers`|Die Header für die Nachricht.|  
|`ContractDescription.Name`, `OperationContract.Name`|Wird beim Export zum Ableiten des `wsdl:message`\/@name\-Werts verwendet.|  
  
#### Nachrichtentext  
 Eine `MessageBodyDescription`\-Instanz wird den `wsdl:message`\/`wsdl:part`\-Definitionen für den Text einer Nachricht zugeordnet.  Der Nachrichtentext wird möglicherweise umgebrochen oder ist leer.  
  
|Eigenschaften|WSDL\-Zuordnung|  
|-------------------|---------------------|  
|`WrapperName`|Ist das Format nicht RPC, wird `WrapperName` dem Elementnamen zugeordnet, auf den von `wsdl:message`\/`wsdl:part` verwiesen wird. Dabei ist @name auf "parameters" festgelegt.|  
|`WrapperNamespace`|Ist das Format nicht RPC, wird `WrapperNamespace` dem Elementnamespace für `wsdl:message`\/`wsdl:part` zugeordnet, wobei @name auf "parameters" festgelegt ist.|  
|`Parts`|Die nachrichtenbezogenen Teile dieses Nachrichtentexts.|  
|`ReturnValue`|Das untergeordnete Element des Wrapperelements, sofern ein Wrapperelement vorhanden ist \(Dokument mit Umbruch oder RPC\-Format\), andernfalls der erste `wsdl:message`\/`wsdl:part` in der Nachricht.|  
  
#### Nachrichtenteile  
 Eine `MessagePartDescription`\-Instanz wird `wsdl:message`\/`wsdl:part` und dem XML\-Schematyp oder \-element zugeordnet, auf den bzw. das der Nachrichtenteil verweist.  
  
|Eigenschaften|WSDL\-Zuordnung|  
|-------------------|---------------------|  
|`Name`|Der `wsd:message`\/`wsdl:part`\/@name\-Wert für den Nachrichtenteil und der Name des Elements, auf das der Nachrichtenteil verweist.|  
|`Namespace`|Der Namespace des Elements, auf das der Nachrichtenteil verweist.|  
|`Index`|Der Index des `wsdl:message`\/`wsdl:part` für die Nachricht.|  
|`ProtectionLevel`|Schutzassertionen in der Sicherheitsrichtlinie, die an die `wsdl:message`\-Definition für diesen Nachrichtenteil angehängt sind.  Die Richtlinie wird parametrisiert, um auf den bestimmten Nachrichtenteil zu verweisen.|  
|`MessageType`|Der XML\-Schematyp des Elements, auf das der Nachrichtenteil verweist.|  
  
#### Nachrichtenheader  
 Eine `MessageHeaderDescription`\-Instanz ist ein Nachrichtenteil, der auch einer `soap:header`\-Bindung für den Nachrichtenteil zugeordnet wird.  
  
### Fehler  
 Eine `FaultDescription`\-Instanz wird einer `wsdl:portType`\/`wsdl:operation`\/`wsdl:fault`\-Definition und der entsprechenden `wsdl:message`\-Definition zugeordnet.  `wsdl:message` wird demselben Zielnamespace wie der zugewiesene WSDL\-Anschlusstyp hinzugefügt.  `wsdl:message` besitzt einen einzelnen Nachrichtenteil mit der Bezeichnung "detail", der auf das XML\-Schemaelement verweist, das dem `DefaultType`\-Eigenschaftswert für die `FaultDescription`\-Instanz entspricht.  
  
|Eigenschaften|WSDL\-Zuordnung|  
|-------------------|---------------------|  
|`Name`|Der `wsdl:portType`\/`wsdl:operation`\/`wsdl:fault`\/@name\-Wert für den Fehler.|  
|`Namespace`|Der Namespace des XML\-Schemaelements, auf das der Nachrichtenteil mit den Fehlerdetails verweist.|  
|`Action`|Die SOAP\- oder WS\-Adressierungsaktion für den Fehler.|  
|`ProtectionLevel`|Schutzassertionen in der Sicherheitsrichtlinie, die an die `wsdl:message`\-Definition für diesen Fehler angehängt sind.|  
|`DetailType`|Der XML\-Schematyp des Elements, auf das der Nachrichtenteil mit den Details verweist.|  
|`Name, ContractDescription.Name, OperationDescription.Name,`|Wird zum Ableiten des `wsdl:message`\/@name\-Werts für die Fehlermeldung verwendet.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Description>
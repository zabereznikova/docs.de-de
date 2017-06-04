---
title: "Exportieren und Importieren von Metadaten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Metadaten [WCF], Importieren und Exportieren"
ms.assetid: 614a75bb-e0b0-4c95-b6d8-02cb5e5ddb38
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# Exportieren und Importieren von Metadaten
In [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] wird unter dem Metadatenexport der Vorgang verstanden, mit dem die Dienstendpunkte beschrieben und in eine parallele, standardisierte Darstellung projiziert werden, aus der die Clients entnehmen können, wie der Dienst zu nutzen ist.Beim Import von Dienstmetadaten werden <xref:System.ServiceModel.Description.ServiceEndpoint>\-Instanzen oder Teile davon aus Dienstmetadaten generiert.  
  
## Exportieren von Metadaten  
 Mit einer Implementierung der abstrakten <xref:System.ServiceModel.Description.MetadataExporter>\-Klasse können Sie Metadaten aus <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=fullName>\-Instanzen exportieren.Der <xref:System.ServiceModel.Description.WsdlExporter>\-Typ stellt die Implementierung der abstrakten <xref:System.ServiceModel.Description.MetadataExporter>\-Klasse in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dar.  
  
 Der <xref:System.ServiceModel.Description.WsdlExporter?displayProperty=fullName>\-Typ generiert WSDL \(Web Services Description Language\)\-Metadaten mit angefügten Richtlinienausdrücken, die in einer <xref:System.ServiceModel.Description.MetadataSet>\-Instanz gekapselt sind.Sie können eine <xref:System.ServiceModel.Description.WsdlExporter?displayProperty=fullName>\-Instanz verwenden, um Metadaten für <xref:System.ServiceModel.Description.ContractDescription>\-Objekte und <xref:System.ServiceModel.Description.ServiceEndpoint>\-Objekte iterativ zu exportieren.Sie können auch eine Auflistung von <xref:System.ServiceModel.Description.ServiceEndpoint>\-Objekten exportieren und sie einem bestimmten Dienstnamen zuordnen.  
  
> [!NOTE]
>  `WsdlExporter` kann nur zum Exportieren von Metadaten aus `ContractDescription`\-Instanzen verwendet werden, die Common Language Runtime \(CLR\)\-Typinformationen enthalten, wie z. B. eine `ContractDescription`\-Instanz, die mit der `ContractDescription.GetContract`\-Methode oder als Teil der `ServiceDescription` für eine `ServiceHost`\-Instanz erstellt wurde.Sie können `WsdlExporter` nicht zum Exportieren von Metadaten aus `ContractDescription`\-Instanzen verwenden, die aus Dienstmetadaten stammen oder ohne Typinformationen erstellt wurden.  
  
## Importieren von Metadaten  
  
### Importieren von WSDL\-Dokumenten  
 Mit einer Implementierung der abstrakten <xref:System.ServiceModel.Description.MetadataImporter>\-Klasse können Sie Metadaten von Diensten in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] importieren.Der <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=fullName>\-Typ stellt die Implementierung der abstrakten <xref:System.ServiceModel.Description.MetadataImporter>\-Klasse in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dar.Der <xref:System.ServiceModel.Description.WsdlImporter>\-Typ importiert WSDL\-Metadaten mit angefügten Richtlinien, die in einem <xref:System.ServiceModel.Description.MetadataSet>\-Objekt zusammengefasst sind.  
  
 Beim <xref:System.ServiceModel.Description.WsdlImporter>\-Typ können Sie steuern, wie die Metadaten importiert werden.Sie können alle Endpunkte, alle Bindungen oder alle Verträge importieren.Sie können alle Endpunkte importieren, die einem bestimmten WSDL\-Dienst, einer bestimmten Bindung oder einem bestimmten Anschlusstyp zugeordnet sind.Zudem können Sie den Endpunkt für einen bestimmten WSDL\-Anschluss, die Bindung für eine bestimmte WSDL\-Bindung oder den Vertag für einen bestimmten WSDL\-Anschlusstyp importieren.  
  
 Der <xref:System.ServiceModel.Description.WsdlImporter>\-Typ macht die <xref:System.ServiceModel.Description.MetadataImporter.KnownContracts%2A>\-Eigenschaft verfügbar, die es Ihnen ermöglicht, eine Gruppe von Verträgen anzugeben, die nicht importiert werden müssen.Der <xref:System.ServiceModel.Description.WsdlImporter>\-Typ verwendet die in der <xref:System.ServiceModel.Description.MetadataImporter.KnownContracts%2A>\-Eigenschaft angegebenen Verträge, statt aus den Metadaten Verträge zu importieren, die über den gleichen qualifizierten Namen verfügen.  
  
### Importieren von Richtlinien  
 Der <xref:System.ServiceModel.Description.WsdlImporter>\-Typ sammelt die Richtlinienausdrücke, die den Nachrichten\-, Vorgangs\- und Endpunktrichtliniensubjekts angehängt sind, und importiert die Richtlinienausdrücke dann mithilfe der <xref:System.ServiceModel.Description.IPolicyImportExtension>\-Implementierungen aus der <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A>\-Auflistung.  
  
 Das Richtlinienimportprogramm verarbeitet automatisch Richtlinienverweise auf Richtlinienausdrücke im gleichen WSDL\-Dokument und wird durch das `wsu:Id`\-Attribut oder das `xml:id`\-Attribut angegeben.Das Richtlinienimportprogramm schützt Anwendungen vor zirkulären Verweisen, indem es die Größe von Richtlinienausdrücken auf 4096 Knoten beschränkt, wobei ein Knoten eines der folgenden Elemente sein kann: `wsp:Policy`, `wsp:All`, `wsp:ExactlyOne`, `wsp:policyReference`.  
  
 Das Richtlinienimportprogramm normalisiert Richtlinienausdrücke auch automatisch.Geschachtelte Richtlinienausdrücke und das `wsp:Optional`\-Attribut werden nicht normalisiert.Die normalisierte Verarbeitung wird auf höchsten 4096 Schritte beschränkt, wobei jeder Schritt eine Richtlinienassertion oder ein untergeordnetes Element eines `wsp:ExactlyOne`\-Elements ergibt.  
  
 Der <xref:System.ServiceModel.Description.WsdlImporter>\-Typ probiert bis zu 32 Kombinationen von Richtlinienalternativen aus, die verschiedenen WSDL\-Richtliniensubjekten angehängt sind.Wenn keine Kombination sauber importiert werden kann, wird die erste Kombination zur Erstellung einer teilweise benutzerdefinierten Bindung verwendet.  
  
## Fehlerbehandlung  
 Sowohl der <xref:System.ServiceModel.Description.MetadataExporter>\-Typ als auch der <xref:System.ServiceModel.Description.MetadataImporter>\-Typ machen eine `Errors`\-Eigenschaft verfügbar, die eine Auflistung von Meldungen für Fehler und Warnungen enthalten kann, die während des Export\- bzw. Importprozesses auftreten können und die in der Implementierung von Dienstprogrammen verwendet werden können.  
  
 Der <xref:System.ServiceModel.Description.WsdlImporter>\-Typ löst im Allgemeinen eine Ausnahme für jede Ausnahme aus, die während des Importvorgangs abgefangen wurde, und fügt der `Errors`\-Eigenschaft einen entsprechenden Fehler hinzu.Da die Methoden <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>, <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>, <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> und <xref:System.ServiceModel.Description.WsdlImporter.ImportEndpoints%2A> diese Ausnahmen dagegen nicht auslösen, müssen Sie die `Errors`\-Eigenschaft überprüfen, um zu ermitteln, ob während des Aufrufs dieser Methoden Probleme aufgetreten sind.  
  
 Der <xref:System.ServiceModel.Description.WsdlExporter> Typ löst entsprechende Ausnahmen für alle während des Exportprozesses abgefangenen Ausnahmen aus.Diese Ausnahmen werden nicht als Fehler in der `Errors`\-Eigenschaft aufgezeichnet.Sobald der <xref:System.ServiceModel.Description.WsdlExporter>\-Typ eine Ausnahme auslöst, hat er in einen Fehlerstatus und kann nicht wiederverwendet werden.Der <xref:System.ServiceModel.Description.WsdlExporter>\-Typ fügt seiner `Errors`\-Eigenschaft Warnungen hinzu, wenn ein Vorgang nicht exportiert werden kann, weil er Platzhalteraktionen verwendet, und wenn doppelte Bindungsnamen auftreten.  
  
## In diesem Abschnitt  
 [Vorgehensweise: Importieren von Metadaten in Dienstendpunkte](../../../../docs/framework/wcf/feature-details/how-to-import-metadata-into-service-endpoints.md)  
 Beschreibt, wie heruntergeladene Metadaten in Beschreibungsobjekte importiert werden.  
  
 [Vorgehensweise: Exportieren von Metadaten aus Dienstendpunkten](../../../../docs/framework/wcf/feature-details/how-to-export-metadata-from-service-endpoints.md)  
 Beschreibt, wie Beschreibungsobjekte in Metadaten importiert werden.  
  
 [ServiceDescription und WSDL\-Verweis](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md)  
 Beschreibt die Zuordnung zwischen Beschreibungsobjekten und WSDL.  
  
 [Vorgehensweise: Verwenden von "Svcutil.exe" zum Exportieren von Metadaten aus kompiliertem Dienstcode](../../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-export-metadata-from-compiled-service-code.md)  
 Beschreibt die Verwendung von Svcutil.exe zum Export von Metadaten für Dienste, Verträge und Datentypen in kompilierten Assemblys.  
  
 [Datenvertrags\-Schemareferenz](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)  
 Beschreibt die von <xref:System.Runtime.Serialization.DataContractSerializer> zur Beschreibung der Common Language Runtime \(CLR\)\-Typen für die XML\-Serialisierung verwendete Teilmenge des XML\-Schemas \(XSD\).  
  
## Referenz  
 <xref:System.ServiceModel.Description.WsdlExporter>  
  
 <xref:System.ServiceModel.Description.WsdlImporter>  
  
## Siehe auch  
 [Exportieren von benutzerdefinierten Metadaten für eine WCF\-Erweiterung](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md)   
 [Importieren von benutzerdefinierten Metadaten für eine WCF\-Erweiterung](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)
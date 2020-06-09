---
title: Exportieren und Importieren von Metadaten
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WCF], exporting and importing
ms.assetid: 614a75bb-e0b0-4c95-b6d8-02cb5e5ddb38
ms.openlocfilehash: f07a1a10529aa1615bb00a0f3faeca9cb249aa64
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595530"
---
# <a name="exporting-and-importing-metadata"></a>Exportieren und Importieren von Metadaten
In Windows Communication Foundation (WCF) handelt es sich beim Exportieren von Metadaten um das Beschreiben von Dienst Endpunkten und das projizieren in eine parallele, standardisierte Darstellung, die Clients verwenden können, um zu verstehen, wie der Dienst verwendet wird. Beim Import von Dienstmetadaten werden <xref:System.ServiceModel.Description.ServiceEndpoint>-Instanzen oder Teile davon aus Dienstmetadaten generiert.  
  
## <a name="exporting-metadata"></a>Exportieren von Metadaten  
 Mit einer Implementierung der abstrakten <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>-Klasse können Sie Metadaten aus <xref:System.ServiceModel.Description.MetadataExporter>-Instanzen exportieren. Der <xref:System.ServiceModel.Description.WsdlExporter> Typ ist die Implementierung der <xref:System.ServiceModel.Description.MetadataExporter> abstrakten Klasse, die in WCF enthalten ist.  
  
 Der <xref:System.ServiceModel.Description.WsdlExporter?displayProperty=nameWithType>-Typ generiert WSDL (Web Services Description Language)-Metadaten mit angefügten Richtlinienausdrücken, die in einer <xref:System.ServiceModel.Description.MetadataSet>-Instanz gekapselt sind. Sie können eine <xref:System.ServiceModel.Description.WsdlExporter?displayProperty=nameWithType>-Instanz verwenden, um Metadaten für <xref:System.ServiceModel.Description.ContractDescription>-Objekte und <xref:System.ServiceModel.Description.ServiceEndpoint>-Objekte iterativ zu exportieren. Sie können auch eine Auflistung von <xref:System.ServiceModel.Description.ServiceEndpoint>-Objekten exportieren und sie einem bestimmten Dienstnamen zuordnen.  
  
> [!NOTE]
> `WsdlExporter` kann nur zum Exportieren von Metadaten aus `ContractDescription`-Instanzen verwendet werden, die Common Language Runtime (CLR)-Typinformationen enthalten, wie z.&#160;B. eine `ContractDescription`-Instanz, die mit der `ContractDescription.GetContract`-Methode oder als Teil der `ServiceDescription` für eine `ServiceHost`-Instanz erstellt wurde. Sie können `WsdlExporter` nicht zum Exportieren von Metadaten aus `ContractDescription`-Instanzen verwenden, die aus Dienstmetadaten stammen oder ohne Typinformationen erstellt wurden.  
  
## <a name="importing-metadata"></a>Importieren von Metadaten  
  
### <a name="importing-wsdl-documents"></a>Importieren von WSDL-Dokumenten  
 Um Dienst Metadaten in WCF zu importieren, verwenden Sie eine Implementierung der <xref:System.ServiceModel.Description.MetadataImporter> abstrakten-Klasse. Der <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> Typ ist die Implementierung der <xref:System.ServiceModel.Description.MetadataImporter> abstrakten Klasse, die in WCF enthalten ist. Der <xref:System.ServiceModel.Description.WsdlImporter>-Typ importiert WSDL-Metadaten mit angefügten Richtlinien, die in einem <xref:System.ServiceModel.Description.MetadataSet>-Objekt zusammengefasst sind.  
  
 Beim <xref:System.ServiceModel.Description.WsdlImporter>-Typ können Sie steuern, wie die Metadaten importiert werden. Sie können alle Endpunkte, alle Bindungen oder alle Verträge importieren. Sie können alle Endpunkte importieren, die einem bestimmten WSDL-Dienst, einer bestimmten Bindung oder einem bestimmten Anschlusstyp zugeordnet sind. Zudem können Sie den Endpunkt für einen bestimmten WSDL-Anschluss, die Bindung für eine bestimmte WSDL-Bindung oder den Vertag für einen bestimmten WSDL-Anschlusstyp importieren.  
  
 Der <xref:System.ServiceModel.Description.WsdlImporter>-Typ macht die <xref:System.ServiceModel.Description.MetadataImporter.KnownContracts%2A>-Eigenschaft verfügbar, die es Ihnen ermöglicht, eine Gruppe von Verträgen anzugeben, die nicht importiert werden müssen. Der <xref:System.ServiceModel.Description.WsdlImporter>-Typ verwendet die in der <xref:System.ServiceModel.Description.MetadataImporter.KnownContracts%2A>-Eigenschaft angegebenen Verträge, statt aus den Metadaten Verträge zu importieren, die über den gleichen qualifizierten Namen verfügen.  
  
### <a name="importing-policies"></a>Importieren von Richtlinien  
 Der <xref:System.ServiceModel.Description.WsdlImporter>-Typ sammelt die Richtlinienausdrücke, die den Nachrichten-, Vorgangs- und Endpunktrichtliniensubjekts angehängt sind, und importiert die Richtlinienausdrücke dann mithilfe der <xref:System.ServiceModel.Description.IPolicyImportExtension>-Implementierungen aus der <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A>-Auflistung.  
  
 Das Richtlinienimportprogramm verarbeitet automatisch Richtlinienverweise auf Richtlinienausdrücke im gleichen WSDL-Dokument und wird durch das `wsu:Id`-Attribut oder das `xml:id`-Attribut angegeben. Das Richtlinienimportprogramm schützt Anwendungen vor zirkulären Verweisen, indem es die Größe von Richtlinienausdrücken auf 4096&#160;Knoten beschränkt, wobei ein Knoten eines der folgenden Elemente sein kann: `wsp:Policy`, `wsp:All`, `wsp:ExactlyOne`, `wsp:policyReference`.  
  
 Das Richtlinienimportprogramm normalisiert Richtlinienausdrücke auch automatisch. Geschachtelte Richtlinienausdrücke und das `wsp:Optional`-Attribut werden nicht normalisiert. Die normalisierte Verarbeitung wird auf höchsten 4096&#160;Schritte beschränkt, wobei jeder Schritt eine Richtlinienassertion oder ein untergeordnetes Element eines `wsp:ExactlyOne`-Elements ergibt.  
  
 Der <xref:System.ServiceModel.Description.WsdlImporter>-Typ probiert bis zu 32&#160;Kombinationen von Richtlinienalternativen aus, die verschiedenen WSDL-Richtliniensubjekten angehängt sind. Wenn keine Kombination sauber importiert werden kann, wird die erste Kombination zur Erstellung einer teilweise benutzerdefinierten Bindung verwendet.  
  
## <a name="error-handling"></a>Fehlerbehandlung  
 Sowohl der <xref:System.ServiceModel.Description.MetadataExporter>-Typ als auch der <xref:System.ServiceModel.Description.MetadataImporter>-Typ machen eine `Errors`-Eigenschaft verfügbar, die eine Auflistung von Meldungen für Fehler und Warnungen enthalten kann, die während des Export- bzw. Importprozesses auftreten können und die in der Implementierung von Dienstprogrammen verwendet werden können.  
  
 Der <xref:System.ServiceModel.Description.WsdlImporter>-Typ löst im Allgemeinen eine Ausnahme für jede Ausnahme aus, die während des Importvorgangs abgefangen wurde, und fügt der `Errors`-Eigenschaft einen entsprechenden Fehler hinzu. Da die Methoden <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>, <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>, <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> und <xref:System.ServiceModel.Description.WsdlImporter.ImportEndpoints%2A> diese Ausnahmen dagegen nicht auslösen, müssen Sie die `Errors`-Eigenschaft überprüfen, um zu ermitteln, ob während des Aufrufs dieser Methoden Probleme aufgetreten sind.  
  
 Der <xref:System.ServiceModel.Description.WsdlExporter> Typ löst entsprechende Ausnahmen für alle während des Exportprozesses abgefangenen Ausnahmen aus. Diese Ausnahmen werden nicht als Fehler in der `Errors`-Eigenschaft aufgezeichnet. Sobald der <xref:System.ServiceModel.Description.WsdlExporter>-Typ eine Ausnahme auslöst, hat er in einen Fehlerstatus und kann nicht wiederverwendet werden. Der <xref:System.ServiceModel.Description.WsdlExporter>-Typ fügt seiner `Errors`-Eigenschaft Warnungen hinzu, wenn ein Vorgang nicht exportiert werden kann, weil er Platzhalteraktionen verwendet, und wenn doppelte Bindungsnamen auftreten.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Importieren von Metadaten in Dienstendpunkte](how-to-import-metadata-into-service-endpoints.md)  
 Beschreibt, wie heruntergeladene Metadaten in Beschreibungsobjekte importiert werden.  
  
 [Vorgehensweise: Exportieren von Metadaten aus Dienstendpunkten](how-to-export-metadata-from-service-endpoints.md)  
 Beschreibt, wie Beschreibungsobjekte in Metadaten importiert werden.  
  
 [ServiceDescription und WSDL-Verweis](servicedescription-and-wsdl-reference.md)  
 Beschreibt die Zuordnung zwischen Beschreibungsobjekten und WSDL.  
  
 [Vorgehensweise: Verwenden von „Svcutil.exe“ zum Exportieren von Metadaten aus kompiliertem Dienstcode](how-to-use-svcutil-exe-to-export-metadata-from-compiled-service-code.md)  
 Beschreibt die Verwendung von Svcutil.exe zum Export von Metadaten für Dienste, Verträge und Datentypen in kompilierten Assemblys.  
  
 [Datenvertrags-Schemareferenz](data-contract-schema-reference.md)  
 Beschreibt die von <xref:System.Runtime.Serialization.DataContractSerializer> zur Beschreibung der Common Language Runtime (CLR)-Typen für die XML-Serialisierung verwendete Teilmenge des XML-Schemas (XSD).  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel.Description.WsdlExporter>  
  
 <xref:System.ServiceModel.Description.WsdlImporter>  
  
## <a name="see-also"></a>Siehe auch

- [Exportieren von benutzerdefinierten Metadaten für eine WCF-Erweiterung](../extending/exporting-custom-metadata-for-a-wcf-extension.md)
- [Importieren von benutzerdefinierten Metadaten für eine WCF-Erweiterung](../extending/importing-custom-metadata-for-a-wcf-extension.md)

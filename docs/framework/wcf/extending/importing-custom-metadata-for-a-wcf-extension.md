---
title: "Importieren von benutzerdefinierten Metadaten f&#252;r eine WCF-Erweiterung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 78beb28f-408a-4c75-9c3c-caefe9595b1a
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Importieren von benutzerdefinierten Metadaten f&#252;r eine WCF-Erweiterung
In [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] wird beim Importieren von Metadaten eine abstrakte Darstellung eines Diensts oder seiner Komponenten aus dessen Metadaten generiert.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kann beispielsweise Instanzen von <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Channels.Binding> oder <xref:System.ServiceModel.Description.ContractDescription> aus einem WSDL\-Dokument für einen Dienst importieren.Mit einer Implementierung der abstrakten <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=fullName>\-Klasse können Sie Metadaten von Diensten in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] importieren.Die Unterstützung für das Importieren von Metadatenformaten, die die Importlogik der WS\-Richtlinie in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützen, wird durch Typen implementiert, die von der <xref:System.ServiceModel.Description.MetadataImporter>\-Klasse abgeleitet sind.  
  
 Benutzerdefinierte Metadaten bestehen aus XML\-Elementen, die die Metadatenimportmechanismen des Systems nicht verarbeiten können.Dazu gehören i. d. R. auch benutzerdefinierte WSDL\-Erweiterungen sowie benutzerdefinierte Richtlinienassertionen.  
  
 In diesem Abschnitt wird beschrieben, wie benutzerdefinierte WSDL\-Erweiterungen und benutzerdefinierte Richtlinienassertionen importiert werden.Dabei wird der eigentliche Importvorgang nur am Rande erläutert.Weitere Informationen über die Verwendung von Typen, die Metadaten – egal, ob benutzerdefiniert oder systemeigen – exportieren und importieren, finden Sie unter [Exportieren und Importieren von Metadaten](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md).  
  
## Übersicht  
 Der <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=fullName>\-Typ stellt die Implementierung der abstrakten <xref:System.ServiceModel.Description.MetadataImporter>\-Klasse in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dar.Der <xref:System.ServiceModel.Description.WsdlImporter>\-Typ importiert WSDL\-Metadaten mit angefügten Richtlinien, die in einem <xref:System.ServiceModel.Description.MetadataSet?displayProperty=fullName>\-Objekt zusammengefasst sind.Richtlinienassertionen und WSDL\-Erweiterungen, die von den Standardimportern nicht erkannt werden, werden an eine registrierte benutzerdefinierte Richtlinie oder an einen registrierten WSDL\-Importer übergeben, um sie zu importieren.Normalerweise werden Importer zur Unterstützung von benutzerdefinierten Bindungselementen oder zur Änderung des importierten Vertrags implementiert.  
  
 Dieser Abschnitt beschreibt:  
  
1.  Implementierung und Verwendung der <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=fullName>\-Schnittstelle, die die WSDL\-Daten für benutzerdefinierte Importer verfügbar macht, bevor Beschreibungen und Code generiert werden.Mit dieser Schnittstelle können Sie die Beschreibungen und die Codekompilierungen mit einem vorhandenen Satz von Metadaten untersuchen oder ändern.  
  
2.  Implementierung und Verwendung der <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=fullName>\-Schnittstelle, die die Richtlinienassertionen für Importer verfügbar macht, bevor Beschreibungsobjekte generiert werden.Mit dieser Schnittstelle können Sie die Bindung oder den Vertrag anhand der heruntergeladenen Richtlinien untersuchen oder ändern.  
  
 Weitere Informationen über das Exportieren von benutzerdefinierter WSDL und benutzerdefinierten Richtlinienassertionen finden Sie unter [Exportieren von benutzerdefinierten Metadaten für eine WCF\-Erweiterung](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md).  
  
## Importieren von benutzerdefinierten WSDL\-Erweiterungen  
 Implementieren Sie die <xref:System.ServiceModel.Description.IWsdlImportExtension>\-Schnittstelle, und fügen Sie diese Implementierung der <xref:System.ServiceModel.Description.WsdlImporter.WsdlImportExtensions%2A>\-Eigenschaft hinzu, um eine Unterstützung für das Importieren von WSDL\-Erweiterungen hinzuzufügen.Der <xref:System.ServiceModel.Description.WsdlImporter> kann auch Implementierungen der <xref:System.ServiceModel.Description.IWsdlImportExtension>\-Schnittstelle laden, die in der Konfigurationsdatei der Anwendung registriert sind.Einige WSDL\-Importer sind standardmäßig registriert, und die Reihenfolge der registrierten WSDL\-Importer ist von Bedeutung.  
  
 Wenn ein benutzerdefinierter WSDL\-Importer geladen und vom <xref:System.ServiceModel.Description.WsdlImporter> verwendet wird, wird zunächst die <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%2A>\-Methode aufgerufen, um eine Änderung der Metadaten vor dem Import zu ermöglichen.Anschließend werden die Verträge importiert, und die <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%2A>\-Methode wird aufgerufen, um eine Änderung der aus den Metadaten importierten Verträge zu ermöglichen.Abschließend wird die <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%2A>\-Methode aufgerufen, um die Änderung der importierten Endpunkte zu ermöglichen.  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Importieren von benutzerdefinierter WSDL](../../../../docs/framework/wcf/extending/how-to-import-custom-wsdl.md).  
  
### Importieren von benutzerdefinierten Richtlinienassertionen  
 Die Verarbeitung verschiedener Richtlinienassertionen, die an WSDL\-Dokumente angefügt sind, wird automatisch vom <xref:System.ServiceModel.Description.WsdlImporter>\-Typ und dem [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) behandelt.Diese Tools erfassen, normalisieren, und führen Richtlinienausdrücke zusammen, die an WSDL\-Bindungen und WSDL\-Anschlüsse angefügt sind.  
  
 Implementieren Sie die <xref:System.ServiceModel.Description.IPolicyImportExtension>\-Schnittstelle, und fügen Sie diese Implementierung der <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A>\-Eigenschaft hinzu, um eine Unterstützung für das Importieren von benutzerdefinierten Richtlinienassertionen hinzuzufügen.Der <xref:System.ServiceModel.Description.MetadataImporter> kann auch Implementierungen der <xref:System.ServiceModel.Description.IPolicyImportExtension>\-Schnittstelle laden, die in der Konfigurationsdatei der Anwendung registriert sind.Einige Richtlinienimporter sind standardmäßig registriert, und die Reihenfolge der registrierten Richtlinienimporter ist von Bedeutung.  
  
 Die <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=fullName>\-Methode wird vom Metadatensystem wiederholt für alle registrierten Richtlinienimporterweiterungen aufgerufen. Dies geschieht für alle Kombinationen von Richtlinienalternativen, die an eine Nachricht, einen Vorgang oder an das Richtliniensubjekt eines Endpunkts angefügt sind.Beim Importieren eines WSDL\-Anschlusses werden die an den Anschluss angefügten Richtlinien sowie die entsprechenden WSDL\-Bindungen vor einem Aufruf in die Richtlinienimporterweiterungen zusammengeführt.Die Richtlinienalternativen werden durch einen <xref:System.ServiceModel.Description.PolicyConversionContext> als <xref:System.ServiceModel.Description.PolicyAssertionCollection>\-Objekte verfügbar gemacht.Jede <xref:System.ServiceModel.Description.PolicyAssertionCollection> ist eine Auflistung von Richtlinienassertionen, die durch <xref:System.Xml.XmlElement>\-Objekte dargestellt wird.  
  
 Die <xref:System.ServiceModel.Description.PolicyConversionContext.Contract%2A>\-Eigenschaft und die <xref:System.ServiceModel.Description.PolicyConversionContext.BindingElements%2A>\-Eigenschaft des <xref:System.ServiceModel.Description.PolicyConversionContext>\-Objekts machen das <xref:System.ServiceModel.Description.ContractDescription>\-Objekt und das <xref:System.ServiceModel.Channels.BindingElement>\-Objekt verfügbar, die aus der WSDL importiert wurden.Richtlinienassertionen werden von Richtlinienimporterweiterungen verarbeitet, indem Instanzen eines bestimmten Richtlinienassertionstyps gesucht und entsprechende Änderungen am <xref:System.ServiceModel.Description.ContractDescription>\-Objekt oder an <xref:System.ServiceModel.Channels.BindingElement>\-Objekten vorgenommen und die Richtlinienassertionen anschließend aus der entsprechenden <xref:System.ServiceModel.Description.PolicyAssertionCollection>\-Instanz entfernt werden.  
  
 Das `wsp:Optional`\-Attribut sowie geschachtelte Richtlinienausdrücke werden nicht normalisiert, sodass diese Richtlinienkonstrukte von Richtlinienimporterweiterungen behandelt werden müssen.Richtlinienimporterweiterungen können außerdem mehrmals mit dem gleichen <xref:System.ServiceModel.Description.ContractDescription>\- und <xref:System.ServiceModel.Channels.BindingElement>\-Objekt aufgerufen werden, sodass Richtlinienimporterweiterungen diesem Verhalten gegenüber robust sein sollten.  
  
> [!IMPORTANT]
>  Ungültige oder fehlerhafte Metadaten können an den Importer übergeben werden.Stellen Sie sicher, dass benutzerdefinierte Importer gegenüber allen Arten von XML robust sind.  
  
## Siehe auch  
 [Vorgehensweise: Importieren von benutzerdefinierter WSDL](../../../../docs/framework/wcf/extending/how-to-import-custom-wsdl.md)   
 [Vorgehensweise: Importieren von benutzerdefinierten Richtlinienassertionen](../../../../docs/framework/wcf/extending/how-to-import-custom-policy-assertions.md)   
 [Vorgehensweise: Schreiben einer Erweiterung für den ServiceContractGenerator](../../../../docs/framework/wcf/extending/how-to-write-an-extension-for-the-servicecontractgenerator.md)
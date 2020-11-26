---
title: Exportieren von benutzerdefinierten Metadaten für eine WCF-Erweiterung
ms.date: 03/30/2017
ms.assetid: 53c93882-f8ba-4192-965b-787b5e3f09c0
ms.openlocfilehash: 1aad43eb59a92df9376577ba0108661a0cb9cd87
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249331"
---
# <a name="exporting-custom-metadata-for-a-wcf-extension"></a>Exportieren von benutzerdefinierten Metadaten für eine WCF-Erweiterung

In Windows Communication Foundation (WCF) ist der Metadatenexport der Prozess der Beschreibung von Dienst Endpunkten und der Projektion in eine parallele, standardisierte Darstellung, die Clients verwenden können, um die Verwendung des Diensts zu verstehen. Benutzerdefinierte Metadaten bestehen aus XML-Elementen, die die vom System bereitgestellten Metadaten-Exporteure nicht exportieren können. Normalerweise gehören hierzu benutzerdefinierte Elemente für benutzerdefinierte Verhalten und Bindungselemente und Richtlinienassertionen über die Fähigkeiten und Anforderungen von Bindungen und Verträgen.  
  
 Dieser Abschnitt beschreibt den Export von benutzerdefinierten WSDL- oder Richtlinienassertionen und konzentriert sich nicht auf den Exportprozess selbst. Weitere Informationen zur Verwendung der Typen, die Metadaten exportieren und importieren, unabhängig davon, ob die Metadaten Benutzer definiert oder System konstruiert sind, finden Sie unter [exportieren und Importieren von Metadaten](../feature-details/exporting-and-importing-metadata.md).  
  
## <a name="overview"></a>Übersicht  

 Wenn Metadaten mithilfe von veröffentlicht <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> werden, <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType> wird die untersucht, und XSD und WSDL, einschließlich Richtlinien Assertionen, werden für alle Verträge und Bindungen generiert, die WCF mithilfe der vom System bereitgestellten Attribute und Bindungen unterstützen kann. Benutzerdefinierte Verhaltensattribute oder Bindungselemente erfordern jedoch Unterstützung, bevor sie ordnungsgemäß exportiert werden können.  
  
 Dieser Abschnitt beschreibt:  
  
1. Wie man die Schnittstelle <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> implementiert, die Ihnen die WSDL-Generierungsdaten freigibt, bevor das WSDL veröffentlicht wird.  
  
2. Wie man die Schnittstelle <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> implementiert und nutzt, die Ihnen die Richtliniendaten freigibt, bevor die Richtlinienassertionen in WSDL-Daten exportiert werden.  
  
 Weitere Informationen zum Importieren von benutzerdefinierten WSDL-und Richtlinien Assertionen finden Sie unter [Importieren von benutzerdefinierten Metadaten für eine WCF-Erweiterung](importing-custom-metadata-for-a-wcf-extension.md).  
  
## <a name="exporting-custom-wsdl-elements"></a>Exportieren von benutzerdefinierten WSDL-Elementen  

 Implementieren Sie <xref:System.ServiceModel.Description.IWsdlExportExtension> auf einem Vorgangsverhalten, Vertragsverhalten, Endpunktverhalten oder Bindungselement (jeweils <xref:System.ServiceModel.Description.IOperationBehavior>, <xref:System.ServiceModel.Description.IContractBehavior>, <xref:System.ServiceModel.Description.IEndpointBehavior> oder <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>), und fügen Sie die Verhalten oder Bindungselemente in die Beschreibung des Diensts ein, den Sie zu exportieren versuchen. (Weitere Informationen zum Einfügen von Verhalten finden Sie unter [Konfigurieren und Erweitern der Laufzeit mit Verhalten](configuring-and-extending-the-runtime-with-behaviors.md)). <xref:System.ServiceModel.Description.IWsdlExportExtension> wird für jeden Endpunkt aufgerufen, und jeder Endpunkt exportiert zunächst den Vertrag, wenn dieser nicht bereits exportiert worden ist. Sie können je nach Ihren Bedürfnissen an einem der beiden Exportprozesse teilnehmen:  
  
- Verwenden Sie <xref:System.ServiceModel.Description.WsdlContractConversionContext>, um die exportierten Metadaten in der Methode <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%2A> zu ändern.  
  
- Verwenden Sie <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>, um die exportierten Metadaten des Endpunkts in der Methode <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> zu ändern.  
  
 Die Methode <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%2A> wird auf allen <xref:System.ServiceModel.Description.IWsdlExportExtension>-Implementierungen innerhalb der Instanz <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType>, die exportiert wird, aufgerufen.  Die Methode <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> wird auf allen <xref:System.ServiceModel.Description.IWsdlExportExtension>-Implementierungen mit der Instanz <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>, die exportiert wird, aufgerufen.  
  
 Weitere Informationen finden Sie unter Gewusst [wie: Exportieren von benutzerdefinierten WSDL](how-to-export-custom-wsdl.md) und der [benutzerdefinierten WSDL](../samples/custom-wsdl-publication.md)-Beispiel Veröffentlichung.  
  
## <a name="exporting-custom-policy-assertions"></a>Exportieren von benutzerdefinierten Richtlinienassertionen  

 Implementieren Sie <xref:System.ServiceModel.Description.IPolicyExportExtension> auf <xref:System.ServiceModel.Channels.BindingElement>, und fügen Sie der Bindung das Bindungselement hinzu, um benutzerdefinierte Richtlinienassertionen über den Bindungssupport und die Vertragsfähigkeiten in WSDL zu schreiben. <xref:System.ServiceModel.Description.IPolicyExportExtension> wird einmal aufgerufen, wenn das implementierte Bindungselement in eine Bindung exportiert wird, und reicht <xref:System.ServiceModel.Description.PolicyConversionContext> an die Methode <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A> weiter. Sie können die Methoden in der Instanz <xref:System.ServiceModel.Description.PolicyConversionContext> verwenden, um die Richtlinienassertionen, die der WSDL-Bindung am Nachrichten-, Vorgangs- oder Endpunktsubjekt angehängt sind, zu erweitern.  
  
 Weitere Informationen finden Sie unter Gewusst [wie: Exportieren von benutzerdefinierten Richtlinien](how-to-export-custom-policy-assertions.md)Assertionen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Exportieren von benutzerdefinierten WSDL-Informationen](how-to-export-custom-wsdl.md)
- [Vorgehensweise: Exportieren von benutzerdefinierten Richtlinienassertionen](how-to-export-custom-policy-assertions.md)
- [Importieren von benutzerdefinierten Metadaten für eine WCF-Erweiterung](importing-custom-metadata-for-a-wcf-extension.md)

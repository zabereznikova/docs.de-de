---
title: Exportieren von benutzerdefinierten Metadaten für eine WCF-Erweiterung
ms.date: 03/30/2017
ms.assetid: 53c93882-f8ba-4192-965b-787b5e3f09c0
ms.openlocfilehash: 5134b57c59268b139239021bc2b4f6f4538ad27d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857960"
---
# <a name="exporting-custom-metadata-for-a-wcf-extension"></a>Exportieren von benutzerdefinierten Metadaten für eine WCF-Erweiterung
In Windows Communication Foundation (WCF)-metadatenexport ist der Prozess der Beschreibung von Dienstendpunkten und Ihrer Projektion in eine parallele, standardisierte Darstellung, die Clients verwenden können, um zu verstehen, wie Sie den Dienst verwenden. Benutzerdefinierte Metadaten bestehen aus XML-Elementen, die die vom System bereitgestellten Metadaten-Exporteure nicht exportieren können. Normalerweise gehören hierzu benutzerdefinierte Elemente für benutzerdefinierte Verhalten und Bindungselemente und Richtlinienassertionen über die Fähigkeiten und Anforderungen von Bindungen und Verträgen.  
  
 Dieser Abschnitt beschreibt den Export von benutzerdefinierten WSDL- oder Richtlinienassertionen und konzentriert sich nicht auf den Exportprozess selbst. Weitere Informationen dazu, wie Sie die Typen zu verwenden, das Exportieren und Importieren von Metadaten unabhängig davon, ob die Metadaten benutzerdefinierte oder systemkonstruiert sind, finden Sie unter [exportieren und Importieren von Metadaten](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md).  
  
## <a name="overview"></a>Übersicht  
 Wenn Metadaten veröffentlicht werden, mithilfe der <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>, <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType> wird untersucht und XSD und WSDL – einschließlich der Richtlinienassertionen – werden für alle Verträge und Bindungen, WCF unterstützen kann mithilfe von System gelieferten Attributen und Bindungen, generiert. Benutzerdefinierte Verhaltensattribute oder Bindungselemente erfordern jedoch Unterstützung, bevor sie ordnungsgemäß exportiert werden können.  
  
 Dieser Abschnitt beschreibt:  
  
1. Wie man die Schnittstelle <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> implementiert, die Ihnen die WSDL-Generierungsdaten freigibt, bevor das WSDL veröffentlicht wird.  
  
2. Wie man die Schnittstelle <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> implementiert und nutzt, die Ihnen die Richtliniendaten freigibt, bevor die Richtlinienassertionen in WSDL-Daten exportiert werden.  
  
 Weitere Informationen zum Importieren von benutzerdefinierten WSDL- und Richtlinienassertionen finden Sie unter [Importieren von benutzerdefinierten Metadaten für eine WCF-Erweiterung](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md).  
  
## <a name="exporting-custom-wsdl-elements"></a>Exportieren von benutzerdefinierten WSDL-Elementen  
 Implementieren Sie <xref:System.ServiceModel.Description.IWsdlExportExtension> auf einem Vorgangsverhalten, Vertragsverhalten, Endpunktverhalten oder Bindungselement (jeweils <xref:System.ServiceModel.Description.IOperationBehavior>, <xref:System.ServiceModel.Description.IContractBehavior>, <xref:System.ServiceModel.Description.IEndpointBehavior> oder <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>), und fügen Sie die Verhalten oder Bindungselemente in die Beschreibung des Diensts ein, den Sie zu exportieren versuchen. (Weitere Informationen zum Einfügen von Verhaltensweisen finden Sie unter [konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)). <xref:System.ServiceModel.Description.IWsdlExportExtension> wird für jeden Endpunkt aufgerufen, und jeder Endpunkt exportiert zunächst den Vertrag, wenn dieser nicht bereits exportiert worden ist. Sie können je nach Ihren Bedürfnissen an einem der beiden Exportprozesse teilnehmen:  
  
- Verwenden Sie <xref:System.ServiceModel.Description.WsdlContractConversionContext>, um die exportierten Metadaten in der Methode <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%2A> zu ändern.  
  
- Verwenden Sie <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>, um die exportierten Metadaten des Endpunkts in der Methode <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> zu ändern.  
  
 Die Methode <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%2A> wird auf allen <xref:System.ServiceModel.Description.IWsdlExportExtension>-Implementierungen innerhalb der Instanz <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType>, die exportiert wird, aufgerufen.  Die Methode <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> wird auf allen <xref:System.ServiceModel.Description.IWsdlExportExtension>-Implementierungen mit der Instanz <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>, die exportiert wird, aufgerufen.  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Exportieren Sie benutzerdefinierte WSDL](../../../../docs/framework/wcf/extending/how-to-export-custom-wsdl.md) und im Beispiel [benutzerdefinierte WSDL-Veröffentlichung](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md).  
  
## <a name="exporting-custom-policy-assertions"></a>Exportieren von benutzerdefinierten Richtlinienassertionen  
 Implementieren Sie <xref:System.ServiceModel.Description.IPolicyExportExtension> auf <xref:System.ServiceModel.Channels.BindingElement>, und fügen Sie der Bindung das Bindungselement hinzu, um benutzerdefinierte Richtlinienassertionen über den Bindungssupport und die Vertragsfähigkeiten in WSDL zu schreiben. <xref:System.ServiceModel.Description.IPolicyExportExtension> wird einmal aufgerufen, wenn das implementierte Bindungselement in eine Bindung exportiert wird, und reicht <xref:System.ServiceModel.Description.PolicyConversionContext> an die Methode <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A> weiter. Sie können die Methoden in der Instanz <xref:System.ServiceModel.Description.PolicyConversionContext> verwenden, um die Richtlinienassertionen, die der WSDL-Bindung am Nachrichten-, Vorgangs- oder Endpunktsubjekt angehängt sind, zu erweitern.  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Exportieren von benutzerdefinierten Richtlinienassertionen](../../../../docs/framework/wcf/extending/how-to-export-custom-policy-assertions.md).  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Exportieren von benutzerdefinierter WSDL](../../../../docs/framework/wcf/extending/how-to-export-custom-wsdl.md)
- [Vorgehensweise: Exportieren von benutzerdefinierten Richtlinienassertionen](../../../../docs/framework/wcf/extending/how-to-export-custom-policy-assertions.md)
- [Importieren von benutzerdefinierten Metadaten für eine WCF-Erweiterung](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)

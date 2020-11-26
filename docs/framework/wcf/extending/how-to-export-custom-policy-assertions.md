---
title: 'Vorgehensweise: Exportieren von benutzerdefinierten Richtlinienassertionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99030386-43b0-4f7b-866d-17ea307f5cbd
ms.openlocfilehash: 8bdc9948d6846631fde1d428c113682f40d15ec3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249214"
---
# <a name="how-to-export-custom-policy-assertions"></a>Vorgehensweise: Exportieren von benutzerdefinierten Richtlinienassertionen

Richtlinienassertionen beschreiben die Funktionen und Anforderungen eines Dienstendpunkts. Dienstanwendungen können benutzerdefinierte Richtlinienassertionen in Dienstmetadaten verwenden, um Endpunkt-, Bindungs- oder Vertragsanpassungsinformationen an die Clientanwendung zu übermitteln. Sie können Windows Communication Foundation (WCF) verwenden, um Assertionen in Richtlinien Ausdrücken zu exportieren, die in WSDL-Bindungen an den Endpunkt-, Vorgangs-oder Nachrichten Subjekten angefügt sind, abhängig von den Funktionen oder Anforderungen, die Sie miteinander kommunizieren.  
  
 Exportieren Sie benutzerdefinierte Richtlinienassertionen, indem Sie die <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType>-Schnittstelle für <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> implementieren und das Bindungselement entweder direkt in die Bindung des Dienstendpunkts einfügen oder das Bindungselement in der Anwendungskonfigurationsdatei registrieren. Bei der Implementierung des Richtlinienexports sollte die benutzerdefinierte Richtlinienassertion der entsprechenden <xref:System.Xml.XmlElement?displayProperty=nameWithType> zum <xref:System.ServiceModel.Description.PolicyAssertionCollection?displayProperty=nameWithType>, der in der <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=nameWithType>-Methode übergeben wird, als <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A>-Instanz hinzugefügt werden.  
  
 Außerdem müssen Sie die <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A>-Eigenschaft der <xref:System.ServiceModel.Description.WsdlExporter>-Klasse überprüfen und geschachtelte Richtlinienausdrücke und Attribute des Richtlinienframework anhand der angegebenen Richtlinienversion in den richtigen Namespace exportieren.  
  
 Informationen zum Importieren von benutzerdefinierten Richtlinien Assertionen finden Sie unter <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> und Vorgehens [Weise: Importieren benutzerdefinierter Richtlinien](how-to-import-custom-policy-assertions.md)Assertionen.  
  
### <a name="to-export-custom-policy-assertions"></a>So exportieren Sie benutzerdefinierte Richtlinienassertionen  
  
1. Implementieren Sie die <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType>-Schnittstelle für <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>. Im folgenden Codebeispiel wird die Implementierung einer benutzerdefinierten Richtlinienassertion auf der Bindungsebene veranschaulicht.  
  
     [!code-csharp[CustomPolicySample#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/policyexporter.cs#14)]
     [!code-vb[CustomPolicySample#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/policyexporter.vb#14)]  
  
2. Fügen Sie das Bindungselement programmgesteuert oder mithilfe einer Anwendungskonfigurationsdatei in die Endpunktbindung ein. Anweisungen hierzu finden Sie in den folgenden Verfahren.  
  
### <a name="to-insert-a-binding-element-using-an-application-configuration-file"></a>So fügen Sie ein Bindungselement mit einer Anwendungskonfigurationsdatei ein  
  
1. Implementieren Sie <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType> für das Bindungselement der benutzerdefinierten Richtlinienassertion.  
  
2. Fügen Sie die Bindungs Element Erweiterung der Konfigurationsdatei mithilfe des- [\<bindingElementExtensions>](../../configure-apps/file-schema/wcf/bindingelementextensions.md) Elements hinzu.  
  
3. Erstellen Sie mit <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> eine benutzerdefinierte Bindung.  
  
### <a name="to-insert-a-binding-element-programmatically"></a>So fügen Sie ein Bindungselement programmgesteuert ein  
  
1. Erstellen Sie ein neues <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>, und fügen Sie es <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> hinzu.  
  
2. Fügen Sie die benutzerdefinierte Bindung aus Schritt 1 einem neuen Endpunkt hinzu, und fügen Sie diesen neuen Dienstendpunkt <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> hinzu, indem Sie die <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methode aufrufen.  
  
3. Öffnen Sie die Datei <xref:System.ServiceModel.ServiceHost>. Im folgenden Codebeispiel wird das Erstellen einer benutzerdefinierten Bindung und das programmgesteuerte Einfügen von Bindungselementen veranschaulicht.  
  
     [!code-csharp[s_imperative#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_imperative/cs/service.cs#1)]
     [!code-vb[s_imperative#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_imperative/vb/service.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Description.IPolicyImportExtension>
- <xref:System.ServiceModel.Description.IPolicyExportExtension>
- [Vorgehensweise: Importieren von benutzerdefinierten Richtlinienassertionen](how-to-import-custom-policy-assertions.md)

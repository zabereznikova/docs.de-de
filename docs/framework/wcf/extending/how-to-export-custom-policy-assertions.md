---
title: "Vorgehensweise: Exportieren von benutzerdefinierten Richtlinienassertionen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 99030386-43b0-4f7b-866d-17ea307f5cbd
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Vorgehensweise: Exportieren von benutzerdefinierten Richtlinienassertionen
Richtlinienassertionen beschreiben die Funktionen und Anforderungen eines Dienstendpunkts.Dienstanwendungen können benutzerdefinierte Richtlinienassertionen in Dienstmetadaten verwenden, um Endpunkt\-, Bindungs\- oder Vertragsanpassungsinformationen an die Clientanwendung zu übermitteln.Sie können Assertionen je nach den zu übermittelnden Funktionen oder Anforderungen in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in Richtlinienausdrücke exportieren, die in WSDL\-Bindungen am Subjekt des Endpunkts, des Vorgangs oder der Nachricht angefügt werden.  
  
 Exportieren Sie benutzerdefinierte Richtlinienassertionen, indem Sie die <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=fullName>\-Schnittstelle für <xref:System.ServiceModel.Channels.BindingElement?displayProperty=fullName> implementieren und das Bindungselement entweder direkt in die Bindung des Dienstendpunkts einfügen oder das Bindungselement in der Anwendungskonfigurationsdatei registrieren.Bei der Implementierung des Richtlinienexports sollte die benutzerdefinierte Richtlinienassertion der entsprechenden <xref:System.ServiceModel.Description.PolicyAssertionCollection?displayProperty=fullName> zum <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=fullName>, der in der <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A>\-Methode übergeben wird, als <xref:System.Xml.XmlElement?displayProperty=fullName>\-Instanz hinzugefügt werden.  
  
 Außerdem müssen Sie die <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A>\-Eigenschaft der <xref:System.ServiceModel.Description.WsdlExporter>\-Klasse überprüfen und geschachtelte Richtlinienausdrücke und Attribute des Richtlinienframework anhand der angegebenen Richtlinienversion in den richtigen Namespace exportieren.  
  
 Weitere Informationen zum Importieren von benutzerdefinierten Richtlinienassertionen finden Sie unter <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=fullName> und [Vorgehensweise: Importieren von benutzerdefinierten Richtlinienassertionen](../../../../docs/framework/wcf/extending/how-to-import-custom-policy-assertions.md).  
  
### So exportieren Sie benutzerdefinierte Richtlinienassertionen  
  
1.  Implementieren Sie die <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=fullName>\-Schnittstelle für <xref:System.ServiceModel.Channels.BindingElement?displayProperty=fullName>.Im folgenden Codebeispiel wird die Implementierung einer benutzerdefinierten Richtlinienassertion auf der Bindungsebene veranschaulicht.  
  
     [!code-csharp[CustomPolicySample#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/policyexporter.cs#14)]
     [!code-vb[CustomPolicySample#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/policyexporter.vb#14)]  
  
2.  Fügen Sie das Bindungselement programmgesteuert oder mithilfe einer Anwendungskonfigurationsdatei in die Endpunktbindung ein.Anweisungen hierzu finden Sie in den folgenden Verfahren.  
  
### So fügen Sie ein Bindungselement mit einer Anwendungskonfigurationsdatei ein  
  
1.  Implementieren Sie <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=fullName> für das Bindungselement der benutzerdefinierten Richtlinienassertion.  
  
2.  Fügen Sie der Konfigurationsdatei mit dem [\<bindingElementExtensions\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindingelementextensions.md)\-Element die Erweiterung des Bindungselements hinzu.  
  
3.  Erstellen Sie mit <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=fullName> eine benutzerdefinierte Bindung.  
  
### So fügen Sie ein Bindungselement programmgesteuert ein  
  
1.  Erstellen Sie ein neues <xref:System.ServiceModel.Channels.BindingElement?displayProperty=fullName>, und fügen Sie es <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=fullName> hinzu.  
  
2.  Fügen Sie die benutzerdefinierte Bindung aus Schritt 1einem neuen Endpunkt hinzu, und fügen Sie diesen neuen Dienstendpunkt <xref:System.ServiceModel.ServiceHost?displayProperty=fullName> hinzu, indem Sie die <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>\-Methode aufrufen.  
  
3.  Öffnen Sie <xref:System.ServiceModel.ServiceHost>.Im folgenden Codebeispiel wird das Erstellen einer benutzerdefinierten Bindung und das programmgesteuerte Einfügen von Bindungselementen veranschaulicht.  
  
     [!code-csharp[s_imperative#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_imperative/cs/service.cs#1)]
     [!code-vb[s_imperative#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_imperative/vb/service.vb#1)]  
  
## Siehe auch  
 <xref:System.ServiceModel.Description.IPolicyImportExtension>   
 <xref:System.ServiceModel.Description.IPolicyExportExtension>   
 [Vorgehensweise: Importieren von benutzerdefinierten Richtlinienassertionen](../../../../docs/framework/wcf/extending/how-to-import-custom-policy-assertions.md)
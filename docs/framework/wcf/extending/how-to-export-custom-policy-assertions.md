---
title: 'Vorgehensweise: Exportieren von benutzerdefinierten Richtlinienassertionen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 99030386-43b0-4f7b-866d-17ea307f5cbd
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 466aecb5102332d3e246fd340e43b482d2c17a4c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-export-custom-policy-assertions"></a>Vorgehensweise: Exportieren von benutzerdefinierten Richtlinienassertionen
Richtlinienassertionen beschreiben die Funktionen und Anforderungen eines Dienstendpunkts. Dienstanwendungen können benutzerdefinierte Richtlinienassertionen in Dienstmetadaten verwenden, um Endpunkt-, Bindungs- oder Vertragsanpassungsinformationen an die Clientanwendung zu übermitteln. Sie können Assertionen je nach den zu übermittelnden Funktionen oder Anforderungen in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in Richtlinienausdrücke exportieren, die in WSDL-Bindungen am Subjekt des Endpunkts, des Vorgangs oder der Nachricht angefügt werden.  
  
 Exportieren Sie benutzerdefinierte Richtlinienassertionen, indem Sie die <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType>-Schnittstelle für <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> implementieren und das Bindungselement entweder direkt in die Bindung des Dienstendpunkts einfügen oder das Bindungselement in der Anwendungskonfigurationsdatei registrieren. Bei der Implementierung des Richtlinienexports sollte die benutzerdefinierte Richtlinienassertion der entsprechenden <xref:System.Xml.XmlElement?displayProperty=nameWithType> zum <xref:System.ServiceModel.Description.PolicyAssertionCollection?displayProperty=nameWithType>, der in der <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=nameWithType>-Methode übergeben wird, als <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A>-Instanz hinzugefügt werden.  
  
 Außerdem müssen Sie die <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A>-Eigenschaft der <xref:System.ServiceModel.Description.WsdlExporter>-Klasse überprüfen und geschachtelte Richtlinienausdrücke und Attribute des Richtlinienframework anhand der angegebenen Richtlinienversion in den richtigen Namespace exportieren.  
  
 Um benutzerdefinierte Richtlinienassertionen zu importieren, finden Sie unter <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> und [Vorgehensweise: Importieren von benutzerdefinierten Richtlinienassertionen](../../../../docs/framework/wcf/extending/how-to-import-custom-policy-assertions.md).  
  
### <a name="to-export-custom-policy-assertions"></a>So exportieren Sie benutzerdefinierte Richtlinienassertionen  
  
1.  Implementieren Sie die <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType>-Schnittstelle für <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>. Im folgenden Codebeispiel wird die Implementierung einer benutzerdefinierten Richtlinienassertion auf der Bindungsebene veranschaulicht.  
  
     [!code-csharp[CustomPolicySample#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/policyexporter.cs#14)]
     [!code-vb[CustomPolicySample#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/policyexporter.vb#14)]  
  
2.  Fügen Sie das Bindungselement programmgesteuert oder mithilfe einer Anwendungskonfigurationsdatei in die Endpunktbindung ein. Anweisungen hierzu finden Sie in den folgenden Verfahren.  
  
### <a name="to-insert-a-binding-element-using-an-application-configuration-file"></a>So fügen Sie ein Bindungselement mit einer Anwendungskonfigurationsdatei ein  
  
1.  Implementieren Sie <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType> für das Bindungselement der benutzerdefinierten Richtlinienassertion.  
  
2.  Fügen Sie die bindungselementerweiterung auf die Konfigurationsdatei mit den [ \<BindingElementExtensions >](../../../../docs/framework/configure-apps/file-schema/wcf/bindingelementextensions.md) Element.  
  
3.  Erstellen Sie mit <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> eine benutzerdefinierte Bindung.  
  
### <a name="to-insert-a-binding-element-programmatically"></a>So fügen Sie ein Bindungselement programmgesteuert ein  
  
1.  Erstellen Sie ein neues <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType>, und fügen Sie es <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> hinzu.  
  
2.  Fügen Sie die benutzerdefinierte Bindung aus Schritt 1 einem neuen Endpunkt hinzu, und fügen Sie diesen neuen Dienstendpunkt <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> hinzu, indem Sie die <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methode aufrufen.  
  
3.  Öffnen Sie <xref:System.ServiceModel.ServiceHost>. Im folgenden Codebeispiel wird das Erstellen einer benutzerdefinierten Bindung und das programmgesteuerte Einfügen von Bindungselementen veranschaulicht.  
  
     [!code-csharp[s_imperative#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_imperative/cs/service.cs#1)]
     [!code-vb[s_imperative#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_imperative/vb/service.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Description.IPolicyImportExtension>  
 <xref:System.ServiceModel.Description.IPolicyExportExtension>  
 [Vorgehensweise: Importieren von benutzerdefinierten Richtlinienassertionen](../../../../docs/framework/wcf/extending/how-to-import-custom-policy-assertions.md)

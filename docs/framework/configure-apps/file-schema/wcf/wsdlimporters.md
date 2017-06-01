---
title: "&lt;wsdlImporters&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 270c7f93-eab7-47b6-8b94-ac3f5b7f17e4
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;wsdlImporters&gt;
Dieses Konfigurationselement gibt alle WSDL\-Importer an, die WSDL 1.1\-Metadaten \(Web Services Description Language\) mit WS\-Richtlinienanhängen importieren.  Jedes untergeordnete Element ist ein \<`wsdlImporter`\>, der die Art und Weise des Imports von Metadaten und der Konvertierung der Informationen in verschiedene Klassen angibt, die Vertrags\- und Endpunktinformationen darstellen.  Vertrags\- und Endpunktinformationen sowie Eigenschaften, die Importfehler offenlegen und Typinformationen akzeptieren, die für den Import\- und Konvertierungsvorgang relevant sind, können selektiv importiert werden.  Außerdem wird der Import von Bindungsinformationen und \-eigenschaften unterstützt, die Zugriff auf Richtliniendokumente, WSDL\-Dokumente, WSDL\-Erweiterungen und XML\-Schemadokumente bereitstellen.  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.MetadataElement>   
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>   
 <xref:System.ServiceModel.Description.MetadataImporter>   
 <xref:System.ServiceModel.Description.WsdlImporter>   
 [WCF\-Clientkonfiguration](../../../../../docs/framework/wcf/feature-details/client-configuration.md)   
 [Clients](../../../../../docs/framework/wcf/feature-details/clients.md)
---
title: "Vorgehensweise: Importieren von Metadaten in Dienstendpunkte | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b69dbe20-92a1-4911-89d8-ffbc3dad4663
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Vorgehensweise: Importieren von Metadaten in Dienstendpunkte
In diesem Thema wird erläutert, wie Sie Metadaten in eine Auflistung der Dienstendpunkte importieren und den unter [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md) definierten Dienst verwenden.  Im Thema wird gezeigt, wie Sie eine Clientanwendung erstellen, die Metadaten aus dem Dienst importiert und anschließend die`Add`\-Methode für den Dienst aufruft.  
  
### So importieren Sie Metadaten in Dienstendpunkte  
  
1.  Deklarieren Sie ein <xref:System.ServiceModel.EndpointAddress>\-Objekt, und initialisieren Sie es mit dem Uniform Resource Identifier \(URI\) für die Metadatenaustausch\-Adresse \(MEX\) des Dienstes.  
  
     [!code-csharp[UE_ImportMetadata#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#0)]  
  
2.  Erstellen Sie einen <xref:System.ServiceModel.Description.MetadataExchangeClient>, der die MEX\-Adresse übergibt, und rufen Sie <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> auf.  Auf diese Weise werden die Metadaten aus dem Dienst abgerufen.  
  
     [!code-csharp[UE_ImportMetadata#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#1)]  
  
3.  Erstellen Sie einen <xref:System.ServiceModel.Description.WsdlImporter>, der die vorher abgerufenen Metadaten übergibt, und rufen Sie <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A> auf.  Dadurch wird eine Auflistung der <xref:System.ServiceModel.Description.ContractDescription>\-Objekte erzeugt.  Sie können je nach Ihren Anforderungen auch <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> oder <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A> aufrufen.  
  
     [!code-csharp[UE_ImportMetadata#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#2)]  
  
    > [!NOTE]
    >  Nachdem Sie die Metadaten importiert haben, können Sie keinen Clientkanal mehr erstellen oder die Metadaten exportieren.  Dies liegt daran, dass an diesem Punkt keine Typinformationen verfügbar sind.  Typinformationen sind erforderlich, um direkt mit dem Dienst zu interagieren oder Metadaten zu exportieren.  Um die Typinformationen zu erzeugen, müssen Sie den in den Schritten 4 und 5 gezeigten Code generieren.  Alternativ dazu können Sie auch die <xref:System.ServiceModel.Description.MetadataResolver>\-Hilfsklasse verwenden.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Vorgehensweise: Verwenden von MetadataResolver, um Bindungsmetadaten dynamisch zu erhalten](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md).  
  
4.  Generieren Sie Typinformationen für jeden Vertrag.  
  
     [!code-csharp[UE_ImportMetadata#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#3)]  
  
5.  Jetzt können Sie diese Informationen verwenden.  Im folgenden Beispiel wird C\#\-Quellcode generiert.  
  
     [!code-csharp[UE_ImportMetadata#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#4)]  
  
## Siehe auch  
 [Metadaten](../../../../docs/framework/wcf/feature-details/metadata.md)   
 [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md)
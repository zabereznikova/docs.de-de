---
title: "Vorgehensweise: Die Verwendung von MetadataExchangeClient zum Abrufen von Metadaten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0754e9dc-13c5-45c2-81b5-f3da466e5a87
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Vorgehensweise: Die Verwendung von MetadataExchangeClient zum Abrufen von Metadaten
Verwenden Sie die <xref:System.ServiceModel.Description.MetadataExchangeClient>\-Klasse, um Metadaten mit dem WS\-MetadataExchange \(MEX\)\-Protokoll herunterzuladen.Die abgerufenen Metadatendateien werden als <xref:System.ServiceModel.Description.MetadataSet>\-Objekt zurückgegeben.Das zurückgegebene <xref:System.ServiceModel.Description.MetadataSet>\-Objekt enthält eine Auflistung der <xref:System.ServiceModel.Description.MetadataSection>\-Objekte, von denen jedes einen bestimmten Metadatendialekt sowie eine ID enthält.Sie können die zurückgegebenen Metadaten in Dateien schreiben. Wenn die zurückgegebenen Metadaten WSDL \(Web Services Description Language\)\-Dokumente enthalten, können Sie die Metadaten mit <xref:System.ServiceModel.Description.WsdlImporter> importieren.  
  
 Die <xref:System.ServiceModel.Description.MetadataExchangeClient>\-Konstruktoren, die eine Adresse enthalten, verwenden die Bindung der statischen <xref:System.ServiceModel.Description.MetadataExchangeBindings>\-Klasse, die dem URL\-\(Uniform Resource Identifier\-\)Schema der Adresse entspricht.Sie können als Alternative auch den <xref:System.ServiceModel.Description.MetadataExchangeClient>\-Konstruktor verwenden, mit dem Sie die zu verwendende Bindung ausdrücklich angeben können.Die angegebene Bindung wird zum Auflösen aller Metadatenverweise verwendet.  
  
 Wie bei jedem anderen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Client stellt der <xref:System.ServiceModel.Description.MetadataExchangeClient>\-Typ einen Konstruktor zum Laden der Clientendpunkt\-Konfigurationen mithilfe des Endpunktkonfigurationsnamens bereit.Die angegebene Endpunktkonfiguration muss den <xref:System.ServiceModel.Description.IMetadataExchange>\-Vertrag angeben.Die Adresse der Endpunktkonfiguration ist nicht geladen. Deshalb müssen Sie eine der <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>\-Überladungen verwenden, die eine Adresse verwenden.Wenn Sie die Metadatenadresse mit einer <xref:System.ServiceModel.EndpointAddress>\-Instanz angeben, geht <xref:System.ServiceModel.Description.MetadataExchangeClient> davon aus, dass die Adresse auf einen MEX\-Endpunkt verweist.Wenn Sie die Metadatenadresse als URL angeben, müssen Sie auch angeben, welcher <xref:System.ServiceModel.Description.MetadataExchangeClientMode> verwendet werden soll, MEX oder HTTP GET.  
  
> [!IMPORTANT]
>  Standardmäßig löst <xref:System.ServiceModel.Description.MetadataExchangeClient> alle Verweise auf, einschließlich WSDL\- und XML\-Schemaimporte und \-Includes.Sie können diese Funktion deaktivieren, indem Sie die Eigenschaft <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> auf `false` festlegen.Sie können die maximale Anzahl von aufzulösenden Verweisen mithilfe der <xref:System.ServiceModel.Description.MetadataExchangeClient.MaximumResolvedReferences%2A>\-Eigenschaft steuern.Sie können diese Eigenschaft zusammen mit der `MaxReceivedMessageSize`\-Eigenschaft für die Bindung verwenden, um zu steuern, wie viele Metadaten abgerufen werden.  
  
### So verwenden Sie MetadataExchangeClient zum Abrufen von Metadaten  
  
1.  Erstellen Sie ein neues <xref:System.ServiceModel.Description.MetadataExchangeClient>\-Objekt, indem Sie ausdrücklich eine Bindung, einen Endpunktkonfigurationsnamen oder die Adresse der Metadaten angeben.  
  
2.  Konfigurieren Sie <xref:System.ServiceModel.Description.MetadataExchangeClient>, um ihn an Ihre Anforderungen anzupassen.So können Sie z. B. Anmeldeinformationen angeben, die verwendet werden, wenn Metadaten angefordert werden. Und Sie können die <xref:System.ServiceModel.Description.MetadataExchangeClient.OperationTimeout%2A>\-Eigenschaft festlegen, um zu steuern, wie lange die Metadatenanforderung zurückgegeben werden muss, bevor das Zeitlimit überschritten wird.  
  
3.  Rufen Sie das <xref:System.ServiceModel.Description.MetadataSet>\-Objekt ab, das die abgerufenen Metadaten enthält, indem Sie eine der <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>\-Methoden aufrufen.Beachten Sie, dass Sie lediglich die <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>\-Überladung verwenden können, die keine Argumente aufnimmt, wenn Sie beim Erstellen von <xref:System.ServiceModel.Description.MetadataExchangeClient> ausdrücklich eine Adresse angegeben haben.  
  
## Beispiel  
 Im folgenden Codebeispiel wird die Verwendung von <xref:System.ServiceModel.Description.MetadataExchangeClient> dargestellt, mit dem Metadatendateien heruntergeladen und aufgelistet werden.  
  
 [!code-csharp[MetadataResolver#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/metadataresolver/cs/client.cs#3)]  
  
## Kompilieren des Codes  
 Um dieses Codebeispiel zu kompilieren, müssen Sie die System.ServiceModel.dll\-Assembly mit Verweisen versehen und den <xref:System.ServiceModel.Description>\-Namespace importieren.  
  
## Siehe auch  
 <xref:System.ServiceModel.Description.MetadataResolver>   
 <xref:System.ServiceModel.Description.MetadataExchangeClient>   
 <xref:System.ServiceModel.Description.WsdlImporter>
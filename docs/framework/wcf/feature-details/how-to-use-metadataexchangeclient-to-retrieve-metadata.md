---
title: 'Vorgehensweise: Die Verwendung von MetadataExchangeClient zum Abrufen von Metadaten'
ms.date: 03/30/2017
ms.assetid: 0754e9dc-13c5-45c2-81b5-f3da466e5a87
ms.openlocfilehash: 412e695036f29886310099cc5a55b940247b0c72
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280831"
---
# <a name="how-to-use-metadataexchangeclient-to-retrieve-metadata"></a>Vorgehensweise: Die Verwendung von MetadataExchangeClient zum Abrufen von Metadaten

Verwenden Sie die <xref:System.ServiceModel.Description.MetadataExchangeClient>-Klasse, um Metadaten mit dem WS-MetadataExchange (MEX)-Protokoll herunterzuladen. Die abgerufenen Metadatendateien werden als <xref:System.ServiceModel.Description.MetadataSet>-Objekt zurückgegeben. Das zurückgegebene <xref:System.ServiceModel.Description.MetadataSet>-Objekt enthält eine Auflistung der <xref:System.ServiceModel.Description.MetadataSection>-Objekte, von denen jedes einen bestimmten Metadatendialekt sowie eine ID enthält. Sie können die zurückgegebenen Metadaten in Dateien schreiben. Wenn die zurückgegebenen Metadaten WSDL (Web Services Description Language)-Dokumente enthalten, können Sie die Metadaten mit <xref:System.ServiceModel.Description.WsdlImporter> importieren.  
  
 Die <xref:System.ServiceModel.Description.MetadataExchangeClient>-Konstruktoren, die eine Adresse enthalten, verwenden die Bindung der statischen <xref:System.ServiceModel.Description.MetadataExchangeBindings>-Klasse, die dem URL-(Uniform Resource Identifier-)Schema der Adresse entspricht. Sie können als Alternative auch den <xref:System.ServiceModel.Description.MetadataExchangeClient>-Konstruktor verwenden, mit dem Sie die zu verwendende Bindung ausdrücklich angeben können. Die angegebene Bindung wird zum Auflösen aller Metadatenverweise verwendet.  
  
 Ebenso wie jeder andere Windows Communication Foundation (WCF)-Client stellt der- <xref:System.ServiceModel.Description.MetadataExchangeClient> Typ einen Konstruktor zum Laden von clientend Punkt Konfigurationen mithilfe des Endpunkt Konfigurations namens bereit. Die angegebene Endpunktkonfiguration muss den <xref:System.ServiceModel.Description.IMetadataExchange>-Vertrag angeben. Die Adresse der Endpunktkonfiguration ist nicht geladen. Deshalb müssen Sie eine der <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>-Überladungen verwenden, die eine Adresse verwenden. Wenn Sie die Metadatenadresse mit einer <xref:System.ServiceModel.EndpointAddress>-Instanz angeben, geht <xref:System.ServiceModel.Description.MetadataExchangeClient> davon aus, dass die Adresse auf einen MEX-Endpunkt verweist. Wenn Sie die Metadatenadresse als URL angeben, müssen Sie auch angeben, welcher <xref:System.ServiceModel.Description.MetadataExchangeClientMode> verwendet werden soll, MEX oder HTTP GET.  
  
> [!IMPORTANT]
> Standardmäßig löst <xref:System.ServiceModel.Description.MetadataExchangeClient> alle Verweise auf, einschließlich WSDL- und XML-Schemaimporte und -Includes. Sie können diese Funktion deaktivieren, indem Sie die Eigenschaft <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> auf `false` festlegen. Sie können die maximale Anzahl von aufzulösenden Verweisen mithilfe der <xref:System.ServiceModel.Description.MetadataExchangeClient.MaximumResolvedReferences%2A>-Eigenschaft steuern. Sie können diese Eigenschaft zusammen mit der `MaxReceivedMessageSize`-Eigenschaft für die Bindung verwenden, um zu steuern, wie viele Metadaten abgerufen werden.  
  
### <a name="to-use-metadataexchangeclient-to-obtain-metadata"></a>So verwenden Sie MetadataExchangeClient zum Abrufen von Metadaten  
  
1. Erstellen Sie ein neues <xref:System.ServiceModel.Description.MetadataExchangeClient>-Objekt, indem Sie ausdrücklich eine Bindung, einen Endpunktkonfigurationsnamen oder die Adresse der Metadaten angeben.  
  
2. Konfigurieren Sie <xref:System.ServiceModel.Description.MetadataExchangeClient>, um ihn an Ihre Anforderungen anzupassen. So können Sie z.&#160;B. Anmeldeinformationen angeben, die verwendet werden, wenn Metadaten angefordert werden. Und Sie können die <xref:System.ServiceModel.Description.MetadataExchangeClient.OperationTimeout%2A>-Eigenschaft festlegen, um zu steuern, wie lange die Metadatenanforderung zurückgegeben werden muss, bevor das Zeitlimit überschritten wird.  
  
3. Rufen Sie das <xref:System.ServiceModel.Description.MetadataSet>-Objekt ab, das die abgerufenen Metadaten enthält, indem Sie eine der <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>-Methoden aufrufen. Beachten Sie, dass Sie lediglich die <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>-Überladung verwenden können, die keine Argumente aufnimmt, wenn Sie beim Erstellen von <xref:System.ServiceModel.Description.MetadataExchangeClient> ausdrücklich eine Adresse angegeben haben.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Codebeispiel wird die Verwendung von <xref:System.ServiceModel.Description.MetadataExchangeClient> dargestellt, mit dem Metadatendateien heruntergeladen und aufgelistet werden.  

 [!code-csharp[MetadataResolver#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/metadataresolver/cs/client.cs#3)]  

## <a name="compiling-the-code"></a>Kompilieren des Codes  

 Um dieses Codebeispiel zu kompilieren, müssen Sie die System.ServiceModel.dll-Assembly mit Verweisen versehen und den <xref:System.ServiceModel.Description>-Namespace importieren.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Description.MetadataResolver>
- <xref:System.ServiceModel.Description.MetadataExchangeClient>
- <xref:System.ServiceModel.Description.WsdlImporter>

---
title: Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung
ms.date: 03/30/2017
ms.assetid: 904e11b4-d90e-45c6-9ee5-c3472c90008c
ms.openlocfilehash: 528f7662ee3a1f956427e5e42f540816f55027f8
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="publishing-and-retrieving-metadata-over-a-custom-binding"></a>Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung
<xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> bietet Support für das Hinzufügen von Metadatenendpunkten zu einem Dienst. Diese Metadatenendpunkte können reagieren auf HTTP GET-Anforderungen an eine URL, die verfügt über eine `?wsdl` Querystring und WS-Transfer GET-Anforderungen, wie in der WS-MetadataExchange (MEX)-Spezifikation definiert. MEX-Endpunkte implementieren den <xref:System.ServiceModel.Description.IMetadataExchange?displayProperty=nameWithType>-Vertrag.  
  
## <a name="publishing-metadata-over-a-custom-binding"></a>Veröffentlichen von Metadaten über eine benutzerdefinierte Bindung  
 Die HTTP GET-Metadatenendpunkte und HTTPS GET-Metadatenendpunkte werden durch Festlegen der <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A?displayProperty=nameWithType>-Eigenschaften oder <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A?displayProperty=nameWithType>-Eigenschaften auf `true` aktiviert. Die Bindungen für diese Endpunkte können nicht konfiguriert werden.  
  
 Die <xref:System.ServiceModel.Description.IMetadataExchange> Vertrag, aber kann verwendet werden, mit anderen Endpunkten, auch solche, die benutzerdefinierte Bindungen verwenden, da <xref:System.ServiceModel.Description.IMetadataExchange> Endpunkte sind identisch mit anderen Windows Communication Foundation (WCF)-Dienstendpunkt. Wenn Sie wissen, wie Sie die Konfiguration einer vom System bereitgestellten Bindung ändern können oder wie Sie eine <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> konfigurieren können, dann können Sie eine Bindung so konfigurieren, dass sie mit einem <xref:System.ServiceModel.Description.IMetadataExchange>-Endpunkt verwendet werden kann.  
  
## <a name="retrieving-metadata-over-a-custom-binding"></a>Abrufen von Metadaten über eine benutzerdefinierte Bindung  
 Metadaten können von HTTP Get-Metadatenendpunkten und HTTPS Get-Metadatenendpunkten mit Standard-HTTP-Anforderungen bzw. HTTPS-GET-Anforderungen abgerufen werden.  
  
 Zum Abrufen von Metadaten von einem MEX-Metadatenendpunkt eine der von WCF unterstützten standard-MEX-Bindungen in der Regel verwenden können. Weitere Informationen finden Sie unter <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType>. Der <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType>-Typ und das Tool "Svcutil.exe" wählen automatisch eine dieser Standard-MEX-Bindungen basierend auf der Adresse des angegebenen Metadatenendpunkts aus.  
  
 Wenn ein MEX-Metadatenendpunkt eine andere Bindung als eine der Standard-MEX-Bindungen verwendet, können Sie die vom <xref:System.ServiceModel.Description.MetadataExchangeClient> verwendete Bindung mit Code oder über die Angabe einer <xref:System.ServiceModel.Description.IMetadataExchange>-Clientendpunktkonfiguration konfigurieren. Das Tool Svcutil.exe lädt automatisch aus der Konfigurationsdatei eine <xref:System.ServiceModel.Description.IMetadataExchange>-Clientendpunktkonfiguration, die den gleichen Namen hat wie das URI-Schema für die Metadatenendpunktadresse.  
  
## <a name="security"></a>Sicherheit  
 Stellen Sie beim Veröffentlichen von Metadaten über eine benutzerdefinierte Bindung sicher, dass die Bindung den Sicherheitssupport bietet, der für die Metadaten erforderlich ist. Um beispielsweise die Offenlegung von Informationen zu verhindern und sicherzustellen, dass der Client die Berechtigung hat, die Metadaten abzurufen, können Sie die Metadaten und die Anwendung weiter sichern, indem Sie den <xref:System.ServiceModel.Description.IMetadataExchange>-Endpunkt so konfigurieren, dass eine Authentifizierung und Verschlüsselung notwendig sind. Im Beispiel [benutzerdefinierter sicherer Metadatenendpunkt](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) wird dieses Szenario veranschaulicht.  
  
## <a name="see-also"></a>Siehe auch  
 [Sichern von Diensten](../../../../docs/framework/wcf/securing-services.md)  
 [WS-MetadataExchange-Bindungen](../../../../docs/framework/wcf/extending/ws-metadataexchange-bindings.md)  
 [Vorgehensweise: Konfigurieren einer benutzerdefinierten WS-Metadata Exchange-Bindung](../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)  
 [Vorgehensweise: Abrufen von Metadaten über eine Nicht-MEX-Bindung](../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)

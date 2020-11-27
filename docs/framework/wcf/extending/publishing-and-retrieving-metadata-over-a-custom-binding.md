---
title: Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung
ms.date: 03/30/2017
ms.assetid: 904e11b4-d90e-45c6-9ee5-c3472c90008c
ms.openlocfilehash: 2c88ab92bb9cbe2fc07240d0934d246fa4de5cc0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262761"
---
# <a name="publishing-and-retrieving-metadata-over-a-custom-binding"></a>Veröffentlichen und Abrufen von Metadaten über eine benutzerdefinierte Bindung

<xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> bietet Support für das Hinzufügen von Metadatenendpunkten zu einem Dienst. Diese Metadatenendpunkte können auf HTTP GET-Anforderungen bei einer URL reagieren, die eine `?wsdl` QueryString hat, und um WS-Transfer Get-Anforderungen zu, wie in der WS-MetadataExchange (MEX)-Spezifikation definiert. MEX-Endpunkte implementieren den <xref:System.ServiceModel.Description.IMetadataExchange?displayProperty=nameWithType>-Vertrag.  
  
## <a name="publishing-metadata-over-a-custom-binding"></a>Veröffentlichen von Metadaten über eine benutzerdefinierte Bindung  

 Die HTTP GET-Metadatenendpunkte und HTTPS GET-Metadatenendpunkte werden durch Festlegen der <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A?displayProperty=nameWithType>-Eigenschaften oder <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A?displayProperty=nameWithType>-Eigenschaften auf `true` aktiviert. Die Bindungen für diese Endpunkte können nicht konfiguriert werden.  
  
 Der <xref:System.ServiceModel.Description.IMetadataExchange> Vertrag kann jedoch mit jedem beliebigen Endpunkt verwendet werden, einschließlich derjenigen, die benutzerdefinierte Bindungen verwenden, da <xref:System.ServiceModel.Description.IMetadataExchange> Endpunkte mit einem beliebigen anderen Windows Communication Foundation (WCF)-Dienst Endpunkt identisch sind. Wenn Sie wissen, wie Sie die Konfiguration einer vom System bereitgestellten Bindung ändern können oder wie Sie eine <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> konfigurieren können, dann können Sie eine Bindung so konfigurieren, dass sie mit einem <xref:System.ServiceModel.Description.IMetadataExchange>-Endpunkt verwendet werden kann.  
  
## <a name="retrieving-metadata-over-a-custom-binding"></a>Abrufen von Metadaten über eine benutzerdefinierte Bindung  

 Metadaten können von HTTP Get-Metadatenendpunkten und HTTPS Get-Metadatenendpunkten mit Standard-HTTP-Anforderungen bzw. HTTPS-GET-Anforderungen abgerufen werden.  
  
 Um Metadaten von einem MEX-Metadatenendpunkt abzurufen, können Sie eine der Standard-MEX-Bindungen verwenden, die von WCF unterstützt werden. Weitere Informationen finden Sie unter <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType>. Der <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType>-Typ und das Tool „Svcutil.exe“ wählen automatisch eine dieser Standard-MEX-Bindungen basierend auf der Adresse des angegebenen Metadatenendpunkts aus.  
  
 Wenn ein MEX-Metadatenendpunkt eine andere Bindung als eine der Standard-MEX-Bindungen verwendet, können Sie die vom <xref:System.ServiceModel.Description.MetadataExchangeClient> verwendete Bindung mit Code oder über die Angabe einer <xref:System.ServiceModel.Description.IMetadataExchange>-Clientendpunktkonfiguration konfigurieren. Das Tool Svcutil.exe lädt automatisch aus der Konfigurationsdatei eine <xref:System.ServiceModel.Description.IMetadataExchange>-Clientendpunktkonfiguration, die den gleichen Namen hat wie das URI-Schema für die Metadatenendpunktadresse.  
  
## <a name="security"></a>Sicherheit  

 Stellen Sie beim Veröffentlichen von Metadaten über eine benutzerdefinierte Bindung sicher, dass die Bindung den Sicherheitssupport bietet, der für die Metadaten erforderlich ist. Um beispielsweise die Offenlegung von Informationen zu verhindern und sicherzustellen, dass der Client die Berechtigung hat, die Metadaten abzurufen, können Sie die Metadaten und die Anwendung weiter sichern, indem Sie den <xref:System.ServiceModel.Description.IMetadataExchange>-Endpunkt so konfigurieren, dass eine Authentifizierung und Verschlüsselung notwendig sind. Das Beispiel für einen [benutzerdefinierten sicheren Metadatenendpunkt](../samples/custom-secure-metadata-endpoint.md) veranschaulicht dieses Szenario.  
  
## <a name="see-also"></a>Weitere Informationen

- [Sichern von Diensten](../securing-services.md)
- [WS-MetadataExchange-Bindungen](ws-metadataexchange-bindings.md)
- [Vorgehensweise: Konfigurieren einer benutzerdefinierten WS-Metadata Exchange-Bindung](how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [Vorgehensweise: Aufrufen von Metadaten über eine Nicht-MEX-Bindung](how-to-retrieve-metadata-over-a-non-mex-binding.md)

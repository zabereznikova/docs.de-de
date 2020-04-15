---
title: Erstellen von interoperablen WS-I Basic Profile 1.1-Diensten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
ms.openlocfilehash: fd7828cccb1a19a17e899525d863021d3670fbdd
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389762"
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a>Erstellen von interoperablen WS-I Basic Profile 1.1-Diensten
So konfigurieren Sie einen WCF-Dienstendpunkt so, dass er mit ASP.NET Webdienstclients interoperabel ist:  
  
- Verwenden Sie den <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>-Typ als Bindungstyp für den Dienstendpunkt.  
  
- Verwenden Sie für den Dienstendpunkt keine Rückruf- und Sitzungsvertragsfunktionen oder Transaktionsverhalten.  
  
Sie können für die Bindung auch Unterstützung für HTTPS und Clientauthentifizierung auf Transportebene aktivieren.  
  
Die folgenden Funktionen der <xref:System.ServiceModel.BasicHttpBinding>-Klasse erfordern Funktionalität jenseits von WS-I Basic Profiles 1.1:  
  
- MTOM-Meldungscodierung (Message Transmission Optimization Mechanism), die von der <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>-Eigenschaft gesteuert wird. Behalten Sie für diese Eigenschaft den Standardwert bei, der <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> ist, was bedeutet, dass kein MTOM verwendet wird.  
  
- Meldungssicherheit, die vom <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType>-Wert gesteuert wird, stellt WS-Sicherheit bereit, die mit WS-I Basic Security Profile 1.0 kompatibel ist. Behalten Sie für diese Eigenschaft den Standardwert <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> bei, d. h. es wird keine WS-Sicherheit verwendet.  
  
Um die Metadaten für einen WCF-Dienst für ASP.NET verfügbar zu machen, verwenden Sie die Tools zur Webdienstclientgenerierung: [Web Services Description Language Tool (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6%28v=vs.100%29), Web Services Discovery Tool [(Disco.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs%28v=vs.100%29)und die Funktion **Webreferenz hinzufügen** in Visual Studio. Aktivieren sie die Metadatenpublikation. Weitere Informationen finden Sie unter [Veröffentlichen von Metadatenendpunkten](publishing-metadata-endpoints.md).  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>BESCHREIBUNG  
 Im folgenden Beispielcode wird veranschaulicht, wie Sie einen WCF-Endpunkt hinzufügen, der mit ASP.NET Webdienstclients im Code und alternativ in einer Konfigurationsdatei kompatibel ist.  
  
### <a name="code"></a>Code  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Interoperabilität mit ASP.NET-Webdiensten](./feature-details/interop-with-aspnet-web-services.md)

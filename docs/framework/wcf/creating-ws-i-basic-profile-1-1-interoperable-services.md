---
title: Erstellen von interoperablen WS-I Basic Profile 1.1-Diensten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
ms.openlocfilehash: 7d732f26f3f679d744f86863a13d1ca0d7c88819
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43400689"
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a>Erstellen von interoperablen WS-I Basic Profile 1.1-Diensten
So konfigurieren Sie einen WCF-Dienstendpunkt, um Interoperabilität mit [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Webdienstclients:  
  
-   Verwenden Sie den <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>-Typ als Bindungstyp für den Dienstendpunkt.  
  
-   Verwenden Sie für den Dienstendpunkt keine Rückruf- und Sitzungsvertragsfunktionen oder Transaktionsverhalten.  
  
 Sie können für die Bindung auch Unterstützung für HTTPS und Clientauthentifizierung auf Transportebene aktivieren.  
  
 Die folgenden Funktionen der <xref:System.ServiceModel.BasicHttpBinding>-Klasse erfordern Funktionalität jenseits von WS-I Basic Profiles 1.1:  
  
-   MTOM-Meldungscodierung (Message Transmission Optimization Mechanism), die von der <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>-Eigenschaft gesteuert wird. Behalten Sie für diese Eigenschaft den Standardwert bei, der <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> ist, was bedeutet, dass kein MTOM verwendet wird.  
  
-   Meldungssicherheit, die vom <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType>-Wert gesteuert wird, stellt WS-Sicherheit bereit, die mit WS-I Basic Security Profile 1.0 kompatibel ist. Behalten Sie für diese Eigenschaft den Standardwert <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> bei, d. h. es wird keine WS-Sicherheit verwendet.  
  
 Um die Metadaten für einen WCF-Dienst verfügbar zu machen [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], verwenden Sie die Web Service-Generation-Clienttools: [Web Services Description Language Tool (Wsdl.exe)](https://msdn.microsoft.com/library/b9210348-8bc2-4367-8c91-d1a04b403e88), [Web Services Discovery Tool (Disco.exe)](https://msdn.microsoft.com/library/acd88078-c581-42bc-94ca-6633e2851979), und die `Add Web Reference` Features in Visual Studio; Sie müssen die Metadatenveröffentlichung aktivieren. Weitere Informationen finden Sie unter [Veröffentlichen von Metadatenendpunkten](../../../docs/framework/wcf/publishing-metadata-endpoints.md).  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Der folgende Beispielcode veranschaulicht, wie einen WCF-Endpunkt hinzufügen, die kompatibel mit [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] -Webdienstclients, die im Code und Alternativ in einer Konfigurationsdatei.  
  
### <a name="code"></a>Code  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [Interoperabilität mit ASP.NET-Webdiensten](../../../docs/framework/wcf/feature-details/interop-with-aspnet-web-services.md)

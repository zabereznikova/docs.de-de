---
title: Erstellen von interoperablen WS-I Basic Profile 1.1-Diensten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
ms.openlocfilehash: b5d262c3e0443503ccbf49a1a468c82843799a61
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255051"
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a><span data-ttu-id="70000-102">Erstellen von interoperablen WS-I Basic Profile 1.1-Diensten</span><span class="sxs-lookup"><span data-stu-id="70000-102">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>

<span data-ttu-id="70000-103">So konfigurieren Sie einen WCF-Dienst Endpunkt so, dass er mit ASP.NET-Webdienst Clients interoperabel ist:</span><span class="sxs-lookup"><span data-stu-id="70000-103">To configure a WCF service endpoint to be interoperable with ASP.NET Web service clients:</span></span>  
  
- <span data-ttu-id="70000-104">Verwenden Sie den <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>-Typ als Bindungstyp für den Dienstendpunkt.</span><span class="sxs-lookup"><span data-stu-id="70000-104">Use the <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> type as the binding type for your service endpoint.</span></span>  
  
- <span data-ttu-id="70000-105">Verwenden Sie für den Dienstendpunkt keine Rückruf- und Sitzungsvertragsfunktionen oder Transaktionsverhalten.</span><span class="sxs-lookup"><span data-stu-id="70000-105">Do not use callback and session contract features or transaction behaviors on your service endpoint</span></span>  
  
<span data-ttu-id="70000-106">Sie können für die Bindung auch Unterstützung für HTTPS und Clientauthentifizierung auf Transportebene aktivieren.</span><span class="sxs-lookup"><span data-stu-id="70000-106">You can optionally enable support for HTTPS and transport-level client authentication on the binding.</span></span>  
  
<span data-ttu-id="70000-107">Die folgenden Funktionen der <xref:System.ServiceModel.BasicHttpBinding>-Klasse erfordern Funktionalität jenseits von WS-I Basic Profiles 1.1:</span><span class="sxs-lookup"><span data-stu-id="70000-107">The following features of the <xref:System.ServiceModel.BasicHttpBinding> class require functionality beyond WS-I Basic Profile 1.1:</span></span>  
  
- <span data-ttu-id="70000-108">MTOM-Meldungscodierung (Message Transmission Optimization Mechanism), die von der <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>-Eigenschaft gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="70000-108">Message Transmission Optimization Mechanism (MTOM) message encoding controlled by the <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="70000-109">Behalten Sie für diese Eigenschaft den Standardwert bei, der <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> ist, was bedeutet, dass kein MTOM verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="70000-109">Leave  this property at its default value, which is <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> to not use MTOM.</span></span>  
  
- <span data-ttu-id="70000-110">Meldungssicherheit, die vom <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType>-Wert gesteuert wird, stellt WS-Sicherheit bereit, die mit WS-I Basic Security Profile 1.0 kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="70000-110">Message security controlled by the <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> value provides WS-Security support compliant with WS-I Basic Security Profile 1.0.</span></span> <span data-ttu-id="70000-111">Behalten Sie für diese Eigenschaft den Standardwert <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> bei, d. h. es wird keine WS-Sicherheit verwendet.</span><span class="sxs-lookup"><span data-stu-id="70000-111">Leave this property at its default value, which is <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> to not use WS-Security.</span></span>  
  
<span data-ttu-id="70000-112">Um die Metadaten für einen WCF-Dienst für ASP.net verfügbar zu machen, verwenden Sie das Tool Webdienst Client Generierungs Tools: [Web Services Description Language Tool (Wsdl.exe)](/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100)), [Web Services Discovery Tool (Disco.exe)](/previous-versions/dotnet/netframework-4.0/cy2a3ybs(v=vs.100))und das Feature **Webverweis hinzufügen** in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="70000-112">To make the metadata for a WCF service available to ASP.NET, use the Web service client generation tools: [Web Services Description Language Tool (Wsdl.exe)](/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100)), [Web Services Discovery Tool (Disco.exe)](/previous-versions/dotnet/netframework-4.0/cy2a3ybs(v=vs.100)), and the **Add Web Reference** feature in Visual Studio.</span></span> <span data-ttu-id="70000-113">Aktivieren Sie die Metadatenveröffentlichung.</span><span class="sxs-lookup"><span data-stu-id="70000-113">Enable metadata publication.</span></span> <span data-ttu-id="70000-114">Weitere Informationen finden Sie unter [Veröffentlichen von Metadatenendpunkten](publishing-metadata-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="70000-114">For more information, see [Publishing Metadata Endpoints](publishing-metadata-endpoints.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="70000-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70000-115">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="70000-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="70000-116">Description</span></span>  

 <span data-ttu-id="70000-117">Im folgenden Beispielcode wird veranschaulicht, wie ein WCF-Endpunkt, der mit ASP.NET-Webdienst Clients kompatibel ist, im Code und alternativ in einer Konfigurationsdatei hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="70000-117">The following example code demonstrates how to add a WCF endpoint that is compatible with ASP.NET Web service clients in code and, alternatively, in a configuration file.</span></span>  
  
### <a name="code"></a><span data-ttu-id="70000-118">Code</span><span class="sxs-lookup"><span data-stu-id="70000-118">Code</span></span>  

 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a><span data-ttu-id="70000-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70000-119">See also</span></span>

- [<span data-ttu-id="70000-120">Interoperabilität mit ASP.NET-Webdiensten</span><span class="sxs-lookup"><span data-stu-id="70000-120">Interoperability with ASP.NET Web Services</span></span>](./feature-details/interop-with-aspnet-web-services.md)

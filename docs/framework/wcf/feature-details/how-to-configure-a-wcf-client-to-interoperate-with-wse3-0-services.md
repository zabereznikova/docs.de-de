---
title: 'Vorgehensweise: Konfigurieren eines WCF-Clients für die Zusammenarbeit mit WSE3.0-Diensten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
ms.openlocfilehash: 0136fa7c3a51a7d64340c6251e9f5eb63017ffd4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220694"
---
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a><span data-ttu-id="ba960-102">Vorgehensweise: Konfigurieren eines WCF-Clients für die Zusammenarbeit mit WSE3.0-Diensten</span><span class="sxs-lookup"><span data-stu-id="ba960-102">How to: Configure a WCF Client to interoperate with WSE3.0 Services</span></span>
<span data-ttu-id="ba960-103">Windows Communication Foundation (WCF)-Clients sind auf niedriger Ebene mit Web Services Enhancements 3.0 für Dienste von Microsoft .NET (WSE) kompatibel, wenn WCF-Clients konfiguriert werden, um die Version vom August 2004 von WS-Addressing-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="ba960-103">Windows Communication Foundation (WCF) clients are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) services when WCF clients are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a><span data-ttu-id="ba960-104">So konfigurieren Sie einen WCF-Client für die Zusammenarbeit mit einem WSE3.0-Webdienst</span><span class="sxs-lookup"><span data-stu-id="ba960-104">To configure a WCF client to interoperate with a WSE 3.0 Web service</span></span>  
  
1.  <span data-ttu-id="ba960-105">Führen Sie die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) beim Erstellen eines WCF-Clients für den WSE 3.0-Webdienst.</span><span class="sxs-lookup"><span data-stu-id="ba960-105">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a WCF client for the WSE 3.0 Web service.</span></span>  
  
     <span data-ttu-id="ba960-106">Für einen WSE-Webdienst wird eine WCF-Clientklasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="ba960-106">For a WSE Web service, a WCF client class is created.</span></span>  
  
     <span data-ttu-id="ba960-107">Weitere Informationen zum Erstellen eines WCF-Clients finden Sie unter den [Vorgehensweise: Erstellen Sie einen Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="ba960-107">For details about creating a WCF client, see the [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
2.  <span data-ttu-id="ba960-108">Erstellen Sie eine Klasse, die eine Bindung darstellt, die mit WSE 3.0-Webdiensten kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="ba960-108">Create a class that represents a binding that can communicate with WSE 3.0 Web services.</span></span>  
  
     <span data-ttu-id="ba960-109">Die folgende Klasse ist Teil der [interoperieren mit WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ba960-109">The following class is part of the [Interoperating with WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29) sample.</span></span>  
  
    1.  <span data-ttu-id="ba960-110">Erstellen Sie eine von der <xref:System.ServiceModel.Channels.Binding>-Klasse abgeleitete Klasse.</span><span class="sxs-lookup"><span data-stu-id="ba960-110">Create a class that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         <span data-ttu-id="ba960-111">Der folgende Code erstellt eine Klasse mit dem Namen `WseHttpBinding`, die von der <xref:System.ServiceModel.Channels.Binding>-Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="ba960-111">The following code example creates a class named `WseHttpBinding` that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  <span data-ttu-id="ba960-112">Fügen Sie der Klasse Eigenschaften hinzu, die die sofort verwendbare WSE-Assertion festlegen. Hierzu gehört, ob abgeleitete Schlüssel erforderlich sind, ob Sicherheitssitzungen zum Einsatz kommen, ob Signaturbestätigungen erforderlich sind sowie die Einstellungen für den Nachrichtenschutz.</span><span class="sxs-lookup"><span data-stu-id="ba960-112">Add properties to the class that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings.</span></span>  
  
         <span data-ttu-id="ba960-113">Das folgende Codebeispiel definiert die `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext`, und `MessageProtectionOrder` Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="ba960-113">The following code example defines the `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext`, and `MessageProtectionOrder` properties.</span></span> <span data-ttu-id="ba960-114">Sie geben die sofort verwendbare WSE-Assertion, gibt an, ob abgeleitete Schlüssel erforderlich sind, gibt an, ob sicherheitssitzungen zum Einsatz kommen, ob signaturbestätigungen erforderlich sind und die Einstellungen für den.</span><span class="sxs-lookup"><span data-stu-id="ba960-114">They specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings, respectively.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  <span data-ttu-id="ba960-115">Überschreiben Sie die <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A>-Methode, um die Bindungseigenschaften einzurichten.</span><span class="sxs-lookup"><span data-stu-id="ba960-115">Override the <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> method to set the binding properties.</span></span>  
  
         <span data-ttu-id="ba960-116">Das folgende Codebeispiel legt die Einstellungen für Transport, Nachrichtencodierung und Nachrichtenschutz fest, indem die Werte für `SecurityAssertion` und die `MessageProtectionOrder`-Eigenschaften abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ba960-116">The following code example specifies the transport, message encoding, and message protection settings by getting the values of the `SecurityAssertion` and `MessageProtectionOrder` properties.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  <span data-ttu-id="ba960-117">Fügen Sie im Clientanwendungscode Code hinzu, um die Bindungseigenschaften festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ba960-117">In the client application code, add code to set the binding properties.</span></span>  
  
     <span data-ttu-id="ba960-118">Das folgende Codebeispiel gibt an, dass der WCF-Client Nachrichtenschutz und -Authentifizierung verwenden muss, gemäß der WSE 3.0 `AnonymousForCertificate` sicherheitsassertion.</span><span class="sxs-lookup"><span data-stu-id="ba960-118">The following code example specifies that the WCF client must use message protection and authentication as defined by the WSE 3.0 `AnonymousForCertificate` turnkey security assertion.</span></span> <span data-ttu-id="ba960-119">Darüber hinaus sind Sicherheitssitzungen und abgeleitete Schlüssel erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ba960-119">Additionally, secure sessions and derived keys are required.</span></span>  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="ba960-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ba960-120">Example</span></span>  
 <span data-ttu-id="ba960-121">Das folgende Codebeispiel definiert eine benutzerdefinierte Bindung, die Eigenschaften offenlegt, die mit den Eigenschaften der sofort verwendbaren WSE 3.0-Sicherheitsassertion übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="ba960-121">The following code example defines a custom binding that exposes properties that correspond to the properties of a WSE 3.0 turnkey security assertion.</span></span> <span data-ttu-id="ba960-122">Die benutzerdefinierte Bindung, mit dem Namen `WseHttpBinding`, dann verwendet, um die Bindungseigenschaften für einen WCF-Client anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ba960-122">The custom binding, which is named `WseHttpBinding`, is then used to specify the binding properties for a WCF client.</span></span>  

[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="ba960-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba960-123">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- [<span data-ttu-id="ba960-124">Interoperieren mit WSE</span><span class="sxs-lookup"><span data-stu-id="ba960-124">Interoperating with WSE</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29)

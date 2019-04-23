---
title: 'Vorgehensweise: Konfigurieren eines lokalen Ausstellers'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 15263371-514e-4ea6-90fb-14b4939154cd
ms.openlocfilehash: 46dbb39a31a1ef256bef0f5b7e1bbc41ce1eca3e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59306988"
---
# <a name="how-to-configure-a-local-issuer"></a><span data-ttu-id="1590e-102">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="1590e-102">How to: Configure a Local Issuer</span></span>
<span data-ttu-id="1590e-103">In diesem Thema wird beschrieben, wie Sie einen Client für die Verwendung eines lokalen Ausstellers für ausgestellte Token konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1590e-103">This topic describes how to configure a client to use a local issuer for issued tokens.</span></span>  
  
 <span data-ttu-id="1590e-104">Wenn ein Client mit einem Verbunddienst kommuniziert, wird vom Dienst die Adresse des Sicherheitstokendiensts angegeben, der das Token ausgeben soll, das vom Client für die Authentifizierung am Verbunddienst verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1590e-104">Often, when a client communicates with a federated service, the service specifies the address of the security token service that is expected to issue the token the client will use to authenticate itself to the federated service.</span></span> <span data-ttu-id="1590e-105">In bestimmten Situationen kann der Client konfiguriert werden um verwenden eine *lokalen Ausstellers*.</span><span class="sxs-lookup"><span data-stu-id="1590e-105">In certain situations, the client may be configured to use a *local issuer*.</span></span>  
  
 <span data-ttu-id="1590e-106">Windows Communication Foundation (WCF) verwendet einen lokalen Aussteller in Fällen, in denen die Ausstelleradresse einer verbundbindung `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` oder `null`.</span><span class="sxs-lookup"><span data-stu-id="1590e-106">Windows Communication Foundation (WCF) uses a local issuer in cases where the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`.</span></span> <span data-ttu-id="1590e-107">In diesem Fall müssen Sie <xref:System.ServiceModel.Description.ClientCredentials> mit der Adresse des lokalen Ausstellers und der für die Kommunikation mit diesem Aussteller zu verwendenden Bindung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1590e-107">In such cases, you must configure the <xref:System.ServiceModel.Description.ClientCredentials> with the address of the local issuer and the binding to use to communicate with that issuer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1590e-108">Wenn die <xref:System.ServiceModel.Description.ClientCredentials.SupportInteractive%2A> Eigenschaft der `ClientCredentials` -Klasse festgelegt, dass `true`keine lokale Ausstelleradresse angegeben ist und die Ausstelleradresse angegeben wird, durch die [ \<WsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) oder andere verbundbindung `http://schemas.xmlsoap.org/ws/2005/05/identity/issuer/self`, `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous`, oder `null`, klicken Sie dann die Windows [!INCLUDE[infocard](../../../../includes/infocard-md.md)] Aussteller verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1590e-108">If the <xref:System.ServiceModel.Description.ClientCredentials.SupportInteractive%2A> property of the `ClientCredentials` class is set to `true`, a local issuer address is not specified, and the issuer address specified by the [\<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) or other federated binding is `http://schemas.xmlsoap.org/ws/2005/05/identity/issuer/self`, `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous`, or is `null`, then the Windows [!INCLUDE[infocard](../../../../includes/infocard-md.md)] issuer is used.</span></span>  
  
### <a name="to-configure-the-local-issuer-in-code"></a><span data-ttu-id="1590e-109">So konfigurieren Sie den lokalen Aussteller im Code</span><span class="sxs-lookup"><span data-stu-id="1590e-109">To configure the local issuer in code</span></span>  
  
1. <span data-ttu-id="1590e-110">Erstellen Sie eine Variable vom Typ <xref:System.ServiceModel.Security.IssuedTokenClientCredential>.</span><span class="sxs-lookup"><span data-stu-id="1590e-110">Create a variable of type <xref:System.ServiceModel.Security.IssuedTokenClientCredential></span></span>  
  
2. <span data-ttu-id="1590e-111">Legen Sie die Variable der Instanz fest, die von der <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>-Eigenschaft der `ClientCredentials`-Klasse zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1590e-111">Set the variable to the instance returned from the <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> property of the `ClientCredentials` class.</span></span> <span data-ttu-id="1590e-112">Diese Instanz wird von der <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>-Eigenschaft des Clients (geerbt von <xref:System.ServiceModel.ClientBase%601>) oder der <xref:System.ServiceModel.ChannelFactory.Credentials%2A>-Eigenschaft der <xref:System.ServiceModel.ChannelFactory> zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="1590e-112">That instance is returned by the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the client (inherited from <xref:System.ServiceModel.ClientBase%601>) or the <xref:System.ServiceModel.ChannelFactory.Credentials%2A> property of the <xref:System.ServiceModel.ChannelFactory>:</span></span>  
  
     [!code-csharp[c_CreateSTS#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#9)]
     [!code-vb[c_CreateSTS#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#9)]  
  
3. <span data-ttu-id="1590e-113">Legen Sie die <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A>-Eigenschaft auf eine neue Instanz der <xref:System.ServiceModel.EndpointAddress> fest, wobei die Adresse des lokalen Ausstellers als Argument für den Konstruktor verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1590e-113">Set the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A> property to a new instance of the <xref:System.ServiceModel.EndpointAddress>, with the address of the local issuer as an argument to the constructor.</span></span>  
  
     [!code-csharp[c_CreateSTS#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#10)]
     [!code-vb[c_CreateSTS#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#10)]  
  
     <span data-ttu-id="1590e-114">Sie können auch eine neue <xref:System.Uri>-Instanz als Argument für den Konstruktor erstellen.</span><span class="sxs-lookup"><span data-stu-id="1590e-114">Alternatively, create a new <xref:System.Uri> instance as an argument to the constructor.</span></span>  
  
     [!code-csharp[c_CreateSTS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#11)]
     [!code-vb[c_CreateSTS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#11)]  
  
     <span data-ttu-id="1590e-115">Die `addressHeaders` -Parameter ist ein Array von <xref:System.ServiceModel.Channels.AddressHeader> Instanzen, wie hier gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1590e-115">The `addressHeaders` parameter is an array of <xref:System.ServiceModel.Channels.AddressHeader> instances, as shown.</span></span>  
  
     [!code-csharp[c_CreateSTS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#12)]
     [!code-vb[c_CreateSTS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#12)]  
  
4. <span data-ttu-id="1590e-116">Legen Sie die Bindung für den lokalen Aussteller mit der <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1590e-116">Set the binding for the local issuer using the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A> property.</span></span>  
  
     [!code-csharp[c_CreateSTS#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#13)]
     [!code-vb[c_CreateSTS#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#13)]  
  
5. <span data-ttu-id="1590e-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="1590e-117">Optional.</span></span> <span data-ttu-id="1590e-118">Fügen Sie die konfigurierten Endpunktverhalten für den lokalen Aussteller hinzu, indem Sie solche Verhalten der Auflistung hinzufügen, die von der <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A>-Eigenschaft zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1590e-118">Add configured endpoint behaviors for the local issuer by adding such behaviors to the collection returned by the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A> property.</span></span>  
  
     [!code-csharp[c_CreateSTS#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#14)]
     [!code-vb[c_CreateSTS#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#14)]  
  
### <a name="to-configure-the-local-issuer-in-configuration"></a><span data-ttu-id="1590e-119">So konfigurieren Sie den lokalen Aussteller in der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="1590e-119">To configure the local issuer in configuration</span></span>  
  
1. <span data-ttu-id="1590e-120">Erstellen einer [ \<LocalIssuer >](../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md) Element als untergeordnetes Element der [ \<IssuedToken >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) -Element, das selbst untergeordnet ist die [ \<ClientCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) Element in einem Endpunktverhalten darstellt.</span><span class="sxs-lookup"><span data-stu-id="1590e-120">Create a [\<localIssuer>](../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md) element as a child of the [\<issuedToken>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) element that is itself a child of the [\<clientCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element in an endpoint behavior.</span></span>  
  
2. <span data-ttu-id="1590e-121">Legen Sie das `address`-Attribut auf die Adresse des lokalen Ausstellers fest, der Tokenanforderungen annimmt.</span><span class="sxs-lookup"><span data-stu-id="1590e-121">Set the `address` attribute to the address of the local issuer that will accept token requests.</span></span>  
  
3. <span data-ttu-id="1590e-122">Legen Sie das `binding`-Attribut und das `bindingConfiguration`-Attribut auf Werte fest, mit denen die für die Kommunikation mit dem lokalen Ausstellerendpunkt geeignete Bindung referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="1590e-122">Set the `binding` and `bindingConfiguration` attributes to values that reference the appropriate binding to use when communicating with the local issuer endpoint.</span></span>  
  
4. <span data-ttu-id="1590e-123">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="1590e-123">Optional.</span></span> <span data-ttu-id="1590e-124">Legen Sie die [ \<Identität >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) Element als untergeordnetes Element der <`localIssuer`> Element, und geben Sie Identitätsinformationen für den lokalen Aussteller.</span><span class="sxs-lookup"><span data-stu-id="1590e-124">Set the [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) element as a child of the <`localIssuer`> element and specify identity information for the local issuer.</span></span>  
  
5. <span data-ttu-id="1590e-125">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="1590e-125">Optional.</span></span> <span data-ttu-id="1590e-126">Festlegen der [ \<Header >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) Element als untergeordnetes Element der <`localIssuer`> Element, und geben Sie zusätzliche Header, die erforderlich sind, um zu den lokalen Aussteller ordnungsgemäß zu adressieren.</span><span class="sxs-lookup"><span data-stu-id="1590e-126">Set the [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) element as a child of the <`localIssuer`> element and specify additional headers that are required in order to correctly address the local issuer.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1590e-127">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1590e-127">.NET Framework Security</span></span>  
 <span data-ttu-id="1590e-128">Beachten Sie, dass beim Angeben einer Ausstelleradresse und einer Ausstellerbindung für eine bestimmte Bindung nicht der lokale Aussteller für Endpunkte verwendet wird, die diese Bindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="1590e-128">Note that if an issuer address and binding are specified for a given binding, the local issuer is not used for endpoints that use that binding.</span></span> <span data-ttu-id="1590e-129">Clients, die immer den lokalen Aussteller verwenden möchten, sollten sicherstellen, dass keine solche Bindung verwendet wird oder dass die Bindung so geändert wird, dass die Ausstelleradresse `null` lautet.</span><span class="sxs-lookup"><span data-stu-id="1590e-129">Clients who expect to always use the local issuer should ensure that they do not use such a binding or that they modify the binding so that the issuer address is `null`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1590e-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1590e-130">See also</span></span>

- [<span data-ttu-id="1590e-131">Vorgehensweise: Konfigurieren von Anmeldeinformationen für einen Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="1590e-131">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="1590e-132">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="1590e-132">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="1590e-133">Vorgehensweise: Erstellen einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="1590e-133">How to: Create a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)

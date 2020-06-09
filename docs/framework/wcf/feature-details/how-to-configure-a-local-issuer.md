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
ms.openlocfilehash: 7da3cd34d0840eea48c9ef0bb89fb6580b87623b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601243"
---
# <a name="how-to-configure-a-local-issuer"></a><span data-ttu-id="580a0-102">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="580a0-102">How to: Configure a Local Issuer</span></span>

<span data-ttu-id="580a0-103">In diesem Thema wird beschrieben, wie Sie einen Client für die Verwendung eines lokalen Ausstellers für ausgestellte Token konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="580a0-103">This topic describes how to configure a client to use a local issuer for issued tokens.</span></span>

<span data-ttu-id="580a0-104">Wenn ein Client mit einem Verbunddienst kommuniziert, wird vom Dienst die Adresse des Sicherheitstokendiensts angegeben, der das Token ausgeben soll, das vom Client für die Authentifizierung am Verbunddienst verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="580a0-104">Often, when a client communicates with a federated service, the service specifies the address of the security token service that is expected to issue the token the client will use to authenticate itself to the federated service.</span></span> <span data-ttu-id="580a0-105">In bestimmten Situationen kann der Client für die Verwendung eines *lokalen Ausstellers*konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="580a0-105">In certain situations, the client may be configured to use a *local issuer*.</span></span>

<span data-ttu-id="580a0-106">Windows Communication Foundation (WCF) verwendet einen lokalen Aussteller in Fällen, in denen die Aussteller Adresse einer Verbund Bindung `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` oder ist `null` .</span><span class="sxs-lookup"><span data-stu-id="580a0-106">Windows Communication Foundation (WCF) uses a local issuer in cases where the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`.</span></span> <span data-ttu-id="580a0-107">In diesem Fall müssen Sie <xref:System.ServiceModel.Description.ClientCredentials> mit der Adresse des lokalen Ausstellers und der für die Kommunikation mit diesem Aussteller zu verwendenden Bindung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="580a0-107">In such cases, you must configure the <xref:System.ServiceModel.Description.ClientCredentials> with the address of the local issuer and the binding to use to communicate with that issuer.</span></span>

> [!NOTE]
> <span data-ttu-id="580a0-108">Wenn die- <xref:System.ServiceModel.Description.ClientCredentials.SupportInteractive%2A> Eigenschaft der- `ClientCredentials` Klasse auf festgelegt ist `true` , eine lokale Aussteller Adresse nicht angegeben ist und die von der oder einer anderen Verbund Bindung angegebene Aussteller Adresse ist, [\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md) `http://schemas.xmlsoap.org/ws/2005/05/identity/issuer/self` `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` oder ist `null` , dann wird der Windows CardSpace-Aussteller verwendet.</span><span class="sxs-lookup"><span data-stu-id="580a0-108">If the <xref:System.ServiceModel.Description.ClientCredentials.SupportInteractive%2A> property of the `ClientCredentials` class is set to `true`, a local issuer address is not specified, and the issuer address specified by the [\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md) or other federated binding is `http://schemas.xmlsoap.org/ws/2005/05/identity/issuer/self`, `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous`, or is `null`, then the Windows CardSpace issuer is used.</span></span>

## <a name="to-configure-the-local-issuer-in-code"></a><span data-ttu-id="580a0-109">So konfigurieren Sie den lokalen Aussteller im Code</span><span class="sxs-lookup"><span data-stu-id="580a0-109">To configure the local issuer in code</span></span>

1. <span data-ttu-id="580a0-110">Erstellen Sie eine Variable vom Typ <xref:System.ServiceModel.Security.IssuedTokenClientCredential>.</span><span class="sxs-lookup"><span data-stu-id="580a0-110">Create a variable of type <xref:System.ServiceModel.Security.IssuedTokenClientCredential></span></span>

2. <span data-ttu-id="580a0-111">Legen Sie die Variable der Instanz fest, die von der <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>-Eigenschaft der `ClientCredentials`-Klasse zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="580a0-111">Set the variable to the instance returned from the <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> property of the `ClientCredentials` class.</span></span> <span data-ttu-id="580a0-112">Diese Instanz wird von der <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>-Eigenschaft des Clients (geerbt von <xref:System.ServiceModel.ClientBase%601>) oder der <xref:System.ServiceModel.ChannelFactory.Credentials%2A>-Eigenschaft der <xref:System.ServiceModel.ChannelFactory> zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="580a0-112">That instance is returned by the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the client (inherited from <xref:System.ServiceModel.ClientBase%601>) or the <xref:System.ServiceModel.ChannelFactory.Credentials%2A> property of the <xref:System.ServiceModel.ChannelFactory>:</span></span>

     [!code-csharp[c_CreateSTS#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#9)]
     [!code-vb[c_CreateSTS#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#9)]

3. <span data-ttu-id="580a0-113">Legen Sie die <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A>-Eigenschaft auf eine neue Instanz der <xref:System.ServiceModel.EndpointAddress> fest, wobei die Adresse des lokalen Ausstellers als Argument für den Konstruktor verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="580a0-113">Set the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A> property to a new instance of the <xref:System.ServiceModel.EndpointAddress>, with the address of the local issuer as an argument to the constructor.</span></span>

     [!code-csharp[c_CreateSTS#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#10)]
     [!code-vb[c_CreateSTS#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#10)]

     <span data-ttu-id="580a0-114">Sie können auch eine neue <xref:System.Uri>-Instanz als Argument für den Konstruktor erstellen.</span><span class="sxs-lookup"><span data-stu-id="580a0-114">Alternatively, create a new <xref:System.Uri> instance as an argument to the constructor.</span></span>

     [!code-csharp[c_CreateSTS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#11)]
     [!code-vb[c_CreateSTS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#11)]

     <span data-ttu-id="580a0-115">Der- `addressHeaders` Parameter ist ein Array von- <xref:System.ServiceModel.Channels.AddressHeader> Instanzen, wie gezeigt.</span><span class="sxs-lookup"><span data-stu-id="580a0-115">The `addressHeaders` parameter is an array of <xref:System.ServiceModel.Channels.AddressHeader> instances, as shown.</span></span>

     [!code-csharp[c_CreateSTS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#12)]
     [!code-vb[c_CreateSTS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#12)]

4. <span data-ttu-id="580a0-116">Legen Sie die Bindung für den lokalen Aussteller mithilfe der- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A> Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="580a0-116">Set the binding for the local issuer using the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A> property.</span></span>

     [!code-csharp[c_CreateSTS#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#13)]
     [!code-vb[c_CreateSTS#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#13)]

5. <span data-ttu-id="580a0-117">Optional.</span><span class="sxs-lookup"><span data-stu-id="580a0-117">Optional.</span></span> <span data-ttu-id="580a0-118">Fügen Sie die konfigurierten Endpunktverhalten für den lokalen Aussteller hinzu, indem Sie solche Verhalten der Auflistung hinzufügen, die von der <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A>-Eigenschaft zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="580a0-118">Add configured endpoint behaviors for the local issuer by adding such behaviors to the collection returned by the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A> property.</span></span>

     [!code-csharp[c_CreateSTS#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#14)]
     [!code-vb[c_CreateSTS#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#14)]

## <a name="to-configure-the-local-issuer-in-configuration"></a><span data-ttu-id="580a0-119">So konfigurieren Sie den lokalen Aussteller in der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="580a0-119">To configure the local issuer in configuration</span></span>

1. <span data-ttu-id="580a0-120">Erstellen Sie ein- [\<localIssuer>](../../configure-apps/file-schema/wcf/localissuer.md) Element als untergeordnetes [\<issuedToken>](../../configure-apps/file-schema/wcf/issuedtoken.md) Element des-Elements, das selbst ein untergeordnetes Element des- [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md) Elements in einem Endpunkt Verhalten ist.</span><span class="sxs-lookup"><span data-stu-id="580a0-120">Create a [\<localIssuer>](../../configure-apps/file-schema/wcf/localissuer.md) element as a child of the [\<issuedToken>](../../configure-apps/file-schema/wcf/issuedtoken.md) element that is itself a child of the [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md) element in an endpoint behavior.</span></span>

2. <span data-ttu-id="580a0-121">Legen Sie das `address`-Attribut auf die Adresse des lokalen Ausstellers fest, der Tokenanforderungen annimmt.</span><span class="sxs-lookup"><span data-stu-id="580a0-121">Set the `address` attribute to the address of the local issuer that will accept token requests.</span></span>

3. <span data-ttu-id="580a0-122">Legen Sie das `binding`-Attribut und das `bindingConfiguration`-Attribut auf Werte fest, mit denen die für die Kommunikation mit dem lokalen Ausstellerendpunkt geeignete Bindung referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="580a0-122">Set the `binding` and `bindingConfiguration` attributes to values that reference the appropriate binding to use when communicating with the local issuer endpoint.</span></span>

4. <span data-ttu-id="580a0-123">Optional.</span><span class="sxs-lookup"><span data-stu-id="580a0-123">Optional.</span></span> <span data-ttu-id="580a0-124">Legen Sie das [\<identity>](../../configure-apps/file-schema/wcf/identity.md) -Element als untergeordnetes Element des <`localIssuer`>-Elements fest, und geben Sie Identitätsinformationen für den lokalen Aussteller an.</span><span class="sxs-lookup"><span data-stu-id="580a0-124">Set the [\<identity>](../../configure-apps/file-schema/wcf/identity.md) element as a child of the <`localIssuer`> element and specify identity information for the local issuer.</span></span>

5. <span data-ttu-id="580a0-125">Optional.</span><span class="sxs-lookup"><span data-stu-id="580a0-125">Optional.</span></span> <span data-ttu-id="580a0-126">Legen [\<headers>](../../configure-apps/file-schema/wcf/headers.md) Sie das-Element als untergeordnetes Element des <`localIssuer`> Elements fest, und geben Sie zusätzliche Header an, die erforderlich sind, um den lokalen Aussteller ordnungsgemäß zu adressieren.</span><span class="sxs-lookup"><span data-stu-id="580a0-126">Set the [\<headers>](../../configure-apps/file-schema/wcf/headers.md) element as a child of the <`localIssuer`> element and specify additional headers that are required in order to correctly address the local issuer.</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="580a0-127">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="580a0-127">.NET Framework Security</span></span>

<span data-ttu-id="580a0-128">Beachten Sie, dass beim Angeben einer Ausstelleradresse und einer Ausstellerbindung für eine bestimmte Bindung nicht der lokale Aussteller für Endpunkte verwendet wird, die diese Bindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="580a0-128">Note that if an issuer address and binding are specified for a given binding, the local issuer is not used for endpoints that use that binding.</span></span> <span data-ttu-id="580a0-129">Clients, die immer den lokalen Aussteller verwenden möchten, sollten sicherstellen, dass keine solche Bindung verwendet wird oder dass die Bindung so geändert wird, dass die Ausstelleradresse `null` lautet.</span><span class="sxs-lookup"><span data-stu-id="580a0-129">Clients who expect to always use the local issuer should ensure that they do not use such a binding or that they modify the binding so that the issuer address is `null`.</span></span>

## <a name="see-also"></a><span data-ttu-id="580a0-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="580a0-130">See also</span></span>

- [<span data-ttu-id="580a0-131">Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="580a0-131">How to: Configure Credentials on a Federation Service</span></span>](how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="580a0-132">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="580a0-132">How to: Create a Federated Client</span></span>](how-to-create-a-federated-client.md)
- [<span data-ttu-id="580a0-133">Vorgehensweise: Erstellen einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="580a0-133">How to: Create a WSFederationHttpBinding</span></span>](how-to-create-a-wsfederationhttpbinding.md)

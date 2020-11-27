---
title: 'Vorgehensweise: Erstellen einer benutzerdefinierten Clientidentitätsüberprüfung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f2d34e43-fa8b-46d2-91cf-d2960e13e16b
ms.openlocfilehash: 84982aca06bacb5718855602872fe4dab2376a9d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256065"
---
# <a name="how-to-create-a-custom-client-identity-verifier"></a><span data-ttu-id="048eb-102">Vorgehensweise: Erstellen einer benutzerdefinierten Clientidentitätsüberprüfung</span><span class="sxs-lookup"><span data-stu-id="048eb-102">How to: Create a Custom Client Identity Verifier</span></span>

<span data-ttu-id="048eb-103">Mit der *Identity* -Funktion von Windows Communication Foundation (WCF) kann ein Client im Voraus die erwartete Identität des Dienstanbieter angeben.</span><span class="sxs-lookup"><span data-stu-id="048eb-103">The *identity* feature of Windows Communication Foundation (WCF) enables a client to specify in advance the expected identity of the service.</span></span> <span data-ttu-id="048eb-104">Bei jeder Authentifizierung eines Servers beim Client wird die Identität mit der erwarteten Identität verglichen.</span><span class="sxs-lookup"><span data-stu-id="048eb-104">Whenever a server authenticates itself to the client, the identity is checked against the expected identity.</span></span> <span data-ttu-id="048eb-105">(Eine Erläuterung der Identität und ihrer Funktionsweise finden Sie unter [Dienst Identität und-Authentifizierung](../feature-details/service-identity-and-authentication.md).)</span><span class="sxs-lookup"><span data-stu-id="048eb-105">(For an explanation of identity and how it works, see [Service Identity and Authentication](../feature-details/service-identity-and-authentication.md).)</span></span>  
  
 <span data-ttu-id="048eb-106">Sofern erforderlich, kann die Überprüfung mit einer benutzerdefinierten Identitätsüberprüfung angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="048eb-106">If needed, the verification can be customized using a custom identity verifier.</span></span> <span data-ttu-id="048eb-107">Zum Beispiel können Sie zusätzliche Dienstidentitätsüberprüfungen durchführen.</span><span class="sxs-lookup"><span data-stu-id="048eb-107">For example, you can perform additional service identity verification checks.</span></span> <span data-ttu-id="048eb-108">In diesem Beispiel überprüft die benutzerdefinierte Identitätsprüfung zusätzliche Ansprüche in dem X.509-Zertifikat, das vom Server zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="048eb-108">In this example, the custom identity verifier checks additional claims in the X.509 certificate returned from the server.</span></span> <span data-ttu-id="048eb-109">Eine Beispielanwendung finden Sie unter [Beispiel für Dienst Identität](../samples/service-identity-sample.md).</span><span class="sxs-lookup"><span data-stu-id="048eb-109">For a sample application, see [Service Identity Sample](../samples/service-identity-sample.md).</span></span>  
  
### <a name="to-extend-the-endpointidentity-class"></a><span data-ttu-id="048eb-110">So erweitern Sie die EndpointIdentity-Klasse:</span><span class="sxs-lookup"><span data-stu-id="048eb-110">To extend the EndpointIdentity class</span></span>  
  
1. <span data-ttu-id="048eb-111">Definieren Sie eine neue Klasse, die von der <xref:System.ServiceModel.EndpointIdentity>-Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="048eb-111">Define a new class that derives from the <xref:System.ServiceModel.EndpointIdentity> class.</span></span> <span data-ttu-id="048eb-112">In diesem Beispiel wird die Erweiterung `OrgEndpointIdentity` genannt.</span><span class="sxs-lookup"><span data-stu-id="048eb-112">This example names the extension `OrgEndpointIdentity`.</span></span>  
  
2. <span data-ttu-id="048eb-113">Fügen Sie private Member mit Eigenschaften hinzu, die von der erweiterten <xref:System.ServiceModel.Security.IdentityVerifier>-Klasse zum Ausführen der Identitätsprüfung anhand der Ansprüche im vom Dienst zurückgegebenen Sicherheitstoken verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="048eb-113">Add private members along with properties that will be used by the extended <xref:System.ServiceModel.Security.IdentityVerifier> class to perform the identity check against claims in the security token returned from the service.</span></span> <span data-ttu-id="048eb-114">Dieses Beispiel definiert eine Eigenschaft: die `OrganizationClaim`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="048eb-114">This example defines one property: the `OrganizationClaim` property.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#6)]
     [!code-vb[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#6)]  
  
### <a name="to-extend-the-identityverifier-class"></a><span data-ttu-id="048eb-115">So erweitern Sie die IdentityVerifier-Klasse:</span><span class="sxs-lookup"><span data-stu-id="048eb-115">To extend the IdentityVerifier class</span></span>  
  
1. <span data-ttu-id="048eb-116">Definieren Sie eine neue Klasse, die von <xref:System.ServiceModel.Security.IdentityVerifier> abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="048eb-116">Define a new class that derives from <xref:System.ServiceModel.Security.IdentityVerifier>.</span></span> <span data-ttu-id="048eb-117">In diesem Beispiel wird die Erweiterung `CustomIdentityVerifier` genannt.</span><span class="sxs-lookup"><span data-stu-id="048eb-117">This example names the extension `CustomIdentityVerifier`.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#7)]
     [!code-vb[c_HowToSetCustomClientIdentity#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#7)]  
  
2. <span data-ttu-id="048eb-118">Überschreiben Sie die <xref:System.ServiceModel.Security.IdentityVerifier.CheckAccess%2A> -Methode.</span><span class="sxs-lookup"><span data-stu-id="048eb-118">Override the <xref:System.ServiceModel.Security.IdentityVerifier.CheckAccess%2A> method.</span></span> <span data-ttu-id="048eb-119">Mit dieser Methode wird bestimmt, ob die Identitätsprüfung erfolgreich war oder fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="048eb-119">The method determines whether the identity check succeeded or failed.</span></span>  
  
3. <span data-ttu-id="048eb-120">Die `CheckAccess`-Methode verfügt über zwei Parameter.</span><span class="sxs-lookup"><span data-stu-id="048eb-120">The `CheckAccess` method has two parameters.</span></span> <span data-ttu-id="048eb-121">Der erste Parameter ist eine Instanz der <xref:System.ServiceModel.EndpointIdentity>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="048eb-121">The first is an instance of the <xref:System.ServiceModel.EndpointIdentity> class.</span></span> <span data-ttu-id="048eb-122">Der zweite Parameter ist eine Instanz der <xref:System.IdentityModel.Policy.AuthorizationContext>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="048eb-122">The second is an instance of the <xref:System.IdentityModel.Policy.AuthorizationContext> class.</span></span>  
  
     <span data-ttu-id="048eb-123">Prüfen Sie in der Methodenimplementierung die Auflistung der von der <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A>-Eigenschaft der <xref:System.IdentityModel.Policy.AuthorizationContext>-Klasse zurückgegebenen Ansprüche, und führen Sie gemäß Bedarf Authentifizierungsprüfungen aus.</span><span class="sxs-lookup"><span data-stu-id="048eb-123">In the method implementation, examine the collection of claims returned by the <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> property of the <xref:System.IdentityModel.Policy.AuthorizationContext> class, and perform authentication checks as required.</span></span> <span data-ttu-id="048eb-124">Dieses Beispiel beginnt durch Suchen eines Anspruchs vom Typ "Distinguished Name" und anschließendes Vergleichen des Namens mit der Erweiterung von <xref:System.ServiceModel.EndpointIdentity> (`OrgEndpointIdentity`).</span><span class="sxs-lookup"><span data-stu-id="048eb-124">This example begins by finding any claim that is of type "Distinguished Name" and then compares the name to the extension of the <xref:System.ServiceModel.EndpointIdentity> (`OrgEndpointIdentity`).</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#1)]
     [!code-vb[c_HowToSetCustomClientIdentity#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#1)]  
  
### <a name="to-implement-the-trygetidentity-method"></a><span data-ttu-id="048eb-125">So implementieren Sie die TryGetIdentity-Methode:</span><span class="sxs-lookup"><span data-stu-id="048eb-125">To implement the TryGetIdentity method</span></span>  
  
1. <span data-ttu-id="048eb-126">Implementieren Sie die <xref:System.ServiceModel.Security.IdentityVerifier.TryGetIdentity%2A>-Methode, mit der bestimmt wird, ob vom Client eine Instanz der <xref:System.ServiceModel.EndpointIdentity>-Klasse zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="048eb-126">Implement the <xref:System.ServiceModel.Security.IdentityVerifier.TryGetIdentity%2A> method, which determines whether an instance of the <xref:System.ServiceModel.EndpointIdentity> class can be returned by the client.</span></span> <span data-ttu-id="048eb-127">Die WCF-Infrastruktur Ruft die-Implementierung der `TryGetIdentity` -Methode zuerst auf, um die Identität des dienstanders aus der Nachricht abzurufen.</span><span class="sxs-lookup"><span data-stu-id="048eb-127">The WCF infrastructure calls the implementation of the `TryGetIdentity` method first to retrieve the service's identity from the message.</span></span> <span data-ttu-id="048eb-128">Anschließend ruft die Infrastruktur die `CheckAccess`-Implementierung mit der zurückgegebenen `EndpointIdentity` und dem zurückgegebenen <xref:System.IdentityModel.Policy.AuthorizationContext> auf.</span><span class="sxs-lookup"><span data-stu-id="048eb-128">Next, the infrastructure calls the `CheckAccess` implementation with the returned `EndpointIdentity` and <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span>  
  
2. <span data-ttu-id="048eb-129">Fügen Sie in die `TryGetIdentity`-Methode folgenden Code ein:</span><span class="sxs-lookup"><span data-stu-id="048eb-129">In the `TryGetIdentity` method, put the following code:</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#2)]
     [!code-vb[c_HowToSetCustomClientIdentity#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#2)]  
  
### <a name="to-implement-a-custom-binding-and-set-the-custom-identityverifier"></a><span data-ttu-id="048eb-130">So implementieren Sie eine benutzerdefinierte Bindung und legen den benutzerdefinierten IdentityVerifier fest:</span><span class="sxs-lookup"><span data-stu-id="048eb-130">To implement a custom binding and set the custom IdentityVerifier</span></span>  
  
1. <span data-ttu-id="048eb-131">Erstellen Sie eine Methode, von der ein <xref:System.ServiceModel.Channels.Binding>-Objekt zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="048eb-131">Create a method that returns a <xref:System.ServiceModel.Channels.Binding> object.</span></span> <span data-ttu-id="048eb-132">In diesem Beispiel wird zunächst eine Instanz der <xref:System.ServiceModel.WSHttpBinding>-Klasse erstellt und der Sicherheitsmodus auf <xref:System.ServiceModel.SecurityMode.Message> und der <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> auf <xref:System.ServiceModel.MessageCredentialType.None> festgelegt.</span><span class="sxs-lookup"><span data-stu-id="048eb-132">This example begins creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class and sets its security mode to <xref:System.ServiceModel.SecurityMode.Message>, and its <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> to <xref:System.ServiceModel.MessageCredentialType.None>.</span></span>  
  
2. <span data-ttu-id="048eb-133">Erstellen Sie mit der <xref:System.ServiceModel.Channels.BindingElementCollection>-Methode <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A>.</span><span class="sxs-lookup"><span data-stu-id="048eb-133">Create a <xref:System.ServiceModel.Channels.BindingElementCollection> using the <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> method.</span></span>  
  
3. <span data-ttu-id="048eb-134">Geben Sie <xref:System.ServiceModel.Channels.SecurityBindingElement> aus der Auflistung zurück, und wandeln Sie sie in eine <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>-Variable um.</span><span class="sxs-lookup"><span data-stu-id="048eb-134">Return the <xref:System.ServiceModel.Channels.SecurityBindingElement> from the collection and cast it to a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> variable.</span></span>  
  
4. <span data-ttu-id="048eb-135">Legen Sie die <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.IdentityVerifier%2A>-Eigenschaft der <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>-Klasse auf eine neue Instanz der zuvor erstellten `CustomIdentityVerifier`-Klasse fest.</span><span class="sxs-lookup"><span data-stu-id="048eb-135">Set the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.IdentityVerifier%2A> property of the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> class to a new instance of the `CustomIdentityVerifier` class created previously.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#3)]
     [!code-vb[c_HowToSetCustomClientIdentity#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#3)]  
  
5. <span data-ttu-id="048eb-136">Mit der benutzerdefinierten Bindung, die zurückgegeben wird, wird eine Instanz des Clients und der Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="048eb-136">The custom binding that is returned is used to create an instance of the client and class.</span></span> <span data-ttu-id="048eb-137">Der Client kann anschließend eine benutzerdefinierte Identitätsprüfung des Diensts gemäß der Anzeige im folgenden Code ausführen.</span><span class="sxs-lookup"><span data-stu-id="048eb-137">The client can then perform a custom identity verification check of the service as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#4)]
     [!code-vb[c_HowToSetCustomClientIdentity#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="048eb-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="048eb-138">Example</span></span>  

 <span data-ttu-id="048eb-139">Im folgenden Beispiel wird eine vollständige Implementierung der <xref:System.ServiceModel.Security.IdentityVerifier>-Klasse gezeigt.</span><span class="sxs-lookup"><span data-stu-id="048eb-139">The following example shows a complete implementation of the <xref:System.ServiceModel.Security.IdentityVerifier> class.</span></span>  
  
 [!code-csharp[c_HowToSetCustomClientIdentity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#5)]
 [!code-vb[c_HowToSetCustomClientIdentity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="048eb-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="048eb-140">Example</span></span>  

 <span data-ttu-id="048eb-141">Im folgenden Beispiel wird eine vollständige Implementierung der <xref:System.ServiceModel.EndpointIdentity>-Klasse gezeigt.</span><span class="sxs-lookup"><span data-stu-id="048eb-141">The following example shows a complete implementation of the <xref:System.ServiceModel.EndpointIdentity> class.</span></span>  
  
 [!code-csharp[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#6)]
 [!code-vb[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="048eb-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="048eb-142">See also</span></span>

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- <xref:System.ServiceModel.EndpointIdentity>
- <xref:System.ServiceModel.Security.IdentityVerifier>
- [<span data-ttu-id="048eb-143">Dienstidentitätsbeispiel</span><span class="sxs-lookup"><span data-stu-id="048eb-143">Service Identity Sample</span></span>](../samples/service-identity-sample.md)
- [<span data-ttu-id="048eb-144">Autorisierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="048eb-144">Authorization Policy</span></span>](../samples/authorization-policy.md)

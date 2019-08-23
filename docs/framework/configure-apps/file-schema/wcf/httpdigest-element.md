---
title: <httpDigest>-Element
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 2ceefdd7fab82025e89ad08d8423d57524c2e4d8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925566"
---
# <a name="httpdigest-element"></a><span data-ttu-id="b2f74-102">\<httpdigest-> Element</span><span class="sxs-lookup"><span data-stu-id="b2f74-102">\<httpDigest> Element</span></span>
<span data-ttu-id="b2f74-103">Gibt Anmeldeinformationen vom Typ Digest an, die bei der Authentifizierung des Clients bei einem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b2f74-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
 <span data-ttu-id="b2f74-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b2f74-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b2f74-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="b2f74-105">\<behaviors></span></span>  
<span data-ttu-id="b2f74-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="b2f74-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="b2f74-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b2f74-107">\<behavior></span></span>  
<span data-ttu-id="b2f74-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="b2f74-108">\<clientCredentials></span></span>  
<span data-ttu-id="b2f74-109">\<httpDigest></span><span class="sxs-lookup"><span data-stu-id="b2f74-109">\<httpDigest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2f74-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2f74-110">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2f74-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b2f74-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b2f74-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b2f74-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2f74-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="b2f74-113">Attributes</span></span>  
  
|<span data-ttu-id="b2f74-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="b2f74-114">Attribute</span></span>|<span data-ttu-id="b2f74-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2f74-115">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="b2f74-116">Legt die Identitätswechseleinstellungen fest, die der Client an den Server weitergibt.</span><span class="sxs-lookup"><span data-stu-id="b2f74-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="b2f74-117">Der Identitätswechselmodus, den der Client auswählt, wird nicht auf dem Server durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="b2f74-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="b2f74-118">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="b2f74-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b2f74-119">Identifi Der Server kann die Identität und die Berechtigungen des Clients erhalten, kann jedoch nicht die Identität des Clients annehmen.</span><span class="sxs-lookup"><span data-stu-id="b2f74-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="b2f74-120">Identitätswechsel Der Server kann den Sicherheitskontext des Clients auf dem lokalen System imitieren.</span><span class="sxs-lookup"><span data-stu-id="b2f74-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="b2f74-121">Delegations Der Server kann den Sicherheitskontext des Clients auf Remote Systemen imitieren.</span><span class="sxs-lookup"><span data-stu-id="b2f74-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="b2f74-122">Anonymous Der Server kann den Client nicht annehmen oder ihn identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b2f74-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="b2f74-123">Gar Eine Identitätswechsel Ebene ist nicht zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b2f74-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="b2f74-124">Die Standardeinstellung ist Identification.</span><span class="sxs-lookup"><span data-stu-id="b2f74-124">The default is Identification.</span></span> <span data-ttu-id="b2f74-125">Dieses Attribut ist vom Typ <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="b2f74-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2f74-126">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b2f74-126">Child Elements</span></span>  
 <span data-ttu-id="b2f74-127">None</span><span class="sxs-lookup"><span data-stu-id="b2f74-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b2f74-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b2f74-128">Parent Elements</span></span>  
  
|<span data-ttu-id="b2f74-129">Element</span><span class="sxs-lookup"><span data-stu-id="b2f74-129">Element</span></span>|<span data-ttu-id="b2f74-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b2f74-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2f74-131">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="b2f74-131">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="b2f74-132">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="b2f74-132">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2f74-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b2f74-133">Remarks</span></span>  
 <span data-ttu-id="b2f74-134">Ein Digest ist ein Hash, der mit einem Algorithmus und einer Reihe von Eingaben ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="b2f74-134">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="b2f74-135">Der Authentifizierer und der Authentifizierte verständigen sich über einen Algorithmus und tauschen die für die Eingabe verwendeten Daten aus.</span><span class="sxs-lookup"><span data-stu-id="b2f74-135">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="b2f74-136">Der Client kann den Hash berechnen und an den Dienst senden.</span><span class="sxs-lookup"><span data-stu-id="b2f74-136">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="b2f74-137">Der Dienst berechnet den Hash ebenfalls und vergleicht die Werte.</span><span class="sxs-lookup"><span data-stu-id="b2f74-137">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="b2f74-138">Bei einer Übereinstimmung ist die Überprüfung des Clients erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="b2f74-138">A match validates the client.</span></span>  
  
 <span data-ttu-id="b2f74-139">Diese Funktion muss mit Active Directory unter Windows und unter IIS (Internet Information Services) aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="b2f74-139">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="b2f74-140">Weitere Informationen finden Sie unter [Digest-Authentifizierung in IIS 6,0](https://go.microsoft.com/fwlink/?LinkId=88443).</span><span class="sxs-lookup"><span data-stu-id="b2f74-140">For more information, see [Digest Authentication in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2f74-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2f74-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="b2f74-142">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="b2f74-142">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="b2f74-143">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="b2f74-143">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="b2f74-144">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="b2f74-144">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="b2f74-145">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="b2f74-145">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

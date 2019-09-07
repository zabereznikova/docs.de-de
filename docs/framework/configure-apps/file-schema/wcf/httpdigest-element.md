---
title: <httpDigest>-Element
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: f392ebf4eeb6a008952fd4d5ef4e301e57f6eb31
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397994"
---
# <a name="httpdigest-element"></a><span data-ttu-id="2e02a-102">\<httpdigest-> Element</span><span class="sxs-lookup"><span data-stu-id="2e02a-102">\<httpDigest> Element</span></span>
<span data-ttu-id="2e02a-103">Gibt Anmeldeinformationen vom Typ Digest an, die bei der Authentifizierung des Clients bei einem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2e02a-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
<span data-ttu-id="2e02a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2e02a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2e02a-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2e02a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2e02a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2e02a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="2e02a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2e02a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="2e02a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2e02a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="2e02a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client Anmelde Informationen >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="2e02a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="2e02a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<httpdigest->**</span><span class="sxs-lookup"><span data-stu-id="2e02a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpDigest>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e02a-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e02a-111">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e02a-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2e02a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2e02a-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2e02a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e02a-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="2e02a-114">Attributes</span></span>  
  
|<span data-ttu-id="2e02a-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="2e02a-115">Attribute</span></span>|<span data-ttu-id="2e02a-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e02a-116">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="2e02a-117">Legt die Identitätswechseleinstellungen fest, die der Client an den Server weitergibt.</span><span class="sxs-lookup"><span data-stu-id="2e02a-117">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="2e02a-118">Der Identitätswechselmodus, den der Client auswählt, wird nicht auf dem Server durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="2e02a-118">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="2e02a-119">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="2e02a-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="2e02a-120">Identifi Der Server kann die Identität und die Berechtigungen des Clients erhalten, kann jedoch nicht die Identität des Clients annehmen.</span><span class="sxs-lookup"><span data-stu-id="2e02a-120">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="2e02a-121">Identitätswechsel Der Server kann den Sicherheitskontext des Clients auf dem lokalen System imitieren.</span><span class="sxs-lookup"><span data-stu-id="2e02a-121">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="2e02a-122">Delegations Der Server kann den Sicherheitskontext des Clients auf Remote Systemen imitieren.</span><span class="sxs-lookup"><span data-stu-id="2e02a-122">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="2e02a-123">Anonymous Der Server kann den Client nicht annehmen oder ihn identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2e02a-123">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="2e02a-124">Gar Eine Identitätswechsel Ebene ist nicht zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="2e02a-124">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="2e02a-125">Die Standardeinstellung ist Identification.</span><span class="sxs-lookup"><span data-stu-id="2e02a-125">The default is Identification.</span></span> <span data-ttu-id="2e02a-126">Dieses Attribut ist vom Typ <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="2e02a-126">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e02a-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2e02a-127">Child Elements</span></span>  
 <span data-ttu-id="2e02a-128">None</span><span class="sxs-lookup"><span data-stu-id="2e02a-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2e02a-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2e02a-129">Parent Elements</span></span>  
  
|<span data-ttu-id="2e02a-130">Element</span><span class="sxs-lookup"><span data-stu-id="2e02a-130">Element</span></span>|<span data-ttu-id="2e02a-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e02a-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e02a-132">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="2e02a-132">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="2e02a-133">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="2e02a-133">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e02a-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2e02a-134">Remarks</span></span>  
 <span data-ttu-id="2e02a-135">Ein Digest ist ein Hash, der mit einem Algorithmus und einer Reihe von Eingaben ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="2e02a-135">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="2e02a-136">Der Authentifizierer und der Authentifizierte verständigen sich über einen Algorithmus und tauschen die für die Eingabe verwendeten Daten aus.</span><span class="sxs-lookup"><span data-stu-id="2e02a-136">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="2e02a-137">Der Client kann den Hash berechnen und an den Dienst senden.</span><span class="sxs-lookup"><span data-stu-id="2e02a-137">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="2e02a-138">Der Dienst berechnet den Hash ebenfalls und vergleicht die Werte.</span><span class="sxs-lookup"><span data-stu-id="2e02a-138">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="2e02a-139">Bei einer Übereinstimmung ist die Überprüfung des Clients erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="2e02a-139">A match validates the client.</span></span>  
  
 <span data-ttu-id="2e02a-140">Diese Funktion muss mit Active Directory unter Windows und unter IIS (Internet Information Services) aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="2e02a-140">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="2e02a-141">Weitere Informationen finden Sie unter [Digest-Authentifizierung in IIS 6,0](https://go.microsoft.com/fwlink/?LinkId=88443).</span><span class="sxs-lookup"><span data-stu-id="2e02a-141">For more information, see [Digest Authentication in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e02a-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e02a-142">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="2e02a-143">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="2e02a-143">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="2e02a-144">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="2e02a-144">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="2e02a-145">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="2e02a-145">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="2e02a-146">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="2e02a-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

---
title: '&lt;httpDigest&gt;-Element'
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 4f3edb4a525429bfc55c4e4cfaffbfc5726dcef8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43521986"
---
# <a name="lthttpdigestgt-element"></a><span data-ttu-id="8d463-102">&lt;httpDigest&gt;-Element</span><span class="sxs-lookup"><span data-stu-id="8d463-102">&lt;httpDigest&gt; Element</span></span>
<span data-ttu-id="8d463-103">Gibt Anmeldeinformationen vom Typ Hashwert an, die bei der Authentifizierung des Clients bei einem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8d463-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
 <span data-ttu-id="8d463-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8d463-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8d463-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="8d463-105">\<behaviors></span></span>  
<span data-ttu-id="8d463-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="8d463-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="8d463-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="8d463-107">\<behavior></span></span>  
<span data-ttu-id="8d463-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="8d463-108">\<clientCredentials></span></span>  
<span data-ttu-id="8d463-109">\<HttpDigest ></span><span class="sxs-lookup"><span data-stu-id="8d463-109">\<httpDigest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d463-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="8d463-110">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d463-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8d463-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8d463-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8d463-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d463-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="8d463-113">Attributes</span></span>  
  
|<span data-ttu-id="8d463-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="8d463-114">Attribute</span></span>|<span data-ttu-id="8d463-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8d463-115">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="8d463-116">Legt die Identitätswechseleinstellungen fest, die der Client an den Server weitergibt.</span><span class="sxs-lookup"><span data-stu-id="8d463-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="8d463-117">Der Identitätswechselmodus, den der Client auswählt, wird nicht auf dem Server durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="8d463-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="8d463-118">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="8d463-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="8d463-119">-ID: Der Server kann die Identitäts- und Berechtigungsinformationen des Clients abrufen, aber den Client nicht imitieren.</span><span class="sxs-lookup"><span data-stu-id="8d463-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="8d463-120">-Impersonation: Der Server kann der Clientsicherheitskontext auf dem lokalen System imitieren.</span><span class="sxs-lookup"><span data-stu-id="8d463-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="8d463-121">-Delegation: Der Server kann der Clientsicherheitskontext auf Remotesystemen imitieren.</span><span class="sxs-lookup"><span data-stu-id="8d463-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="8d463-122">– Anonymous: Der Server kann nicht imitieren oder identifizieren den Client.</span><span class="sxs-lookup"><span data-stu-id="8d463-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="8d463-123">– None: Ebene des Identitätswechsels wird nicht zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="8d463-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="8d463-124">Die Standardeinstellung ist Identification.</span><span class="sxs-lookup"><span data-stu-id="8d463-124">The default is Identification.</span></span> <span data-ttu-id="8d463-125">Dieses Attribut ist vom Typ <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="8d463-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8d463-126">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8d463-126">Child Elements</span></span>  
 <span data-ttu-id="8d463-127">Keiner</span><span class="sxs-lookup"><span data-stu-id="8d463-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8d463-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8d463-128">Parent Elements</span></span>  
  
|<span data-ttu-id="8d463-129">Element</span><span class="sxs-lookup"><span data-stu-id="8d463-129">Element</span></span>|<span data-ttu-id="8d463-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8d463-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8d463-131">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="8d463-131">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="8d463-132">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="8d463-132">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d463-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8d463-133">Remarks</span></span>  
 <span data-ttu-id="8d463-134">Ein Hashwert ist ein Hash, der mit einem Algorithmus und einer Reihe von Eingaben ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="8d463-134">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="8d463-135">Der Authentifizierer und der Authentifizierte verständigen sich über einen Algorithmus und tauschen die für die Eingabe verwendeten Daten aus.</span><span class="sxs-lookup"><span data-stu-id="8d463-135">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="8d463-136">Der Client kann den Hash berechnen und an den Dienst senden.</span><span class="sxs-lookup"><span data-stu-id="8d463-136">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="8d463-137">Der Dienst berechnet den Hash ebenfalls und vergleicht die Werte.</span><span class="sxs-lookup"><span data-stu-id="8d463-137">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="8d463-138">Bei einer Übereinstimmung ist die Überprüfung des Clients erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="8d463-138">A match validates the client.</span></span>  
  
 <span data-ttu-id="8d463-139">Diese Funktion muss mit Active Directory unter Windows und unter IIS (Internet Information Services) aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="8d463-139">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="8d463-140">Weitere Informationen finden Sie unter [Digestauthentifizierung in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span><span class="sxs-lookup"><span data-stu-id="8d463-140">For more information, see [Digest Authentication in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d463-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d463-141">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>  
 <xref:System.ServiceModel.Configuration.HttpDigestClientElement>  
 <xref:System.ServiceModel.Security.HttpDigestClientCredential>  
 [<span data-ttu-id="8d463-142">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="8d463-142">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="8d463-143">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="8d463-143">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="8d463-144">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="8d463-144">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="8d463-145">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="8d463-145">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

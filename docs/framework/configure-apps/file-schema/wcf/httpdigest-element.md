---
title: '&lt;httpDigest&gt;-Element'
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 2211c593090d697ae07350fcf7ac491b9d23e2d0
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150140"
---
# <a name="lthttpdigestgt-element"></a><span data-ttu-id="e9d6a-102">&lt;httpDigest&gt;-Element</span><span class="sxs-lookup"><span data-stu-id="e9d6a-102">&lt;httpDigest&gt; Element</span></span>
<span data-ttu-id="e9d6a-103">Gibt Anmeldeinformationen vom Typ Hashwert an, die bei der Authentifizierung des Clients bei einem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e9d6a-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
 <span data-ttu-id="e9d6a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e9d6a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e9d6a-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="e9d6a-105">\<behaviors></span></span>  
<span data-ttu-id="e9d6a-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="e9d6a-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="e9d6a-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="e9d6a-107">\<behavior></span></span>  
<span data-ttu-id="e9d6a-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="e9d6a-108">\<clientCredentials></span></span>  
<span data-ttu-id="e9d6a-109">\<HttpDigest ></span><span class="sxs-lookup"><span data-stu-id="e9d6a-109">\<httpDigest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9d6a-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9d6a-110">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9d6a-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e9d6a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e9d6a-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e9d6a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9d6a-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="e9d6a-113">Attributes</span></span>  
  
|<span data-ttu-id="e9d6a-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="e9d6a-114">Attribute</span></span>|<span data-ttu-id="e9d6a-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9d6a-115">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="e9d6a-116">Legt die Identitätswechseleinstellungen fest, die der Client an den Server weitergibt.</span><span class="sxs-lookup"><span data-stu-id="e9d6a-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="e9d6a-117">Der Identitätswechselmodus, den der Client auswählt, wird nicht auf dem Server durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="e9d6a-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="e9d6a-118">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="e9d6a-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e9d6a-119">-ID: Der Server kann die Identitäts- und Berechtigungsinformationen des Clients abrufen, aber den Client nicht imitieren.</span><span class="sxs-lookup"><span data-stu-id="e9d6a-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="e9d6a-120">-Identitätswechsel: Der Server kann der Clientsicherheitskontext auf dem lokalen System imitieren.</span><span class="sxs-lookup"><span data-stu-id="e9d6a-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="e9d6a-121">-Delegierung: Der Server kann der Clientsicherheitskontext auf Remotesystemen imitieren.</span><span class="sxs-lookup"><span data-stu-id="e9d6a-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="e9d6a-122">– Anonymous: Der Server kann nicht imitieren oder identifizieren den Client.</span><span class="sxs-lookup"><span data-stu-id="e9d6a-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="e9d6a-123">– None: Ebene des Identitätswechsels wird nicht zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="e9d6a-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="e9d6a-124">Die Standardeinstellung ist Identification.</span><span class="sxs-lookup"><span data-stu-id="e9d6a-124">The default is Identification.</span></span> <span data-ttu-id="e9d6a-125">Dieses Attribut ist vom Typ <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="e9d6a-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9d6a-126">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9d6a-126">Child Elements</span></span>  
 <span data-ttu-id="e9d6a-127">Keine</span><span class="sxs-lookup"><span data-stu-id="e9d6a-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9d6a-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e9d6a-128">Parent Elements</span></span>  
  
|<span data-ttu-id="e9d6a-129">Element</span><span class="sxs-lookup"><span data-stu-id="e9d6a-129">Element</span></span>|<span data-ttu-id="e9d6a-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9d6a-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9d6a-131">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="e9d6a-131">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="e9d6a-132">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="e9d6a-132">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9d6a-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9d6a-133">Remarks</span></span>  
 <span data-ttu-id="e9d6a-134">Ein Hashwert ist ein Hash, der mit einem Algorithmus und einer Reihe von Eingaben ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="e9d6a-134">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="e9d6a-135">Der Authentifizierer und der Authentifizierte verständigen sich über einen Algorithmus und tauschen die für die Eingabe verwendeten Daten aus.</span><span class="sxs-lookup"><span data-stu-id="e9d6a-135">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="e9d6a-136">Der Client kann den Hash berechnen und an den Dienst senden.</span><span class="sxs-lookup"><span data-stu-id="e9d6a-136">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="e9d6a-137">Der Dienst berechnet den Hash ebenfalls und vergleicht die Werte.</span><span class="sxs-lookup"><span data-stu-id="e9d6a-137">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="e9d6a-138">Bei einer Übereinstimmung ist die Überprüfung des Clients erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="e9d6a-138">A match validates the client.</span></span>  
  
 <span data-ttu-id="e9d6a-139">Diese Funktion muss mit Active Directory unter Windows und unter IIS (Internet Information Services) aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="e9d6a-139">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="e9d6a-140">Weitere Informationen finden Sie unter [Digestauthentifizierung in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span><span class="sxs-lookup"><span data-stu-id="e9d6a-140">For more information, see [Digest Authentication in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d6a-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9d6a-141">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>  
 <xref:System.ServiceModel.Configuration.HttpDigestClientElement>  
 <xref:System.ServiceModel.Security.HttpDigestClientCredential>  
 [<span data-ttu-id="e9d6a-142">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="e9d6a-142">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="e9d6a-143">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="e9d6a-143">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="e9d6a-144">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="e9d6a-144">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="e9d6a-145">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="e9d6a-145">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

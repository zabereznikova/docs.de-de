---
title: '&lt;httpDigest&gt;-Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 95e6a7d31949bd7a6badb029e3f768a63fbaf924
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="lthttpdigestgt-element"></a><span data-ttu-id="817e7-102">&lt;httpDigest&gt;-Element</span><span class="sxs-lookup"><span data-stu-id="817e7-102">&lt;httpDigest&gt; Element</span></span>
<span data-ttu-id="817e7-103">Gibt Anmeldeinformationen vom Typ Hashwert an, die bei der Authentifizierung des Clients bei einem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="817e7-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
 <span data-ttu-id="817e7-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="817e7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="817e7-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="817e7-105">\<behaviors></span></span>  
<span data-ttu-id="817e7-106">\<EndpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="817e7-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="817e7-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="817e7-107">\<behavior></span></span>  
<span data-ttu-id="817e7-108">\<ClientCredentials ></span><span class="sxs-lookup"><span data-stu-id="817e7-108">\<clientCredentials></span></span>  
<span data-ttu-id="817e7-109">\<HttpDigest ></span><span class="sxs-lookup"><span data-stu-id="817e7-109">\<httpDigest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="817e7-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="817e7-110">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="817e7-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="817e7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="817e7-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="817e7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="817e7-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="817e7-113">Attributes</span></span>  
  
|<span data-ttu-id="817e7-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="817e7-114">Attribute</span></span>|<span data-ttu-id="817e7-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="817e7-115">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="817e7-116">Legt die Identitätswechseleinstellungen fest, die der Client an den Server weitergibt.</span><span class="sxs-lookup"><span data-stu-id="817e7-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="817e7-117">Der Identitätswechselmodus, den der Client auswählt, wird nicht auf dem Server durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="817e7-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="817e7-118">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="817e7-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="817e7-119">-ID: Der Server kann die Identitäts- und Berechtigungsinformationen des Clients abrufen, aber den Client nicht imitieren.</span><span class="sxs-lookup"><span data-stu-id="817e7-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="817e7-120">-Impersonation: Der Server kann der Clientsicherheitskontext auf dem lokalen System imitieren.</span><span class="sxs-lookup"><span data-stu-id="817e7-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="817e7-121">-Delegation: Der Server kann Sie in der Sicherheitskontext des Clients auf Remotesystemen imitieren.</span><span class="sxs-lookup"><span data-stu-id="817e7-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="817e7-122">– Anonymous: Der Server kann nicht imitieren oder identifizieren den Client.</span><span class="sxs-lookup"><span data-stu-id="817e7-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="817e7-123">-"None": Eine Ebene des Identitätswechsels ist nicht zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="817e7-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="817e7-124">Die Standardeinstellung ist Identification.</span><span class="sxs-lookup"><span data-stu-id="817e7-124">The default is Identification.</span></span> <span data-ttu-id="817e7-125">Dieses Attribut ist vom Typ <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="817e7-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="817e7-126">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="817e7-126">Child Elements</span></span>  
 <span data-ttu-id="817e7-127">Keiner</span><span class="sxs-lookup"><span data-stu-id="817e7-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="817e7-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="817e7-128">Parent Elements</span></span>  
  
|<span data-ttu-id="817e7-129">Element</span><span class="sxs-lookup"><span data-stu-id="817e7-129">Element</span></span>|<span data-ttu-id="817e7-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="817e7-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="817e7-131">\<ClientCredentials ></span><span class="sxs-lookup"><span data-stu-id="817e7-131">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="817e7-132">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="817e7-132">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="817e7-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="817e7-133">Remarks</span></span>  
 <span data-ttu-id="817e7-134">Ein Hashwert ist ein Hash, der mit einem Algorithmus und einer Reihe von Eingaben ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="817e7-134">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="817e7-135">Der Authentifizierer und der Authentifizierte verständigen sich über einen Algorithmus und tauschen die für die Eingabe verwendeten Daten aus.</span><span class="sxs-lookup"><span data-stu-id="817e7-135">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="817e7-136">Der Client kann den Hash berechnen und an den Dienst senden.</span><span class="sxs-lookup"><span data-stu-id="817e7-136">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="817e7-137">Der Dienst berechnet den Hash ebenfalls und vergleicht die Werte.</span><span class="sxs-lookup"><span data-stu-id="817e7-137">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="817e7-138">Bei einer Übereinstimmung ist die Überprüfung des Clients erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="817e7-138">A match validates the client.</span></span>  
  
 <span data-ttu-id="817e7-139">Diese Funktion muss mit Active Directory unter Windows und unter IIS (Internet Information Services) aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="817e7-139">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<span data-ttu-id="817e7-140">[Digest-Authentifizierung in IIS 6.0](http://go.microsoft.com/fwlink/?LinkId=88443).</span><span class="sxs-lookup"><span data-stu-id="817e7-140"> [Digest Authentication in IIS 6.0](http://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="817e7-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="817e7-141">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>  
 <xref:System.ServiceModel.Configuration.HttpDigestClientElement>  
 <xref:System.ServiceModel.Security.HttpDigestClientCredential>  
 [<span data-ttu-id="817e7-142">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="817e7-142">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="817e7-143">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="817e7-143">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="817e7-144">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="817e7-144">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="817e7-145">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="817e7-145">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

---
title: <windows> der <clientCredentials> Element
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: b5e92745b9e39534d2a0bc35504c2dbc8346d2ca
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221019"
---
# <a name="windows-of-clientcredentials-element"></a><span data-ttu-id="77b44-102">\<Windows > des \<ClientCredentials >-Element</span><span class="sxs-lookup"><span data-stu-id="77b44-102">\<windows> of \<clientCredentials> Element</span></span>
<span data-ttu-id="77b44-103">Gibt die Einstellungen für Windows-Anmeldeinformationen an, die zum Darstellen des Clients verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="77b44-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
 <span data-ttu-id="77b44-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="77b44-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="77b44-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="77b44-105">\<behaviors></span></span>  
<span data-ttu-id="77b44-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="77b44-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="77b44-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="77b44-107">\<behavior></span></span>  
<span data-ttu-id="77b44-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="77b44-108">\<clientCredentials></span></span>  
<span data-ttu-id="77b44-109">\<windows></span><span class="sxs-lookup"><span data-stu-id="77b44-109">\<windows></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77b44-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="77b44-110">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77b44-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="77b44-111">Attributes and Elements</span></span>  
 <span data-ttu-id="77b44-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="77b44-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77b44-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="77b44-113">Attributes</span></span>  
  
|<span data-ttu-id="77b44-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="77b44-114">Attribute</span></span>|<span data-ttu-id="77b44-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77b44-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="77b44-116">Legt die Identitätswechseleinstellungen fest, die der Client an den Server weitergibt.</span><span class="sxs-lookup"><span data-stu-id="77b44-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="77b44-117">Der Identitätswechselmodus, den der Client auswählt, wird nicht auf dem Server durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="77b44-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="77b44-118">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="77b44-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="77b44-119">-ID: Der Server kann die Identitäts- und Berechtigungsinformationen des Clients abrufen, aber den Client nicht imitieren.</span><span class="sxs-lookup"><span data-stu-id="77b44-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="77b44-120">-Identitätswechsel: Der Server kann der Clientsicherheitskontext auf dem lokalen System imitieren.</span><span class="sxs-lookup"><span data-stu-id="77b44-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="77b44-121">-Delegierung: Der Server kann der Clientsicherheitskontext auf Remotesystemen imitieren.</span><span class="sxs-lookup"><span data-stu-id="77b44-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="77b44-122">– Anonymous: Der Server kann nicht imitieren oder identifizieren den Client.</span><span class="sxs-lookup"><span data-stu-id="77b44-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="77b44-123">– None: Ebene des Identitätswechsels wird nicht zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="77b44-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="77b44-124">Die Standardeinstellung ist Identification.</span><span class="sxs-lookup"><span data-stu-id="77b44-124">The default is Identification.</span></span> <span data-ttu-id="77b44-125">Dieses Attribut ist vom Typ <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="77b44-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="77b44-126">Durch das Festlegen dieser Eigenschaft auf `true` kann die Authentifizierung auf NTLM herabgestuft werden, wenn Kerberos nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="77b44-126">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="77b44-127">Wenn diese Eigenschaft auf `false` bewirkt, dass Windows Communication Foundation (WCF) stellen einen Best-Effort-Prinzip eine Ausnahme ausgelöst, wenn NTLM verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="77b44-127">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="77b44-128">Durch das Festlegen dieser Eigenschaft auf `false` wird unter Umständen nicht verhindert, dass NTLM-Anmeldeinformationen über die Verbindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="77b44-128">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77b44-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="77b44-129">Child Elements</span></span>  
 <span data-ttu-id="77b44-130">Keine</span><span class="sxs-lookup"><span data-stu-id="77b44-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="77b44-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="77b44-131">Parent Elements</span></span>  
  
|<span data-ttu-id="77b44-132">Element</span><span class="sxs-lookup"><span data-stu-id="77b44-132">Element</span></span>|<span data-ttu-id="77b44-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77b44-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="77b44-134">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="77b44-134">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="77b44-135">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="77b44-135">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="77b44-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77b44-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="77b44-137">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="77b44-137">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="77b44-138">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="77b44-138">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="77b44-139">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="77b44-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

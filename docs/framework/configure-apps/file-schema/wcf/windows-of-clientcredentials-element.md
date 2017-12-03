---
title: '&lt;windows&gt; des &lt;clientCredentials&gt;-Elements'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5cf2740b0218286178e62262723bb060dc2d3817
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltwindowsgt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="59bd0-102">&lt;windows&gt; des &lt;clientCredentials&gt;-Elements</span><span class="sxs-lookup"><span data-stu-id="59bd0-102">&lt;windows&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="59bd0-103">Gibt die Einstellungen für Windows-Anmeldeinformationen an, die zum Darstellen des Clients verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="59bd0-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
 <span data-ttu-id="59bd0-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="59bd0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="59bd0-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="59bd0-105">\<behaviors></span></span>  
<span data-ttu-id="59bd0-106">\<EndpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="59bd0-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="59bd0-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="59bd0-107">\<behavior></span></span>  
<span data-ttu-id="59bd0-108">\<ClientCredentials ></span><span class="sxs-lookup"><span data-stu-id="59bd0-108">\<clientCredentials></span></span>  
<span data-ttu-id="59bd0-109">\<Windows ></span><span class="sxs-lookup"><span data-stu-id="59bd0-109">\<windows></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59bd0-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="59bd0-110">Syntax</span></span>  
  
```xml  
<windows   
    allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"  
        allowNtlm="Boolean"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59bd0-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="59bd0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="59bd0-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="59bd0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59bd0-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="59bd0-113">Attributes</span></span>  
  
|<span data-ttu-id="59bd0-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="59bd0-114">Attribute</span></span>|<span data-ttu-id="59bd0-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59bd0-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="59bd0-116">Legt die Identitätswechseleinstellungen fest, die der Client an den Server weitergibt.</span><span class="sxs-lookup"><span data-stu-id="59bd0-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="59bd0-117">Der Identitätswechselmodus, den der Client auswählt, wird nicht auf dem Server durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="59bd0-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="59bd0-118">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="59bd0-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="59bd0-119">-ID: Der Server kann die Identitäts- und Berechtigungsinformationen des Clients abrufen, aber den Client nicht imitieren.</span><span class="sxs-lookup"><span data-stu-id="59bd0-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="59bd0-120">-Impersonation: Der Server kann der Clientsicherheitskontext auf dem lokalen System imitieren.</span><span class="sxs-lookup"><span data-stu-id="59bd0-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="59bd0-121">-Delegation: Der Server kann Sie in der Sicherheitskontext des Clients auf Remotesystemen imitieren.</span><span class="sxs-lookup"><span data-stu-id="59bd0-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="59bd0-122">– Anonymous: Der Server kann nicht imitieren oder identifizieren den Client.</span><span class="sxs-lookup"><span data-stu-id="59bd0-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="59bd0-123">-"None": Eine Ebene des Identitätswechsels ist nicht zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="59bd0-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="59bd0-124">Die Standardeinstellung ist Identification.</span><span class="sxs-lookup"><span data-stu-id="59bd0-124">The default is Identification.</span></span> <span data-ttu-id="59bd0-125">Dieses Attribut ist vom Typ <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="59bd0-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="59bd0-126">Durch das Festlegen dieser Eigenschaft auf `true` kann die Authentifizierung auf NTLM herabgestuft werden, wenn Kerberos nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="59bd0-126">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="59bd0-127">Das Festlegen dieser Eigenschaft auf `false` führt dazu, dass [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] nach dem Best-Effort-Prinzip eine Ausnahme auslöst, wenn NTLM verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="59bd0-127">Setting this property to `false` causes [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="59bd0-128">Durch das Festlegen dieser Eigenschaft auf `false` wird unter Umständen nicht verhindert, dass NTLM-Anmeldeinformationen über die Verbindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="59bd0-128">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59bd0-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="59bd0-129">Child Elements</span></span>  
 <span data-ttu-id="59bd0-130">Keine</span><span class="sxs-lookup"><span data-stu-id="59bd0-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59bd0-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="59bd0-131">Parent Elements</span></span>  
  
|<span data-ttu-id="59bd0-132">Element</span><span class="sxs-lookup"><span data-stu-id="59bd0-132">Element</span></span>|<span data-ttu-id="59bd0-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59bd0-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59bd0-134">\<ClientCredentials ></span><span class="sxs-lookup"><span data-stu-id="59bd0-134">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="59bd0-135">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="59bd0-135">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="59bd0-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59bd0-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WindowsClientElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>  
 <xref:System.ServiceModel.Security.WindowsClientCredential>  
 [<span data-ttu-id="59bd0-137">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="59bd0-137">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="59bd0-138">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="59bd0-138">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="59bd0-139">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="59bd0-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)

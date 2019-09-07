---
title: <windows>of <clientCredentials> -Element
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: 61ca99213f0b83a5af5df0184a8c1de405366288
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399118"
---
# <a name="windows-of-clientcredentials-element"></a><span data-ttu-id="b4957-102">\<Windows-> \<von Clientanmelde Informationen >-Element</span><span class="sxs-lookup"><span data-stu-id="b4957-102">\<windows> of \<clientCredentials> Element</span></span>
<span data-ttu-id="b4957-103">Gibt die Einstellungen für Windows-Anmeldeinformationen an, die zum Darstellen des Clients verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4957-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
<span data-ttu-id="b4957-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b4957-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b4957-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b4957-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b4957-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b4957-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="b4957-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b4957-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="b4957-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b4957-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="b4957-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client Anmelde Informationen >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="b4957-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="b4957-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Windows->**</span><span class="sxs-lookup"><span data-stu-id="b4957-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windows>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4957-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4957-111">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4957-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b4957-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b4957-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b4957-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4957-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="b4957-114">Attributes</span></span>  
  
|<span data-ttu-id="b4957-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="b4957-115">Attribute</span></span>|<span data-ttu-id="b4957-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4957-116">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="b4957-117">Legt die Identitätswechseleinstellungen fest, die der Client an den Server weitergibt.</span><span class="sxs-lookup"><span data-stu-id="b4957-117">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="b4957-118">Der Identitätswechselmodus, den der Client auswählt, wird nicht auf dem Server durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="b4957-118">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="b4957-119">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="b4957-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b4957-120">Identifi Der Server kann die Identität und die Berechtigungen des Clients erhalten, kann jedoch nicht die Identität des Clients annehmen.</span><span class="sxs-lookup"><span data-stu-id="b4957-120">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="b4957-121">Identitätswechsel Der Server kann den Sicherheitskontext des Clients auf dem lokalen System imitieren.</span><span class="sxs-lookup"><span data-stu-id="b4957-121">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="b4957-122">Delegations Der Server kann den Sicherheitskontext des Clients auf Remote Systemen imitieren.</span><span class="sxs-lookup"><span data-stu-id="b4957-122">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="b4957-123">Anonymous Der Server kann den Client nicht annehmen oder ihn identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b4957-123">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="b4957-124">Gar Eine Identitätswechsel Ebene ist nicht zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b4957-124">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="b4957-125">Die Standardeinstellung ist Identification.</span><span class="sxs-lookup"><span data-stu-id="b4957-125">The default is Identification.</span></span> <span data-ttu-id="b4957-126">Dieses Attribut ist vom Typ <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="b4957-126">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="b4957-127">Durch das Festlegen dieser Eigenschaft auf `true` kann die Authentifizierung auf NTLM herabgestuft werden, wenn Kerberos nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b4957-127">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="b4957-128">Wenn diese Eigenschaft auf `false` festgelegt wird, bewirkt Windows Communication Foundation (WCF), dass eine Ausnahme ausgelöst wird, wenn NTLM verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b4957-128">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="b4957-129">Durch das Festlegen dieser Eigenschaft auf `false` wird unter Umständen nicht verhindert, dass NTLM-Anmeldeinformationen über die Verbindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4957-129">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4957-130">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b4957-130">Child Elements</span></span>  
 <span data-ttu-id="b4957-131">Keine</span><span class="sxs-lookup"><span data-stu-id="b4957-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b4957-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b4957-132">Parent Elements</span></span>  
  
|<span data-ttu-id="b4957-133">Element</span><span class="sxs-lookup"><span data-stu-id="b4957-133">Element</span></span>|<span data-ttu-id="b4957-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4957-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4957-135">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="b4957-135">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="b4957-136">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="b4957-136">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4957-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4957-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="b4957-138">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="b4957-138">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="b4957-139">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="b4957-139">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="b4957-140">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="b4957-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

---
title: <windows> of- <clientCredentials> Element
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: 115e1822659c04ee37a7364f7b25616b52dc5efe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177825"
---
# <a name="windows-of-clientcredentials-element"></a><span data-ttu-id="08be2-102">\<windows> of- \<clientCredentials> Element</span><span class="sxs-lookup"><span data-stu-id="08be2-102">\<windows> of \<clientCredentials> Element</span></span>

<span data-ttu-id="08be2-103">Gibt die Einstellungen für Windows-Anmeldeinformationen an, die zum Darstellen des Clients verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="08be2-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windows>**  
  
## <a name="syntax"></a><span data-ttu-id="08be2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08be2-104">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08be2-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="08be2-105">Attributes and Elements</span></span>  

 <span data-ttu-id="08be2-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="08be2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08be2-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="08be2-107">Attributes</span></span>  
  
|<span data-ttu-id="08be2-108">attribute</span><span class="sxs-lookup"><span data-stu-id="08be2-108">Attribute</span></span>|<span data-ttu-id="08be2-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08be2-109">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="08be2-110">Legt die Identitätswechseleinstellungen fest, die der Client an den Server weitergibt.</span><span class="sxs-lookup"><span data-stu-id="08be2-110">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="08be2-111">Der Identitätswechselmodus, den der Client auswählt, wird nicht auf dem Server durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="08be2-111">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="08be2-112">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="08be2-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="08be2-113">-Identifikation: der Server kann die Identität und die Berechtigungen des Clients erhalten, kann jedoch nicht die Identität des Clients annehmen.</span><span class="sxs-lookup"><span data-stu-id="08be2-113">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="08be2-114">-Identitätswechsel: der Server kann den Sicherheitskontext des Clients auf dem lokalen System imitieren.</span><span class="sxs-lookup"><span data-stu-id="08be2-114">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="08be2-115">-Delegierung: der Server kann den Sicherheitskontext des Clients auf Remote Systemen imitieren.</span><span class="sxs-lookup"><span data-stu-id="08be2-115">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="08be2-116">-Anonymous: der Server kann den Client nicht annehmen oder ihn identifizieren.</span><span class="sxs-lookup"><span data-stu-id="08be2-116">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="08be2-117">-None: Es wurde keine Identitätswechsel Ebene zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="08be2-117">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="08be2-118">Die Standardeinstellung ist Identification.</span><span class="sxs-lookup"><span data-stu-id="08be2-118">The default is Identification.</span></span> <span data-ttu-id="08be2-119">Dieses Attribut ist vom Typ <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="08be2-119">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="08be2-120">Durch das Festlegen dieser Eigenschaft auf `true` kann die Authentifizierung auf NTLM herabgestuft werden, wenn Kerberos nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="08be2-120">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="08be2-121">Wenn diese Eigenschaft auf festgelegt `false` wird, bewirkt Windows Communication Foundation (WCF), dass eine Ausnahme ausgelöst wird, wenn NTLM verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="08be2-121">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="08be2-122">Durch das Festlegen dieser Eigenschaft auf `false` wird unter Umständen nicht verhindert, dass NTLM-Anmeldeinformationen über die Verbindung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="08be2-122">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08be2-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="08be2-123">Child Elements</span></span>  

 <span data-ttu-id="08be2-124">Keine</span><span class="sxs-lookup"><span data-stu-id="08be2-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08be2-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="08be2-125">Parent Elements</span></span>  
  
|<span data-ttu-id="08be2-126">Element</span><span class="sxs-lookup"><span data-stu-id="08be2-126">Element</span></span>|<span data-ttu-id="08be2-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08be2-127">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="08be2-128">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="08be2-128">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08be2-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08be2-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="08be2-130">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="08be2-130">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="08be2-131">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="08be2-131">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="08be2-132">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="08be2-132">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

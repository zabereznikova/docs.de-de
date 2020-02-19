---
title: <httpDigest>-Element
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 328411a429cd42927a190c6805a1f5e2b3555ea1
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448451"
---
# <a name="httpdigest-element"></a><span data-ttu-id="b4f6c-102">\<httpdigest-> Element</span><span class="sxs-lookup"><span data-stu-id="b4f6c-102">\<httpDigest> Element</span></span>
<span data-ttu-id="b4f6c-103">Gibt Anmeldeinformationen vom Typ Digest an, die bei der Authentifizierung des Clients bei einem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
<span data-ttu-id="b4f6c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b4f6c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b4f6c-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b4f6c-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b4f6c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhalten**](behaviors.md) ></span><span class="sxs-lookup"><span data-stu-id="b4f6c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="b4f6c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**endpointverhaltensweisen**](endpointbehaviors.md) ></span><span class="sxs-lookup"><span data-stu-id="b4f6c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="b4f6c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**Verhalten >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="b4f6c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="b4f6c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Clientanmelde**](clientcredentials.md) Informationen ></span><span class="sxs-lookup"><span data-stu-id="b4f6c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="b4f6c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<httpdigest >**</span><span class="sxs-lookup"><span data-stu-id="b4f6c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpDigest>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4f6c-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4f6c-111">Syntax</span></span>  
  
```xml  
<httpDigest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4f6c-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b4f6c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b4f6c-113">In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4f6c-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="b4f6c-114">Attributes</span></span>  
  
|<span data-ttu-id="b4f6c-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="b4f6c-115">Attribute</span></span>|<span data-ttu-id="b4f6c-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4f6c-116">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="b4f6c-117">Legt die Identitätswechseleinstellungen fest, die der Client an den Server weitergibt.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-117">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="b4f6c-118">Der Identitätswechselmodus, den der Client auswählt, wird nicht auf dem Server durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-118">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="b4f6c-119">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="b4f6c-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b4f6c-120">-Identifikation: der Server kann die Identität und die Berechtigungen des Clients erhalten, kann jedoch nicht die Identität des Clients annehmen.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-120">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="b4f6c-121">-Identitätswechsel: der Server kann den Sicherheitskontext des Clients auf dem lokalen System imitieren.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-121">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="b4f6c-122">-Delegierung: der Server kann den Sicherheitskontext des Clients auf Remote Systemen imitieren.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-122">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="b4f6c-123">-Anonymous: der Server kann den Client nicht annehmen oder ihn identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-123">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="b4f6c-124">-None: Es wurde keine Identitätswechsel Ebene zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-124">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="b4f6c-125">Die Standardeinstellung ist Identification.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-125">The default is Identification.</span></span> <span data-ttu-id="b4f6c-126">Dieses Attribut ist vom Typ <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-126">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4f6c-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b4f6c-127">Child Elements</span></span>  
 <span data-ttu-id="b4f6c-128">Keine</span><span class="sxs-lookup"><span data-stu-id="b4f6c-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b4f6c-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b4f6c-129">Parent Elements</span></span>  
  
|<span data-ttu-id="b4f6c-130">Element</span><span class="sxs-lookup"><span data-stu-id="b4f6c-130">Element</span></span>|<span data-ttu-id="b4f6c-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4f6c-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4f6c-132">\<Clientanmelde Informationen ></span><span class="sxs-lookup"><span data-stu-id="b4f6c-132">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="b4f6c-133">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-133">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4f6c-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4f6c-134">Remarks</span></span>  
 <span data-ttu-id="b4f6c-135">Ein Digest ist ein Hash, der mit einem Algorithmus und einer Reihe von Eingaben ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-135">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="b4f6c-136">Der Authentifizierer und der Authentifizierte verständigen sich über einen Algorithmus und tauschen die für die Eingabe verwendeten Daten aus.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-136">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="b4f6c-137">Der Client kann den Hash berechnen und an den Dienst senden.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-137">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="b4f6c-138">Der Dienst berechnet den Hash ebenfalls und vergleicht die Werte.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-138">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="b4f6c-139">Bei einer Übereinstimmung ist die Überprüfung des Clients erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-139">A match validates the client.</span></span>  
  
 <span data-ttu-id="b4f6c-140">Diese Funktion muss mit Active Directory unter Windows und unter IIS (Internet Information Services) aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="b4f6c-140">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="b4f6c-141">Weitere Informationen finden Sie unter [Digest-Authentifizierung in IIS 6,0](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="b4f6c-141">For more information, see [Digest Authentication in IIS 6.0](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4f6c-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4f6c-142">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="b4f6c-143">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="b4f6c-143">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="b4f6c-144">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="b4f6c-144">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="b4f6c-145">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="b4f6c-145">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="b4f6c-146">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="b4f6c-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

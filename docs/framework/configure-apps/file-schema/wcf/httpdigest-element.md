---
title: <httpDigest>-Element
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 0ffaba218d31a77407c598f8b7fa0260daa4e39c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556901"
---
# <a name="httpdigest-element"></a><span data-ttu-id="7b1fb-102">\<httpDigest>-Element</span><span class="sxs-lookup"><span data-stu-id="7b1fb-102">\<httpDigest> Element</span></span>
<span data-ttu-id="7b1fb-103">Gibt Anmeldeinformationen vom Typ Digest an, die bei der Authentifizierung des Clients bei einem Dienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7b1fb-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpDigest>**  
  
## <a name="syntax"></a><span data-ttu-id="7b1fb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b1fb-104">Syntax</span></span>  
  
```xml  
<httpDigest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b1fb-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7b1fb-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7b1fb-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7b1fb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b1fb-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="7b1fb-107">Attributes</span></span>  
  
|<span data-ttu-id="7b1fb-108">attribute</span><span class="sxs-lookup"><span data-stu-id="7b1fb-108">Attribute</span></span>|<span data-ttu-id="7b1fb-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7b1fb-109">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="7b1fb-110">Legt die Identitätswechseleinstellungen fest, die der Client an den Server weitergibt.</span><span class="sxs-lookup"><span data-stu-id="7b1fb-110">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="7b1fb-111">Der Identitätswechselmodus, den der Client auswählt, wird nicht auf dem Server durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="7b1fb-111">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="7b1fb-112">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="7b1fb-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7b1fb-113">-Identifikation: der Server kann die Identität und die Berechtigungen des Clients erhalten, kann jedoch nicht die Identität des Clients annehmen.</span><span class="sxs-lookup"><span data-stu-id="7b1fb-113">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="7b1fb-114">-Identitätswechsel: der Server kann den Sicherheitskontext des Clients auf dem lokalen System imitieren.</span><span class="sxs-lookup"><span data-stu-id="7b1fb-114">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="7b1fb-115">-Delegierung: der Server kann den Sicherheitskontext des Clients auf Remote Systemen imitieren.</span><span class="sxs-lookup"><span data-stu-id="7b1fb-115">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="7b1fb-116">-Anonymous: der Server kann den Client nicht annehmen oder ihn identifizieren.</span><span class="sxs-lookup"><span data-stu-id="7b1fb-116">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="7b1fb-117">-None: Es wurde keine Identitätswechsel Ebene zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="7b1fb-117">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="7b1fb-118">Die Standardeinstellung ist Identification.</span><span class="sxs-lookup"><span data-stu-id="7b1fb-118">The default is Identification.</span></span> <span data-ttu-id="7b1fb-119">Dieses Attribut ist vom Typ <xref:System.Security.Principal.TokenImpersonationLevel>.</span><span class="sxs-lookup"><span data-stu-id="7b1fb-119">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b1fb-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7b1fb-120">Child Elements</span></span>  
 <span data-ttu-id="7b1fb-121">Keine</span><span class="sxs-lookup"><span data-stu-id="7b1fb-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7b1fb-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7b1fb-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7b1fb-123">Element</span><span class="sxs-lookup"><span data-stu-id="7b1fb-123">Element</span></span>|<span data-ttu-id="7b1fb-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7b1fb-124">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="7b1fb-125">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="7b1fb-125">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b1fb-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7b1fb-126">Remarks</span></span>  
 <span data-ttu-id="7b1fb-127">Ein Digest ist ein Hash, der mit einem Algorithmus und einer Reihe von Eingaben ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="7b1fb-127">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="7b1fb-128">Der Authentifizierer und der Authentifizierte verständigen sich über einen Algorithmus und tauschen die für die Eingabe verwendeten Daten aus.</span><span class="sxs-lookup"><span data-stu-id="7b1fb-128">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="7b1fb-129">Der Client kann den Hash berechnen und an den Dienst senden.</span><span class="sxs-lookup"><span data-stu-id="7b1fb-129">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="7b1fb-130">Der Dienst berechnet den Hash ebenfalls und vergleicht die Werte.</span><span class="sxs-lookup"><span data-stu-id="7b1fb-130">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="7b1fb-131">Bei einer Übereinstimmung ist die Überprüfung des Clients erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="7b1fb-131">A match validates the client.</span></span>  
  
 <span data-ttu-id="7b1fb-132">Diese Funktion muss mit Active Directory unter Windows und unter IIS (Internet Information Services) aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="7b1fb-132">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="7b1fb-133">Weitere Informationen finden Sie unter [Digest-Authentifizierung in IIS 6,0](/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="7b1fb-133">For more information, see [Digest Authentication in IIS 6.0](/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b1fb-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b1fb-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="7b1fb-135">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="7b1fb-135">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="7b1fb-136">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="7b1fb-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="7b1fb-137">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="7b1fb-137">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="7b1fb-138">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="7b1fb-138">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)

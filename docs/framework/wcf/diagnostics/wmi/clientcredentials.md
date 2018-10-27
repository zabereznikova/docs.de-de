---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: 8b6200f84f352d49cf142d9c8b97d1c2b36149b2
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180899"
---
# <a name="clientcredentials"></a><span data-ttu-id="e7e77-102">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="e7e77-102">ClientCredentials</span></span>
<span data-ttu-id="e7e77-103">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="e7e77-103">ClientCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7e77-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7e77-104">Syntax</span></span>  
  
```csharp
class ClientCredentials : Behavior  
{  
  string ClientCertificate;  
  string HttpDigest;  
  string IssuedToken;  
  string Peer;  
  string ServiceCertificate;  
  boolean SupportInteractive;  
  string UserName;  
  string Windows;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e7e77-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e7e77-105">Methods</span></span>  
 <span data-ttu-id="e7e77-106">Die Klasse ClientCredentials definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="e7e77-106">The ClientCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e7e77-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e7e77-107">Properties</span></span>  
 <span data-ttu-id="e7e77-108">Die Klasse ClientCredentials verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="e7e77-108">The ClientCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="e7e77-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="e7e77-109">ClientCertificate</span></span>  
 <span data-ttu-id="e7e77-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e7e77-110">Data type: string</span></span>  
  
 <span data-ttu-id="e7e77-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e7e77-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7e77-112">Das X.509-Zertifikat, das der Client benutzt, um den Dienst zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="e7e77-112">The X.509 certificate the client uses to authenticate to the service.</span></span>  
  
### <a name="httpdigest"></a><span data-ttu-id="e7e77-113">HttpDigest</span><span class="sxs-lookup"><span data-stu-id="e7e77-113">HttpDigest</span></span>  
 <span data-ttu-id="e7e77-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e7e77-114">Data type: string</span></span>  
  
 <span data-ttu-id="e7e77-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e7e77-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7e77-116">Die aktuellen Http-Digestanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="e7e77-116">The current Http Digest credential.</span></span>  
  
### <a name="issuedtoken"></a><span data-ttu-id="e7e77-117">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="e7e77-117">IssuedToken</span></span>  
 <span data-ttu-id="e7e77-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e7e77-118">Data type: string</span></span>  
  
 <span data-ttu-id="e7e77-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e7e77-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7e77-120">Die Endpunktadresse und die Bindung, die verwendet werden, um den lokalen Sicherheitstokendienst anzusprechen.</span><span class="sxs-lookup"><span data-stu-id="e7e77-120">The endpoint address and binding used to contact the local security token service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="e7e77-121">Peer</span><span class="sxs-lookup"><span data-stu-id="e7e77-121">Peer</span></span>  
 <span data-ttu-id="e7e77-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e7e77-122">Data type: string</span></span>  
  
 <span data-ttu-id="e7e77-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e7e77-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7e77-124">Die Anmeldeinformationen, die der Peerknoten verwendet, um sich anderen Knoten im Netz gegenüber zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="e7e77-124">The credentials that the peer node uses to authenticate itself to other nodes in the mesh.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="e7e77-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="e7e77-125">ServiceCertificate</span></span>  
 <span data-ttu-id="e7e77-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e7e77-126">Data type: string</span></span>  
  
 <span data-ttu-id="e7e77-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e7e77-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7e77-128">Das X.509-Zertifikat des Diensts.</span><span class="sxs-lookup"><span data-stu-id="e7e77-128">The service's X.509 certificate.</span></span>  
  
### <a name="supportinteractive"></a><span data-ttu-id="e7e77-129">SupportInteractive</span><span class="sxs-lookup"><span data-stu-id="e7e77-129">SupportInteractive</span></span>  
 <span data-ttu-id="e7e77-130">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="e7e77-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="e7e77-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e7e77-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7e77-132">Ein boolescher Wert, der festlegt, ob die Anmeldeinformationen interaktive Verhandlung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e7e77-132">A Boolean value that specifies whether the credential supports interactive negotiation.</span></span>  
  
### <a name="username"></a><span data-ttu-id="e7e77-133">UserName</span><span class="sxs-lookup"><span data-stu-id="e7e77-133">UserName</span></span>  
 <span data-ttu-id="e7e77-134">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e7e77-134">Data type: string</span></span>  
  
 <span data-ttu-id="e7e77-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e7e77-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7e77-136">Der Benutzername und das Kennwort, die der Client verwendet, um sich dem Dienst gegenüber zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="e7e77-136">The username and password the client uses to authenticate itself to the service.</span></span>  
  
### <a name="windows"></a><span data-ttu-id="e7e77-137">Windows</span><span class="sxs-lookup"><span data-stu-id="e7e77-137">Windows</span></span>  
 <span data-ttu-id="e7e77-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e7e77-138">Data type: string</span></span>  
  
 <span data-ttu-id="e7e77-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e7e77-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7e77-140">Die Windows-Anmeldeinformationen, die der Client verwendet, um sich dem Dienst gegenüber zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="e7e77-140">The windows credentials the client uses to authenticate itself to the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7e77-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e7e77-141">Requirements</span></span>  
  
|<span data-ttu-id="e7e77-142">MOF</span><span class="sxs-lookup"><span data-stu-id="e7e77-142">MOF</span></span>|<span data-ttu-id="e7e77-143">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e7e77-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e7e77-144">Namespace</span><span class="sxs-lookup"><span data-stu-id="e7e77-144">Namespace</span></span>|<span data-ttu-id="e7e77-145">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e7e77-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e7e77-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7e77-146">See Also</span></span>  
 <xref:System.ServiceModel.Description.ClientCredentials>

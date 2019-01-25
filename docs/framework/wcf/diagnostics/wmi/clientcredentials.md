---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: 410a133ae3041db00ecb7a17677afe6538ef1f4f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632737"
---
# <a name="clientcredentials"></a><span data-ttu-id="e81d2-102">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="e81d2-102">ClientCredentials</span></span>
<span data-ttu-id="e81d2-103">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="e81d2-103">ClientCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e81d2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e81d2-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="e81d2-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e81d2-105">Methods</span></span>  
 <span data-ttu-id="e81d2-106">Die Klasse ClientCredentials definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="e81d2-106">The ClientCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e81d2-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e81d2-107">Properties</span></span>  
 <span data-ttu-id="e81d2-108">Die Klasse ClientCredentials verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="e81d2-108">The ClientCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="e81d2-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="e81d2-109">ClientCertificate</span></span>  
 <span data-ttu-id="e81d2-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e81d2-110">Data type: string</span></span>  
  
 <span data-ttu-id="e81d2-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e81d2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e81d2-112">Das X.509-Zertifikat, das der Client benutzt, um den Dienst zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="e81d2-112">The X.509 certificate the client uses to authenticate to the service.</span></span>  
  
### <a name="httpdigest"></a><span data-ttu-id="e81d2-113">HttpDigest</span><span class="sxs-lookup"><span data-stu-id="e81d2-113">HttpDigest</span></span>  
 <span data-ttu-id="e81d2-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e81d2-114">Data type: string</span></span>  
  
 <span data-ttu-id="e81d2-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e81d2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e81d2-116">Die aktuellen Http-Hashwertanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="e81d2-116">The current Http Digest credential.</span></span>  
  
### <a name="issuedtoken"></a><span data-ttu-id="e81d2-117">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="e81d2-117">IssuedToken</span></span>  
 <span data-ttu-id="e81d2-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e81d2-118">Data type: string</span></span>  
  
 <span data-ttu-id="e81d2-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e81d2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e81d2-120">Die Endpunktadresse und die Bindung, die verwendet werden, um den lokalen Sicherheitstokendienst anzusprechen.</span><span class="sxs-lookup"><span data-stu-id="e81d2-120">The endpoint address and binding used to contact the local security token service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="e81d2-121">Peer</span><span class="sxs-lookup"><span data-stu-id="e81d2-121">Peer</span></span>  
 <span data-ttu-id="e81d2-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e81d2-122">Data type: string</span></span>  
  
 <span data-ttu-id="e81d2-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e81d2-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e81d2-124">Die Anmeldeinformationen, die der Peerknoten verwendet, um sich anderen Knoten im Netz gegenüber zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="e81d2-124">The credentials that the peer node uses to authenticate itself to other nodes in the mesh.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="e81d2-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="e81d2-125">ServiceCertificate</span></span>  
 <span data-ttu-id="e81d2-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e81d2-126">Data type: string</span></span>  
  
 <span data-ttu-id="e81d2-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e81d2-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e81d2-128">Das X.509-Zertifikat des Diensts.</span><span class="sxs-lookup"><span data-stu-id="e81d2-128">The service's X.509 certificate.</span></span>  
  
### <a name="supportinteractive"></a><span data-ttu-id="e81d2-129">SupportInteractive</span><span class="sxs-lookup"><span data-stu-id="e81d2-129">SupportInteractive</span></span>  
 <span data-ttu-id="e81d2-130">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="e81d2-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="e81d2-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e81d2-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e81d2-132">Ein boolescher Wert, der festlegt, ob die Anmeldeinformationen interaktive Verhandlung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e81d2-132">A Boolean value that specifies whether the credential supports interactive negotiation.</span></span>  
  
### <a name="username"></a><span data-ttu-id="e81d2-133">UserName</span><span class="sxs-lookup"><span data-stu-id="e81d2-133">UserName</span></span>  
 <span data-ttu-id="e81d2-134">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e81d2-134">Data type: string</span></span>  
  
 <span data-ttu-id="e81d2-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e81d2-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e81d2-136">Der Benutzername und das Kennwort, die der Client verwendet, um sich dem Dienst gegenüber zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="e81d2-136">The username and password the client uses to authenticate itself to the service.</span></span>  
  
### <a name="windows"></a><span data-ttu-id="e81d2-137">Windows</span><span class="sxs-lookup"><span data-stu-id="e81d2-137">Windows</span></span>  
 <span data-ttu-id="e81d2-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e81d2-138">Data type: string</span></span>  
  
 <span data-ttu-id="e81d2-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e81d2-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e81d2-140">Die Windows-Anmeldeinformationen, die der Client verwendet, um sich dem Dienst gegenüber zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="e81d2-140">The windows credentials the client uses to authenticate itself to the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e81d2-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e81d2-141">Requirements</span></span>  
  
|<span data-ttu-id="e81d2-142">MOF</span><span class="sxs-lookup"><span data-stu-id="e81d2-142">MOF</span></span>|<span data-ttu-id="e81d2-143">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e81d2-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e81d2-144">Namespace</span><span class="sxs-lookup"><span data-stu-id="e81d2-144">Namespace</span></span>|<span data-ttu-id="e81d2-145">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e81d2-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e81d2-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e81d2-146">See also</span></span>
- <xref:System.ServiceModel.Description.ClientCredentials>

---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: c3adc675bb6c1e9011459a88fd7dc8e8cf63a880
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59771204"
---
# <a name="clientcredentials"></a><span data-ttu-id="4d0bd-102">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="4d0bd-102">ClientCredentials</span></span>
<span data-ttu-id="4d0bd-103">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="4d0bd-103">ClientCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d0bd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d0bd-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="4d0bd-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="4d0bd-105">Methods</span></span>  
 <span data-ttu-id="4d0bd-106">Die Klasse ClientCredentials definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="4d0bd-106">The ClientCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4d0bd-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4d0bd-107">Properties</span></span>  
 <span data-ttu-id="4d0bd-108">Die Klasse ClientCredentials verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="4d0bd-108">The ClientCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="4d0bd-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="4d0bd-109">ClientCertificate</span></span>  
 <span data-ttu-id="4d0bd-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4d0bd-110">Data type: string</span></span>  
  
 <span data-ttu-id="4d0bd-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4d0bd-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d0bd-112">Das X.509-Zertifikat, das der Client benutzt, um den Dienst zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="4d0bd-112">The X.509 certificate the client uses to authenticate to the service.</span></span>  
  
### <a name="httpdigest"></a><span data-ttu-id="4d0bd-113">HttpDigest</span><span class="sxs-lookup"><span data-stu-id="4d0bd-113">HttpDigest</span></span>  
 <span data-ttu-id="4d0bd-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4d0bd-114">Data type: string</span></span>  
  
 <span data-ttu-id="4d0bd-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4d0bd-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d0bd-116">Die aktuellen Http-Digestanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="4d0bd-116">The current Http Digest credential.</span></span>  
  
### <a name="issuedtoken"></a><span data-ttu-id="4d0bd-117">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="4d0bd-117">IssuedToken</span></span>  
 <span data-ttu-id="4d0bd-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4d0bd-118">Data type: string</span></span>  
  
 <span data-ttu-id="4d0bd-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4d0bd-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d0bd-120">Die Endpunktadresse und die Bindung, die verwendet werden, um den lokalen Sicherheitstokendienst anzusprechen.</span><span class="sxs-lookup"><span data-stu-id="4d0bd-120">The endpoint address and binding used to contact the local security token service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="4d0bd-121">Peer</span><span class="sxs-lookup"><span data-stu-id="4d0bd-121">Peer</span></span>  
 <span data-ttu-id="4d0bd-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4d0bd-122">Data type: string</span></span>  
  
 <span data-ttu-id="4d0bd-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4d0bd-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d0bd-124">Die Anmeldeinformationen, die der Peerknoten verwendet, um sich anderen Knoten im Netz gegenüber zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="4d0bd-124">The credentials that the peer node uses to authenticate itself to other nodes in the mesh.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="4d0bd-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="4d0bd-125">ServiceCertificate</span></span>  
 <span data-ttu-id="4d0bd-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4d0bd-126">Data type: string</span></span>  
  
 <span data-ttu-id="4d0bd-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4d0bd-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d0bd-128">Das X.509-Zertifikat des Diensts.</span><span class="sxs-lookup"><span data-stu-id="4d0bd-128">The service's X.509 certificate.</span></span>  
  
### <a name="supportinteractive"></a><span data-ttu-id="4d0bd-129">SupportInteractive</span><span class="sxs-lookup"><span data-stu-id="4d0bd-129">SupportInteractive</span></span>  
 <span data-ttu-id="4d0bd-130">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="4d0bd-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="4d0bd-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4d0bd-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d0bd-132">Ein boolescher Wert, der festlegt, ob die Anmeldeinformationen interaktive Verhandlung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4d0bd-132">A Boolean value that specifies whether the credential supports interactive negotiation.</span></span>  
  
### <a name="username"></a><span data-ttu-id="4d0bd-133">UserName</span><span class="sxs-lookup"><span data-stu-id="4d0bd-133">UserName</span></span>  
 <span data-ttu-id="4d0bd-134">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4d0bd-134">Data type: string</span></span>  
  
 <span data-ttu-id="4d0bd-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4d0bd-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d0bd-136">Der Benutzername und das Kennwort, die der Client verwendet, um sich dem Dienst gegenüber zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="4d0bd-136">The username and password the client uses to authenticate itself to the service.</span></span>  
  
### <a name="windows"></a><span data-ttu-id="4d0bd-137">Windows</span><span class="sxs-lookup"><span data-stu-id="4d0bd-137">Windows</span></span>  
 <span data-ttu-id="4d0bd-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4d0bd-138">Data type: string</span></span>  
  
 <span data-ttu-id="4d0bd-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4d0bd-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d0bd-140">Die Windows-Anmeldeinformationen, die der Client verwendet, um sich dem Dienst gegenüber zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="4d0bd-140">The windows credentials the client uses to authenticate itself to the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d0bd-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4d0bd-141">Requirements</span></span>  
  
|<span data-ttu-id="4d0bd-142">MOF</span><span class="sxs-lookup"><span data-stu-id="4d0bd-142">MOF</span></span>|<span data-ttu-id="4d0bd-143">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4d0bd-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4d0bd-144">Namespace</span><span class="sxs-lookup"><span data-stu-id="4d0bd-144">Namespace</span></span>|<span data-ttu-id="4d0bd-145">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4d0bd-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d0bd-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d0bd-146">See also</span></span>

- <xref:System.ServiceModel.Description.ClientCredentials>

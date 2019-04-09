---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: c3adc675bb6c1e9011459a88fd7dc8e8cf63a880
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226585"
---
# <a name="clientcredentials"></a><span data-ttu-id="34bdb-102">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="34bdb-102">ClientCredentials</span></span>
<span data-ttu-id="34bdb-103">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="34bdb-103">ClientCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34bdb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="34bdb-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="34bdb-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="34bdb-105">Methods</span></span>  
 <span data-ttu-id="34bdb-106">Die Klasse ClientCredentials definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="34bdb-106">The ClientCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="34bdb-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="34bdb-107">Properties</span></span>  
 <span data-ttu-id="34bdb-108">Die Klasse ClientCredentials verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="34bdb-108">The ClientCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="34bdb-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="34bdb-109">ClientCertificate</span></span>  
 <span data-ttu-id="34bdb-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="34bdb-110">Data type: string</span></span>  
  
 <span data-ttu-id="34bdb-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="34bdb-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="34bdb-112">Das X.509-Zertifikat, das der Client benutzt, um den Dienst zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="34bdb-112">The X.509 certificate the client uses to authenticate to the service.</span></span>  
  
### <a name="httpdigest"></a><span data-ttu-id="34bdb-113">HttpDigest</span><span class="sxs-lookup"><span data-stu-id="34bdb-113">HttpDigest</span></span>  
 <span data-ttu-id="34bdb-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="34bdb-114">Data type: string</span></span>  
  
 <span data-ttu-id="34bdb-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="34bdb-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="34bdb-116">Die aktuellen Http-Digestanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="34bdb-116">The current Http Digest credential.</span></span>  
  
### <a name="issuedtoken"></a><span data-ttu-id="34bdb-117">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="34bdb-117">IssuedToken</span></span>  
 <span data-ttu-id="34bdb-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="34bdb-118">Data type: string</span></span>  
  
 <span data-ttu-id="34bdb-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="34bdb-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="34bdb-120">Die Endpunktadresse und die Bindung, die verwendet werden, um den lokalen Sicherheitstokendienst anzusprechen.</span><span class="sxs-lookup"><span data-stu-id="34bdb-120">The endpoint address and binding used to contact the local security token service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="34bdb-121">Peer</span><span class="sxs-lookup"><span data-stu-id="34bdb-121">Peer</span></span>  
 <span data-ttu-id="34bdb-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="34bdb-122">Data type: string</span></span>  
  
 <span data-ttu-id="34bdb-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="34bdb-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="34bdb-124">Die Anmeldeinformationen, die der Peerknoten verwendet, um sich anderen Knoten im Netz gegenüber zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="34bdb-124">The credentials that the peer node uses to authenticate itself to other nodes in the mesh.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="34bdb-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="34bdb-125">ServiceCertificate</span></span>  
 <span data-ttu-id="34bdb-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="34bdb-126">Data type: string</span></span>  
  
 <span data-ttu-id="34bdb-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="34bdb-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="34bdb-128">Das X.509-Zertifikat des Diensts.</span><span class="sxs-lookup"><span data-stu-id="34bdb-128">The service's X.509 certificate.</span></span>  
  
### <a name="supportinteractive"></a><span data-ttu-id="34bdb-129">SupportInteractive</span><span class="sxs-lookup"><span data-stu-id="34bdb-129">SupportInteractive</span></span>  
 <span data-ttu-id="34bdb-130">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="34bdb-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="34bdb-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="34bdb-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="34bdb-132">Ein boolescher Wert, der festlegt, ob die Anmeldeinformationen interaktive Verhandlung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="34bdb-132">A Boolean value that specifies whether the credential supports interactive negotiation.</span></span>  
  
### <a name="username"></a><span data-ttu-id="34bdb-133">UserName</span><span class="sxs-lookup"><span data-stu-id="34bdb-133">UserName</span></span>  
 <span data-ttu-id="34bdb-134">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="34bdb-134">Data type: string</span></span>  
  
 <span data-ttu-id="34bdb-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="34bdb-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="34bdb-136">Der Benutzername und das Kennwort, die der Client verwendet, um sich dem Dienst gegenüber zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="34bdb-136">The username and password the client uses to authenticate itself to the service.</span></span>  
  
### <a name="windows"></a><span data-ttu-id="34bdb-137">Windows</span><span class="sxs-lookup"><span data-stu-id="34bdb-137">Windows</span></span>  
 <span data-ttu-id="34bdb-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="34bdb-138">Data type: string</span></span>  
  
 <span data-ttu-id="34bdb-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="34bdb-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="34bdb-140">Die Windows-Anmeldeinformationen, die der Client verwendet, um sich dem Dienst gegenüber zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="34bdb-140">The windows credentials the client uses to authenticate itself to the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34bdb-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="34bdb-141">Requirements</span></span>  
  
|<span data-ttu-id="34bdb-142">MOF</span><span class="sxs-lookup"><span data-stu-id="34bdb-142">MOF</span></span>|<span data-ttu-id="34bdb-143">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="34bdb-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="34bdb-144">Namespace</span><span class="sxs-lookup"><span data-stu-id="34bdb-144">Namespace</span></span>|<span data-ttu-id="34bdb-145">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="34bdb-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="34bdb-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34bdb-146">See also</span></span>

- <xref:System.ServiceModel.Description.ClientCredentials>

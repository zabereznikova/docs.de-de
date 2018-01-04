---
title: ClientCredentials
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d6fba00dc98f6b5525e1cb9588ed52bc483a665e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="clientcredentials"></a><span data-ttu-id="ce263-102">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="ce263-102">ClientCredentials</span></span>
<span data-ttu-id="ce263-103">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="ce263-103">ClientCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce263-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce263-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="ce263-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="ce263-105">Methods</span></span>  
 <span data-ttu-id="ce263-106">Die Klasse ClientCredentials definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="ce263-106">The ClientCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ce263-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ce263-107">Properties</span></span>  
 <span data-ttu-id="ce263-108">Die Klasse ClientCredentials verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="ce263-108">The ClientCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="ce263-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="ce263-109">ClientCertificate</span></span>  
 <span data-ttu-id="ce263-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="ce263-110">Data type: string</span></span>  
  
 <span data-ttu-id="ce263-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ce263-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ce263-112">Das X.509-Zertifikat, das der Client benutzt, um den Dienst zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="ce263-112">The X.509 certificate the client uses to authenticate to the service.</span></span>  
  
### <a name="httpdigest"></a><span data-ttu-id="ce263-113">HttpDigest</span><span class="sxs-lookup"><span data-stu-id="ce263-113">HttpDigest</span></span>  
 <span data-ttu-id="ce263-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="ce263-114">Data type: string</span></span>  
  
 <span data-ttu-id="ce263-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ce263-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ce263-116">Die aktuellen Http-Digestanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="ce263-116">The current Http Digest credential.</span></span>  
  
### <a name="issuedtoken"></a><span data-ttu-id="ce263-117">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="ce263-117">IssuedToken</span></span>  
 <span data-ttu-id="ce263-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="ce263-118">Data type: string</span></span>  
  
 <span data-ttu-id="ce263-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ce263-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ce263-120">Die Endpunktadresse und die Bindung, die verwendet werden, um den lokalen Sicherheitstokendienst anzusprechen.</span><span class="sxs-lookup"><span data-stu-id="ce263-120">The endpoint address and binding used to contact the local security token service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="ce263-121">Peer</span><span class="sxs-lookup"><span data-stu-id="ce263-121">Peer</span></span>  
 <span data-ttu-id="ce263-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="ce263-122">Data type: string</span></span>  
  
 <span data-ttu-id="ce263-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ce263-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ce263-124">Die Anmeldeinformationen, die der Peerknoten verwendet, um sich anderen Knoten im Netz gegenüber zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="ce263-124">The credentials that the peer node uses to authenticate itself to other nodes in the mesh.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="ce263-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="ce263-125">ServiceCertificate</span></span>  
 <span data-ttu-id="ce263-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="ce263-126">Data type: string</span></span>  
  
 <span data-ttu-id="ce263-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ce263-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ce263-128">Das X.509-Zertifikat des Diensts.</span><span class="sxs-lookup"><span data-stu-id="ce263-128">The service's X.509 certificate.</span></span>  
  
### <a name="supportinteractive"></a><span data-ttu-id="ce263-129">SupportInteractive</span><span class="sxs-lookup"><span data-stu-id="ce263-129">SupportInteractive</span></span>  
 <span data-ttu-id="ce263-130">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="ce263-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="ce263-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ce263-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ce263-132">Ein boolescher Wert, der festlegt, ob die Anmeldeinformationen interaktive Verhandlung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ce263-132">A Boolean value that specifies whether the credential supports interactive negotiation.</span></span>  
  
### <a name="username"></a><span data-ttu-id="ce263-133">UserName</span><span class="sxs-lookup"><span data-stu-id="ce263-133">UserName</span></span>  
 <span data-ttu-id="ce263-134">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="ce263-134">Data type: string</span></span>  
  
 <span data-ttu-id="ce263-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ce263-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ce263-136">Der Benutzername und das Kennwort, die der Client verwendet, um sich dem Dienst gegenüber zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="ce263-136">The username and password the client uses to authenticate itself to the service.</span></span>  
  
### <a name="windows"></a><span data-ttu-id="ce263-137">Windows</span><span class="sxs-lookup"><span data-stu-id="ce263-137">Windows</span></span>  
 <span data-ttu-id="ce263-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="ce263-138">Data type: string</span></span>  
  
 <span data-ttu-id="ce263-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ce263-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ce263-140">Die Windows-Anmeldeinformationen, die der Client verwendet, um sich dem Dienst gegenüber zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="ce263-140">The windows credentials the client uses to authenticate itself to the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce263-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ce263-141">Requirements</span></span>  
  
|<span data-ttu-id="ce263-142">MOF</span><span class="sxs-lookup"><span data-stu-id="ce263-142">MOF</span></span>|<span data-ttu-id="ce263-143">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ce263-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ce263-144">Namespace</span><span class="sxs-lookup"><span data-stu-id="ce263-144">Namespace</span></span>|<span data-ttu-id="ce263-145">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ce263-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce263-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce263-146">See Also</span></span>  
 <xref:System.ServiceModel.Description.ClientCredentials>

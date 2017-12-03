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
ms.openlocfilehash: 55f7ef12f67bd719f72f158a1fca6f120b4f448a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="clientcredentials"></a><span data-ttu-id="f977f-102">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="f977f-102">ClientCredentials</span></span>
<span data-ttu-id="f977f-103">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="f977f-103">ClientCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f977f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f977f-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="f977f-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f977f-105">Methods</span></span>  
 <span data-ttu-id="f977f-106">Die Klasse ClientCredentials definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="f977f-106">The ClientCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f977f-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f977f-107">Properties</span></span>  
 <span data-ttu-id="f977f-108">Die Klasse ClientCredentials verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f977f-108">The ClientCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="f977f-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="f977f-109">ClientCertificate</span></span>  
 <span data-ttu-id="f977f-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f977f-110">Data type: string</span></span>  
  
 <span data-ttu-id="f977f-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f977f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f977f-112">Das X.509-Zertifikat, das der Client benutzt, um den Dienst zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="f977f-112">The X.509 certificate the client uses to authenticate to the service.</span></span>  
  
### <a name="httpdigest"></a><span data-ttu-id="f977f-113">HttpDigest</span><span class="sxs-lookup"><span data-stu-id="f977f-113">HttpDigest</span></span>  
 <span data-ttu-id="f977f-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f977f-114">Data type: string</span></span>  
  
 <span data-ttu-id="f977f-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f977f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f977f-116">Die aktuellen Http-Digestanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="f977f-116">The current Http Digest credential.</span></span>  
  
### <a name="issuedtoken"></a><span data-ttu-id="f977f-117">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="f977f-117">IssuedToken</span></span>  
 <span data-ttu-id="f977f-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f977f-118">Data type: string</span></span>  
  
 <span data-ttu-id="f977f-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f977f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f977f-120">Die Endpunktadresse und die Bindung, die verwendet werden, um den lokalen Sicherheitstokendienst anzusprechen.</span><span class="sxs-lookup"><span data-stu-id="f977f-120">The endpoint address and binding used to contact the local security token service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="f977f-121">Peer</span><span class="sxs-lookup"><span data-stu-id="f977f-121">Peer</span></span>  
 <span data-ttu-id="f977f-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f977f-122">Data type: string</span></span>  
  
 <span data-ttu-id="f977f-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f977f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f977f-124">Die Anmeldeinformationen, die der Peerknoten verwendet, um sich anderen Knoten im Netz gegenüber zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="f977f-124">The credentials that the peer node uses to authenticate itself to other nodes in the mesh.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="f977f-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="f977f-125">ServiceCertificate</span></span>  
 <span data-ttu-id="f977f-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f977f-126">Data type: string</span></span>  
  
 <span data-ttu-id="f977f-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f977f-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f977f-128">Das X.509-Zertifikat des Diensts.</span><span class="sxs-lookup"><span data-stu-id="f977f-128">The service's X.509 certificate.</span></span>  
  
### <a name="supportinteractive"></a><span data-ttu-id="f977f-129">SupportInteractive</span><span class="sxs-lookup"><span data-stu-id="f977f-129">SupportInteractive</span></span>  
 <span data-ttu-id="f977f-130">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="f977f-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="f977f-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f977f-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f977f-132">Ein boolescher Wert, der festlegt, ob die Anmeldeinformationen interaktive Verhandlung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f977f-132">A Boolean value that specifies whether the credential supports interactive negotiation.</span></span>  
  
### <a name="username"></a><span data-ttu-id="f977f-133">UserName</span><span class="sxs-lookup"><span data-stu-id="f977f-133">UserName</span></span>  
 <span data-ttu-id="f977f-134">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f977f-134">Data type: string</span></span>  
  
 <span data-ttu-id="f977f-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f977f-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f977f-136">Der Benutzername und das Kennwort, die der Client verwendet, um sich dem Dienst gegenüber zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="f977f-136">The username and password the client uses to authenticate itself to the service.</span></span>  
  
### <a name="windows"></a><span data-ttu-id="f977f-137">Windows</span><span class="sxs-lookup"><span data-stu-id="f977f-137">Windows</span></span>  
 <span data-ttu-id="f977f-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f977f-138">Data type: string</span></span>  
  
 <span data-ttu-id="f977f-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f977f-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f977f-140">Die Windows-Anmeldeinformationen, die der Client verwendet, um sich dem Dienst gegenüber zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="f977f-140">The windows credentials the client uses to authenticate itself to the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f977f-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f977f-141">Requirements</span></span>  
  
|<span data-ttu-id="f977f-142">MOF</span><span class="sxs-lookup"><span data-stu-id="f977f-142">MOF</span></span>|<span data-ttu-id="f977f-143">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f977f-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f977f-144">Namespace</span><span class="sxs-lookup"><span data-stu-id="f977f-144">Namespace</span></span>|<span data-ttu-id="f977f-145">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f977f-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f977f-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f977f-146">See Also</span></span>  
 <xref:System.ServiceModel.Description.ClientCredentials>

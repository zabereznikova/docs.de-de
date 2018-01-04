---
title: ServiceCredentials
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 73fad36b5bf14745ca70d297fa988b90d46990df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="servicecredentials"></a><span data-ttu-id="4f508-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="4f508-102">ServiceCredentials</span></span>
<span data-ttu-id="4f508-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="4f508-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f508-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f508-104">Syntax</span></span>  
  
```  
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4f508-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="4f508-105">Methods</span></span>  
 <span data-ttu-id="4f508-106">Die Klasse ServiceCredentials definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="4f508-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4f508-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="4f508-107">Properties</span></span>  
 <span data-ttu-id="4f508-108">Die Klasse ServiceCredentials verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="4f508-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="4f508-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="4f508-109">ClientCertificate</span></span>  
 <span data-ttu-id="4f508-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4f508-110">Data type: string</span></span>  
  
 <span data-ttu-id="4f508-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4f508-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f508-112">Die Authentifizierungs- und Bereitstellungseinstellungen des Clientzertifikats für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="4f508-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="4f508-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="4f508-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="4f508-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4f508-114">Data type: string</span></span>  
  
 <span data-ttu-id="4f508-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4f508-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f508-116">Die Authentifizierungseinstellungen des aktuell ausgegebenen Tokens für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="4f508-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="4f508-117">Peer</span><span class="sxs-lookup"><span data-stu-id="4f508-117">Peer</span></span>  
 <span data-ttu-id="4f508-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4f508-118">Data type: string</span></span>  
  
 <span data-ttu-id="4f508-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4f508-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f508-120">Die aktuellen Authentifizierungs- und Bereitstellungseinstellungen für Anmeldeinformationen, die von Peertransportendpunkten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4f508-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="4f508-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="4f508-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="4f508-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4f508-122">Data type: string</span></span>  
  
 <span data-ttu-id="4f508-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4f508-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f508-124">Gibt die aktuellen sicheren Konversationseinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="4f508-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="4f508-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="4f508-125">ServiceCertificate</span></span>  
 <span data-ttu-id="4f508-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4f508-126">Data type: string</span></span>  
  
 <span data-ttu-id="4f508-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4f508-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f508-128">Das diesem Dienst zugeordnete Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="4f508-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="4f508-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="4f508-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="4f508-130">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4f508-130">Data type: string</span></span>  
  
 <span data-ttu-id="4f508-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4f508-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f508-132">Die Benutzernamen-/Kennworteinstellungen für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="4f508-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="4f508-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="4f508-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="4f508-134">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4f508-134">Data type: string</span></span>  
  
 <span data-ttu-id="4f508-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="4f508-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4f508-136">Die Windows-Authentifizierungseinstellungen für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="4f508-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f508-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f508-137">Requirements</span></span>  
  
|<span data-ttu-id="4f508-138">MOF</span><span class="sxs-lookup"><span data-stu-id="4f508-138">MOF</span></span>|<span data-ttu-id="4f508-139">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4f508-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4f508-140">Namespace</span><span class="sxs-lookup"><span data-stu-id="4f508-140">Namespace</span></span>|<span data-ttu-id="4f508-141">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4f508-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f508-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f508-142">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceCredentials>

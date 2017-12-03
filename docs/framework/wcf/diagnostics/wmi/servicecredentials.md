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
ms.openlocfilehash: 89aff21ed916e1b486a191f86dde5ed8b3e4ba22
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="servicecredentials"></a><span data-ttu-id="971df-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="971df-102">ServiceCredentials</span></span>
<span data-ttu-id="971df-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="971df-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="971df-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="971df-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="971df-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="971df-105">Methods</span></span>  
 <span data-ttu-id="971df-106">Die Klasse ServiceCredentials definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="971df-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="971df-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="971df-107">Properties</span></span>  
 <span data-ttu-id="971df-108">Die Klasse ServiceCredentials verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="971df-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="971df-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="971df-109">ClientCertificate</span></span>  
 <span data-ttu-id="971df-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="971df-110">Data type: string</span></span>  
  
 <span data-ttu-id="971df-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="971df-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="971df-112">Die Authentifizierungs- und Bereitstellungseinstellungen des Clientzertifikats für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="971df-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="971df-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="971df-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="971df-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="971df-114">Data type: string</span></span>  
  
 <span data-ttu-id="971df-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="971df-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="971df-116">Die Authentifizierungseinstellungen des aktuell ausgegebenen Tokens für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="971df-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="971df-117">Peer</span><span class="sxs-lookup"><span data-stu-id="971df-117">Peer</span></span>  
 <span data-ttu-id="971df-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="971df-118">Data type: string</span></span>  
  
 <span data-ttu-id="971df-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="971df-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="971df-120">Die aktuellen Authentifizierungs- und Bereitstellungseinstellungen für Anmeldeinformationen, die von Peertransportendpunkten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="971df-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="971df-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="971df-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="971df-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="971df-122">Data type: string</span></span>  
  
 <span data-ttu-id="971df-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="971df-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="971df-124">Gibt die aktuellen sicheren Konversationseinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="971df-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="971df-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="971df-125">ServiceCertificate</span></span>  
 <span data-ttu-id="971df-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="971df-126">Data type: string</span></span>  
  
 <span data-ttu-id="971df-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="971df-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="971df-128">Das diesem Dienst zugeordnete Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="971df-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="971df-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="971df-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="971df-130">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="971df-130">Data type: string</span></span>  
  
 <span data-ttu-id="971df-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="971df-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="971df-132">Die Benutzernamen-/Kennworteinstellungen für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="971df-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="971df-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="971df-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="971df-134">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="971df-134">Data type: string</span></span>  
  
 <span data-ttu-id="971df-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="971df-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="971df-136">Die Windows-Authentifizierungseinstellungen für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="971df-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="971df-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="971df-137">Requirements</span></span>  
  
|<span data-ttu-id="971df-138">MOF</span><span class="sxs-lookup"><span data-stu-id="971df-138">MOF</span></span>|<span data-ttu-id="971df-139">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="971df-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="971df-140">Namespace</span><span class="sxs-lookup"><span data-stu-id="971df-140">Namespace</span></span>|<span data-ttu-id="971df-141">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="971df-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="971df-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="971df-142">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceCredentials>

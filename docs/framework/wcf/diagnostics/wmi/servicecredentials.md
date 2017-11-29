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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e4cc9d7d7d46157b7df202c6daffb31b90fa98c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="servicecredentials"></a><span data-ttu-id="ba541-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="ba541-102">ServiceCredentials</span></span>
<span data-ttu-id="ba541-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="ba541-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba541-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba541-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="ba541-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="ba541-105">Methods</span></span>  
 <span data-ttu-id="ba541-106">Die Klasse ServiceCredentials definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="ba541-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ba541-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ba541-107">Properties</span></span>  
 <span data-ttu-id="ba541-108">Die Klasse ServiceCredentials verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="ba541-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="ba541-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="ba541-109">ClientCertificate</span></span>  
 <span data-ttu-id="ba541-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="ba541-110">Data type: string</span></span>  
  
 <span data-ttu-id="ba541-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ba541-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ba541-112">Die Authentifizierungs- und Bereitstellungseinstellungen des Clientzertifikats für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="ba541-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="ba541-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="ba541-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="ba541-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="ba541-114">Data type: string</span></span>  
  
 <span data-ttu-id="ba541-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ba541-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ba541-116">Die Authentifizierungseinstellungen des aktuell ausgegebenen Tokens für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="ba541-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="ba541-117">Peer</span><span class="sxs-lookup"><span data-stu-id="ba541-117">Peer</span></span>  
 <span data-ttu-id="ba541-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="ba541-118">Data type: string</span></span>  
  
 <span data-ttu-id="ba541-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ba541-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ba541-120">Die aktuellen Authentifizierungs- und Bereitstellungseinstellungen für Anmeldeinformationen, die von Peertransportendpunkten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ba541-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="ba541-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="ba541-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="ba541-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="ba541-122">Data type: string</span></span>  
  
 <span data-ttu-id="ba541-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ba541-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ba541-124">Gibt die aktuellen sicheren Konversationseinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="ba541-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="ba541-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="ba541-125">ServiceCertificate</span></span>  
 <span data-ttu-id="ba541-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="ba541-126">Data type: string</span></span>  
  
 <span data-ttu-id="ba541-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ba541-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ba541-128">Das diesem Dienst zugeordnete Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="ba541-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="ba541-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="ba541-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="ba541-130">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="ba541-130">Data type: string</span></span>  
  
 <span data-ttu-id="ba541-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ba541-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ba541-132">Die Benutzernamen-/Kennworteinstellungen für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="ba541-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="ba541-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="ba541-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="ba541-134">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="ba541-134">Data type: string</span></span>  
  
 <span data-ttu-id="ba541-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ba541-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ba541-136">Die Windows-Authentifizierungseinstellungen für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="ba541-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba541-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ba541-137">Requirements</span></span>  
  
|<span data-ttu-id="ba541-138">MOF</span><span class="sxs-lookup"><span data-stu-id="ba541-138">MOF</span></span>|<span data-ttu-id="ba541-139">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ba541-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ba541-140">Namespace</span><span class="sxs-lookup"><span data-stu-id="ba541-140">Namespace</span></span>|<span data-ttu-id="ba541-141">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ba541-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ba541-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba541-142">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceCredentials>

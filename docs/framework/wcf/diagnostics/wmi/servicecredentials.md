---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: d9563bd3bfe067ad83bfa03e7c6375a9db933f14
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230927"
---
# <a name="servicecredentials"></a><span data-ttu-id="42f3d-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="42f3d-102">ServiceCredentials</span></span>
<span data-ttu-id="42f3d-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="42f3d-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42f3d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="42f3d-104">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="42f3d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="42f3d-105">Methods</span></span>  
 <span data-ttu-id="42f3d-106">Die Klasse ServiceCredentials definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="42f3d-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="42f3d-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="42f3d-107">Properties</span></span>  
 <span data-ttu-id="42f3d-108">Die Klasse ServiceCredentials verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="42f3d-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="42f3d-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="42f3d-109">ClientCertificate</span></span>  
 <span data-ttu-id="42f3d-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="42f3d-110">Data type: string</span></span>  
  
 <span data-ttu-id="42f3d-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="42f3d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="42f3d-112">Die Authentifizierungs- und Bereitstellungseinstellungen des Clientzertifikats für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="42f3d-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="42f3d-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="42f3d-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="42f3d-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="42f3d-114">Data type: string</span></span>  
  
 <span data-ttu-id="42f3d-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="42f3d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="42f3d-116">Die Authentifizierungseinstellungen des aktuell ausgegebenen Tokens für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="42f3d-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="42f3d-117">Peer</span><span class="sxs-lookup"><span data-stu-id="42f3d-117">Peer</span></span>  
 <span data-ttu-id="42f3d-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="42f3d-118">Data type: string</span></span>  
  
 <span data-ttu-id="42f3d-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="42f3d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="42f3d-120">Die aktuellen Authentifizierungs- und Bereitstellungseinstellungen für Anmeldeinformationen, die von Peertransportendpunkten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="42f3d-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="42f3d-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="42f3d-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="42f3d-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="42f3d-122">Data type: string</span></span>  
  
 <span data-ttu-id="42f3d-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="42f3d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="42f3d-124">Gibt die aktuellen sicheren Konversationseinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="42f3d-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="42f3d-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="42f3d-125">ServiceCertificate</span></span>  
 <span data-ttu-id="42f3d-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="42f3d-126">Data type: string</span></span>  
  
 <span data-ttu-id="42f3d-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="42f3d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="42f3d-128">Das diesem Dienst zugeordnete Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="42f3d-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="42f3d-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="42f3d-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="42f3d-130">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="42f3d-130">Data type: string</span></span>  
  
 <span data-ttu-id="42f3d-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="42f3d-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="42f3d-132">Die Benutzernamen-/Kennworteinstellungen für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="42f3d-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="42f3d-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="42f3d-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="42f3d-134">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="42f3d-134">Data type: string</span></span>  
  
 <span data-ttu-id="42f3d-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="42f3d-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="42f3d-136">Die Windows-Authentifizierungseinstellungen für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="42f3d-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42f3d-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="42f3d-137">Requirements</span></span>  
  
|<span data-ttu-id="42f3d-138">MOF</span><span class="sxs-lookup"><span data-stu-id="42f3d-138">MOF</span></span>|<span data-ttu-id="42f3d-139">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="42f3d-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="42f3d-140">Namespace</span><span class="sxs-lookup"><span data-stu-id="42f3d-140">Namespace</span></span>|<span data-ttu-id="42f3d-141">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="42f3d-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="42f3d-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42f3d-142">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceCredentials>

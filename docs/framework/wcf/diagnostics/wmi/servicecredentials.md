---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: d7e89acedc8fc1004b0198172e58813944df85f3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262306"
---
# <a name="servicecredentials"></a><span data-ttu-id="6f4e1-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="6f4e1-102">ServiceCredentials</span></span>

<span data-ttu-id="6f4e1-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="6f4e1-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f4e1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f4e1-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="6f4e1-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="6f4e1-105">Methods</span></span>  

 <span data-ttu-id="6f4e1-106">Die Klasse ServiceCredentials definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="6f4e1-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6f4e1-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6f4e1-107">Properties</span></span>  

 <span data-ttu-id="6f4e1-108">Die Klasse ServiceCredentials verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="6f4e1-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="6f4e1-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="6f4e1-109">ClientCertificate</span></span>  

 <span data-ttu-id="6f4e1-110">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="6f4e1-110">Data type: string</span></span>  
  
 <span data-ttu-id="6f4e1-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6f4e1-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6f4e1-112">Die Authentifizierungs- und Bereitstellungseinstellungen des Clientzertifikats für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="6f4e1-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="6f4e1-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="6f4e1-113">IssuedTokenAuthentication</span></span>  

 <span data-ttu-id="6f4e1-114">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="6f4e1-114">Data type: string</span></span>  
  
 <span data-ttu-id="6f4e1-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6f4e1-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6f4e1-116">Die Authentifizierungseinstellungen des aktuell ausgegebenen Tokens für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="6f4e1-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="6f4e1-117">Peer</span><span class="sxs-lookup"><span data-stu-id="6f4e1-117">Peer</span></span>  

 <span data-ttu-id="6f4e1-118">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="6f4e1-118">Data type: string</span></span>  
  
 <span data-ttu-id="6f4e1-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6f4e1-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6f4e1-120">Die aktuellen Authentifizierungs- und Bereitstellungseinstellungen für Anmeldeinformationen, die von Peertransportendpunkten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6f4e1-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="6f4e1-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="6f4e1-121">SecureConversationAuthentication</span></span>  

 <span data-ttu-id="6f4e1-122">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="6f4e1-122">Data type: string</span></span>  
  
 <span data-ttu-id="6f4e1-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6f4e1-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6f4e1-124">Gibt die aktuellen sicheren Konversationseinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="6f4e1-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="6f4e1-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="6f4e1-125">ServiceCertificate</span></span>  

 <span data-ttu-id="6f4e1-126">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="6f4e1-126">Data type: string</span></span>  
  
 <span data-ttu-id="6f4e1-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6f4e1-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6f4e1-128">Das diesem Dienst zugeordnete Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="6f4e1-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="6f4e1-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="6f4e1-129">UserNameAuthentication</span></span>  

 <span data-ttu-id="6f4e1-130">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="6f4e1-130">Data type: string</span></span>  
  
 <span data-ttu-id="6f4e1-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6f4e1-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6f4e1-132">Die Benutzernamen-/Kennworteinstellungen für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="6f4e1-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="6f4e1-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="6f4e1-133">WindowsAuthentication</span></span>  

 <span data-ttu-id="6f4e1-134">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="6f4e1-134">Data type: string</span></span>  
  
 <span data-ttu-id="6f4e1-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6f4e1-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6f4e1-136">Die Windows-Authentifizierungseinstellungen für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="6f4e1-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f4e1-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6f4e1-137">Requirements</span></span>  
  
|<span data-ttu-id="6f4e1-138">MOF</span><span class="sxs-lookup"><span data-stu-id="6f4e1-138">MOF</span></span>|<span data-ttu-id="6f4e1-139">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6f4e1-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6f4e1-140">Namespace</span><span class="sxs-lookup"><span data-stu-id="6f4e1-140">Namespace</span></span>|<span data-ttu-id="6f4e1-141">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6f4e1-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6f4e1-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f4e1-142">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceCredentials>

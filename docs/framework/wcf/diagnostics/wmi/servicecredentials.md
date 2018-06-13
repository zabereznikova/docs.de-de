---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: bf906e09ae71d26f8e95877f1c545c0724d57b9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485740"
---
# <a name="servicecredentials"></a><span data-ttu-id="d4111-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="d4111-102">ServiceCredentials</span></span>
<span data-ttu-id="d4111-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="d4111-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4111-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4111-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="d4111-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="d4111-105">Methods</span></span>  
 <span data-ttu-id="d4111-106">Die Klasse ServiceCredentials definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="d4111-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d4111-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d4111-107">Properties</span></span>  
 <span data-ttu-id="d4111-108">Die Klasse ServiceCredentials verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="d4111-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="d4111-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="d4111-109">ClientCertificate</span></span>  
 <span data-ttu-id="d4111-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="d4111-110">Data type: string</span></span>  
  
 <span data-ttu-id="d4111-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d4111-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4111-112">Die Authentifizierungs- und Bereitstellungseinstellungen des Clientzertifikats für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="d4111-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="d4111-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="d4111-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="d4111-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="d4111-114">Data type: string</span></span>  
  
 <span data-ttu-id="d4111-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d4111-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4111-116">Die Authentifizierungseinstellungen des aktuell ausgegebenen Tokens für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="d4111-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="d4111-117">Peer</span><span class="sxs-lookup"><span data-stu-id="d4111-117">Peer</span></span>  
 <span data-ttu-id="d4111-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="d4111-118">Data type: string</span></span>  
  
 <span data-ttu-id="d4111-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d4111-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4111-120">Die aktuellen Authentifizierungs- und Bereitstellungseinstellungen für Anmeldeinformationen, die von Peertransportendpunkten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d4111-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="d4111-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="d4111-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="d4111-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="d4111-122">Data type: string</span></span>  
  
 <span data-ttu-id="d4111-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d4111-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4111-124">Gibt die aktuellen sicheren Konversationseinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="d4111-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="d4111-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="d4111-125">ServiceCertificate</span></span>  
 <span data-ttu-id="d4111-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="d4111-126">Data type: string</span></span>  
  
 <span data-ttu-id="d4111-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d4111-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4111-128">Das diesem Dienst zugeordnete Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="d4111-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="d4111-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="d4111-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="d4111-130">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="d4111-130">Data type: string</span></span>  
  
 <span data-ttu-id="d4111-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d4111-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4111-132">Die Benutzernamen-/Kennworteinstellungen für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="d4111-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="d4111-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="d4111-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="d4111-134">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="d4111-134">Data type: string</span></span>  
  
 <span data-ttu-id="d4111-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="d4111-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d4111-136">Die Windows-Authentifizierungseinstellungen für diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="d4111-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4111-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d4111-137">Requirements</span></span>  
  
|<span data-ttu-id="d4111-138">MOF</span><span class="sxs-lookup"><span data-stu-id="d4111-138">MOF</span></span>|<span data-ttu-id="d4111-139">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d4111-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d4111-140">Namespace</span><span class="sxs-lookup"><span data-stu-id="d4111-140">Namespace</span></span>|<span data-ttu-id="d4111-141">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d4111-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4111-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4111-142">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceCredentials>

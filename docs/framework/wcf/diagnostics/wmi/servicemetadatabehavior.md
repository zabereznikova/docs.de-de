---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 19a04b6432f1ecc38a3b906b7e677175863134db
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188832"
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="19436-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="19436-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="19436-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="19436-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19436-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="19436-104">Syntax</span></span>  
  
```csharp
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="19436-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="19436-105">Methods</span></span>  
 <span data-ttu-id="19436-106">Die ServiceMetadataBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="19436-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="19436-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="19436-107">Properties</span></span>  
 <span data-ttu-id="19436-108">Die ServiceMetadataBehavior-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="19436-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="19436-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="19436-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="19436-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="19436-110">Data type: string</span></span>  
  
 <span data-ttu-id="19436-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19436-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19436-112">Legt den Speicherort fest, zu dem der Dienst Metadatenanforderungen umleitet.</span><span class="sxs-lookup"><span data-stu-id="19436-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="19436-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="19436-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="19436-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="19436-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="19436-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19436-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19436-116">Steuert, ob der Dienst seine WSDL unter der vom `HttpGetUrl`-Attribut gesteuerten Adresse veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="19436-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="19436-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="19436-117">HttpGetUrl</span></span>  
 <span data-ttu-id="19436-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="19436-118">Data type: string</span></span>  
  
 <span data-ttu-id="19436-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19436-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19436-120">Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="19436-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="19436-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="19436-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="19436-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="19436-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="19436-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19436-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19436-124">Steuert, ob der Dienst seine WSDL oder HTTPS unter der vom `HttpsGetUrl`-Attribut gesteuerten Adresse veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="19436-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="19436-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="19436-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="19436-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="19436-126">Data type: string</span></span>  
  
 <span data-ttu-id="19436-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="19436-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="19436-128">Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="19436-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19436-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="19436-129">Requirements</span></span>  
  
|<span data-ttu-id="19436-130">MOF</span><span class="sxs-lookup"><span data-stu-id="19436-130">MOF</span></span>|<span data-ttu-id="19436-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="19436-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="19436-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="19436-132">Namespace</span></span>|<span data-ttu-id="19436-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="19436-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="19436-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19436-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>

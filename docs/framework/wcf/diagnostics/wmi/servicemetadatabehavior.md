---
title: ServiceMetadataBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c05f6be9fc0507b7e2f1de4374e3b9bbe3e2a10e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="e3235-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="e3235-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="e3235-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="e3235-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3235-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3235-104">Syntax</span></span>  
  
```  
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e3235-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e3235-105">Methods</span></span>  
 <span data-ttu-id="e3235-106">Die ServiceMetadataBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="e3235-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e3235-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e3235-107">Properties</span></span>  
 <span data-ttu-id="e3235-108">Die ServiceMetadataBehavior-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="e3235-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="e3235-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="e3235-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="e3235-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e3235-110">Data type: string</span></span>  
  
 <span data-ttu-id="e3235-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e3235-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e3235-112">Legt den Speicherort fest, zu dem der Dienst Metadatenanforderungen umleitet.</span><span class="sxs-lookup"><span data-stu-id="e3235-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="e3235-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="e3235-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="e3235-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="e3235-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="e3235-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e3235-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e3235-116">Steuert, ob der Dienst seine WSDL unter der vom `HttpGetUrl`-Attribut gesteuerten Adresse veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="e3235-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="e3235-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="e3235-117">HttpGetUrl</span></span>  
 <span data-ttu-id="e3235-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e3235-118">Data type: string</span></span>  
  
 <span data-ttu-id="e3235-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e3235-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e3235-120">Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="e3235-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="e3235-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="e3235-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="e3235-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="e3235-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="e3235-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e3235-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e3235-124">Steuert, ob der Dienst seine WSDL oder HTTPS unter der vom `HttpsGetUrl`-Attribut gesteuerten Adresse veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="e3235-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="e3235-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="e3235-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="e3235-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="e3235-126">Data type: string</span></span>  
  
 <span data-ttu-id="e3235-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="e3235-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e3235-128">Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="e3235-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3235-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e3235-129">Requirements</span></span>  
  
|<span data-ttu-id="e3235-130">MOF</span><span class="sxs-lookup"><span data-stu-id="e3235-130">MOF</span></span>|<span data-ttu-id="e3235-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e3235-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e3235-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="e3235-132">Namespace</span></span>|<span data-ttu-id="e3235-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e3235-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3235-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3235-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>

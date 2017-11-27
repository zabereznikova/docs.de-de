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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9d10fdd9e33b078fa392e0ef359372913f9ba133
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="fcf14-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="fcf14-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="fcf14-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="fcf14-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcf14-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fcf14-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="fcf14-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="fcf14-105">Methods</span></span>  
 <span data-ttu-id="fcf14-106">Die ServiceMetadataBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="fcf14-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fcf14-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="fcf14-107">Properties</span></span>  
 <span data-ttu-id="fcf14-108">Die ServiceMetadataBehavior-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="fcf14-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="fcf14-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="fcf14-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="fcf14-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="fcf14-110">Data type: string</span></span>  
  
 <span data-ttu-id="fcf14-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fcf14-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fcf14-112">Legt den Speicherort fest, zu dem der Dienst Metadatenanforderungen umleitet.</span><span class="sxs-lookup"><span data-stu-id="fcf14-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="fcf14-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="fcf14-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="fcf14-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="fcf14-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="fcf14-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fcf14-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fcf14-116">Steuert, ob der Dienst seine WSDL unter der vom `HttpGetUrl`-Attribut gesteuerten Adresse veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="fcf14-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="fcf14-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="fcf14-117">HttpGetUrl</span></span>  
 <span data-ttu-id="fcf14-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="fcf14-118">Data type: string</span></span>  
  
 <span data-ttu-id="fcf14-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fcf14-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fcf14-120">Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="fcf14-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="fcf14-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="fcf14-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="fcf14-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="fcf14-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="fcf14-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fcf14-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fcf14-124">Steuert, ob der Dienst seine WSDL oder HTTPS unter der vom `HttpsGetUrl`-Attribut gesteuerten Adresse veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="fcf14-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="fcf14-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="fcf14-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="fcf14-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="fcf14-126">Data type: string</span></span>  
  
 <span data-ttu-id="fcf14-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="fcf14-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fcf14-128">Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="fcf14-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcf14-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fcf14-129">Requirements</span></span>  
  
|<span data-ttu-id="fcf14-130">MOF</span><span class="sxs-lookup"><span data-stu-id="fcf14-130">MOF</span></span>|<span data-ttu-id="fcf14-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fcf14-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fcf14-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="fcf14-132">Namespace</span></span>|<span data-ttu-id="fcf14-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fcf14-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fcf14-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcf14-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>

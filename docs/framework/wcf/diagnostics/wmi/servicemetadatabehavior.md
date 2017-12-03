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
ms.openlocfilehash: f17b31e1dfe9ba60b2042a85a6d673d986fe0a33
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="f5da9-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="f5da9-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="f5da9-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="f5da9-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5da9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5da9-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="f5da9-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f5da9-105">Methods</span></span>  
 <span data-ttu-id="f5da9-106">Die ServiceMetadataBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="f5da9-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f5da9-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f5da9-107">Properties</span></span>  
 <span data-ttu-id="f5da9-108">Die ServiceMetadataBehavior-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f5da9-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="f5da9-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="f5da9-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="f5da9-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f5da9-110">Data type: string</span></span>  
  
 <span data-ttu-id="f5da9-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f5da9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f5da9-112">Legt den Speicherort fest, zu dem der Dienst Metadatenanforderungen umleitet.</span><span class="sxs-lookup"><span data-stu-id="f5da9-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="f5da9-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="f5da9-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="f5da9-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="f5da9-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="f5da9-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f5da9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f5da9-116">Steuert, ob der Dienst seine WSDL unter der vom `HttpGetUrl`-Attribut gesteuerten Adresse veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="f5da9-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="f5da9-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="f5da9-117">HttpGetUrl</span></span>  
 <span data-ttu-id="f5da9-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f5da9-118">Data type: string</span></span>  
  
 <span data-ttu-id="f5da9-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f5da9-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f5da9-120">Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="f5da9-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="f5da9-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="f5da9-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="f5da9-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="f5da9-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="f5da9-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f5da9-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f5da9-124">Steuert, ob der Dienst seine WSDL oder HTTPS unter der vom `HttpsGetUrl`-Attribut gesteuerten Adresse veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="f5da9-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="f5da9-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="f5da9-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="f5da9-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f5da9-126">Data type: string</span></span>  
  
 <span data-ttu-id="f5da9-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f5da9-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f5da9-128">Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="f5da9-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5da9-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f5da9-129">Requirements</span></span>  
  
|<span data-ttu-id="f5da9-130">MOF</span><span class="sxs-lookup"><span data-stu-id="f5da9-130">MOF</span></span>|<span data-ttu-id="f5da9-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f5da9-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f5da9-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="f5da9-132">Namespace</span></span>|<span data-ttu-id="f5da9-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f5da9-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5da9-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5da9-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>

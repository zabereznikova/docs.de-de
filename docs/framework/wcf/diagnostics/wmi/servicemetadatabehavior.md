---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 921a880dad0d77558a70dff8a09f75c25a3cbb8a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262280"
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="45f74-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="45f74-102">ServiceMetadataBehavior</span></span>

<span data-ttu-id="45f74-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="45f74-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45f74-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45f74-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="45f74-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="45f74-105">Methods</span></span>  

 <span data-ttu-id="45f74-106">Die ServiceMetadataBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="45f74-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="45f74-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="45f74-107">Properties</span></span>  

 <span data-ttu-id="45f74-108">Die ServiceMetadataBehavior-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="45f74-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="45f74-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="45f74-109">ExternalMetadataLocation</span></span>  

 <span data-ttu-id="45f74-110">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="45f74-110">Data type: string</span></span>  
  
 <span data-ttu-id="45f74-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="45f74-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="45f74-112">Legt den Speicherort fest, zu dem der Dienst Metadatenanforderungen umleitet.</span><span class="sxs-lookup"><span data-stu-id="45f74-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="45f74-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="45f74-113">HttpGetEnabled</span></span>  

 <span data-ttu-id="45f74-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="45f74-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="45f74-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="45f74-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="45f74-116">Steuert, ob der Dienst seine WSDL unter der vom `HttpGetUrl`-Attribut gesteuerten Adresse veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="45f74-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="45f74-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="45f74-117">HttpGetUrl</span></span>  

 <span data-ttu-id="45f74-118">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="45f74-118">Data type: string</span></span>  
  
 <span data-ttu-id="45f74-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="45f74-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="45f74-120">Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="45f74-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="45f74-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="45f74-121">HttpsGetEnabled</span></span>  

 <span data-ttu-id="45f74-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="45f74-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="45f74-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="45f74-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="45f74-124">Steuert, ob der Dienst seine WSDL oder HTTPS unter der vom `HttpsGetUrl`-Attribut gesteuerten Adresse veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="45f74-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="45f74-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="45f74-125">HttpsGetUrl</span></span>  

 <span data-ttu-id="45f74-126">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="45f74-126">Data type: string</span></span>  
  
 <span data-ttu-id="45f74-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="45f74-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="45f74-128">Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="45f74-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45f74-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="45f74-129">Requirements</span></span>  
  
|<span data-ttu-id="45f74-130">MOF</span><span class="sxs-lookup"><span data-stu-id="45f74-130">MOF</span></span>|<span data-ttu-id="45f74-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="45f74-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="45f74-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="45f74-132">Namespace</span></span>|<span data-ttu-id="45f74-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="45f74-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="45f74-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45f74-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>

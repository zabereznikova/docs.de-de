---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 1d99af064205447c2f11f6f19258551c1e88d386
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59976132"
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="da53b-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="da53b-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="da53b-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="da53b-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da53b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="da53b-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="da53b-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="da53b-105">Methods</span></span>  
 <span data-ttu-id="da53b-106">Die ServiceMetadataBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="da53b-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="da53b-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="da53b-107">Properties</span></span>  
 <span data-ttu-id="da53b-108">Die ServiceMetadataBehavior-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="da53b-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="da53b-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="da53b-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="da53b-110">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="da53b-110">Data type: string</span></span>  
  
 <span data-ttu-id="da53b-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="da53b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="da53b-112">Legt den Speicherort fest, zu dem der Dienst Metadatenanforderungen umleitet.</span><span class="sxs-lookup"><span data-stu-id="da53b-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="da53b-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="da53b-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="da53b-114">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="da53b-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="da53b-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="da53b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="da53b-116">Steuert, ob der Dienst seine WSDL unter der vom `HttpGetUrl`-Attribut gesteuerten Adresse veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="da53b-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="da53b-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="da53b-117">HttpGetUrl</span></span>  
 <span data-ttu-id="da53b-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="da53b-118">Data type: string</span></span>  
  
 <span data-ttu-id="da53b-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="da53b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="da53b-120">Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="da53b-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="da53b-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="da53b-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="da53b-122">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="da53b-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="da53b-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="da53b-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="da53b-124">Steuert, ob der Dienst seine WSDL oder HTTPS unter der vom `HttpsGetUrl`-Attribut gesteuerten Adresse veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="da53b-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="da53b-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="da53b-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="da53b-126">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="da53b-126">Data type: string</span></span>  
  
 <span data-ttu-id="da53b-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="da53b-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="da53b-128">Legt den Speicherort fest, an dem die Dienst-WSDL für den Abruf mithilfe von HTTPS veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="da53b-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da53b-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="da53b-129">Requirements</span></span>  
  
|<span data-ttu-id="da53b-130">MOF</span><span class="sxs-lookup"><span data-stu-id="da53b-130">MOF</span></span>|<span data-ttu-id="da53b-131">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="da53b-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="da53b-132">Namespace</span><span class="sxs-lookup"><span data-stu-id="da53b-132">Namespace</span></span>|<span data-ttu-id="da53b-133">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="da53b-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="da53b-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da53b-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>

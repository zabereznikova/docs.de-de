---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 6e20556541b1aa48e7dfc6a8cde97e1bc477457e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273944"
---
# <a name="servicetoendpointassociation"></a><span data-ttu-id="ae29c-102">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="ae29c-102">ServiceToEndpointAssociation</span></span>

<span data-ttu-id="ae29c-103">Ordnet einem Endpunkt einen Dienst zu.</span><span class="sxs-lookup"><span data-stu-id="ae29c-103">Maps a service to an endpoint.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae29c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae29c-104">Syntax</span></span>  
  
```csharp
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ae29c-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="ae29c-105">Methods</span></span>  

 <span data-ttu-id="ae29c-106">Die ServiceToEndpointAssociation-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="ae29c-106">The ServiceToEndpointAssociation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ae29c-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ae29c-107">Properties</span></span>  

 <span data-ttu-id="ae29c-108">Die ServiceToEndpointAssociation-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="ae29c-108">The ServiceToEndpointAssociation class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="ae29c-109">ref</span><span class="sxs-lookup"><span data-stu-id="ae29c-109">ref</span></span>  

 <span data-ttu-id="ae29c-110">Datentyp: Dienst</span><span class="sxs-lookup"><span data-stu-id="ae29c-110">Data type: Service</span></span>  
  
 <span data-ttu-id="ae29c-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ae29c-111">Access type: Read-only</span></span>  
<span data-ttu-id="ae29c-112">Qualifizierer: Schlüssel</span><span class="sxs-lookup"><span data-stu-id="ae29c-112">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="ae29c-113">Der dem Endpunkt zugeordnete Dienst.</span><span class="sxs-lookup"><span data-stu-id="ae29c-113">The service associated with the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="ae29c-114">ref</span><span class="sxs-lookup"><span data-stu-id="ae29c-114">ref</span></span>  

 <span data-ttu-id="ae29c-115">Datentyp: Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ae29c-115">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="ae29c-116">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ae29c-116">Access type: Read-only</span></span>  
<span data-ttu-id="ae29c-117">Qualifizierer: Schlüssel</span><span class="sxs-lookup"><span data-stu-id="ae29c-117">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="ae29c-118">Der dem Dienst zugeordnete Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="ae29c-118">The endpoint associated with the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae29c-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ae29c-119">Requirements</span></span>  
  
|<span data-ttu-id="ae29c-120">MOF</span><span class="sxs-lookup"><span data-stu-id="ae29c-120">MOF</span></span>|<span data-ttu-id="ae29c-121">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ae29c-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ae29c-122">Namespace</span><span class="sxs-lookup"><span data-stu-id="ae29c-122">Namespace</span></span>|<span data-ttu-id="ae29c-123">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ae29c-123">Defined in root\ServiceModel</span></span>|

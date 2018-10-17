---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 3d23a3ee10c47e04ea7bdba202ea5063c0d84fac
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "49372178"
---
# <a name="servicetoendpointassociation"></a><span data-ttu-id="403cb-102">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="403cb-102">ServiceToEndpointAssociation</span></span>
<span data-ttu-id="403cb-103">Ordnet einem Endpunkt einen Dienst zu.</span><span class="sxs-lookup"><span data-stu-id="403cb-103">Maps a service to an endpoint.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="403cb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="403cb-104">Syntax</span></span>  
  
```csharp
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="403cb-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="403cb-105">Methods</span></span>  
 <span data-ttu-id="403cb-106">Die ServiceToEndpointAssociation-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="403cb-106">The ServiceToEndpointAssociation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="403cb-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="403cb-107">Properties</span></span>  
 <span data-ttu-id="403cb-108">Die ServiceToEndpointAssociation-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="403cb-108">The ServiceToEndpointAssociation class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="403cb-109">ref</span><span class="sxs-lookup"><span data-stu-id="403cb-109">ref</span></span>  
 <span data-ttu-id="403cb-110">Datentyp: Dienst</span><span class="sxs-lookup"><span data-stu-id="403cb-110">Data type: Service</span></span>  
  
 <span data-ttu-id="403cb-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="403cb-111">Access type: Read-only</span></span>  
<span data-ttu-id="403cb-112">Qualifizierer: Schlüssel</span><span class="sxs-lookup"><span data-stu-id="403cb-112">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="403cb-113">Der dem Endpunkt zugeordnete Dienst.</span><span class="sxs-lookup"><span data-stu-id="403cb-113">The service associated with the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="403cb-114">ref</span><span class="sxs-lookup"><span data-stu-id="403cb-114">ref</span></span>  
 <span data-ttu-id="403cb-115">Datentyp: Endpunkt</span><span class="sxs-lookup"><span data-stu-id="403cb-115">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="403cb-116">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="403cb-116">Access type: Read-only</span></span>  
<span data-ttu-id="403cb-117">Qualifizierer: Schlüssel</span><span class="sxs-lookup"><span data-stu-id="403cb-117">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="403cb-118">Der dem Dienst zugeordnete Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="403cb-118">The endpoint associated with the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="403cb-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="403cb-119">Requirements</span></span>  
  
|<span data-ttu-id="403cb-120">MOF</span><span class="sxs-lookup"><span data-stu-id="403cb-120">MOF</span></span>|<span data-ttu-id="403cb-121">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="403cb-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="403cb-122">Namespace</span><span class="sxs-lookup"><span data-stu-id="403cb-122">Namespace</span></span>|<span data-ttu-id="403cb-123">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="403cb-123">Defined in root\ServiceModel</span></span>|

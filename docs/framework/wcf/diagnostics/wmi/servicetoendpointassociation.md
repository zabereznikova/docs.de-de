---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 3d23a3ee10c47e04ea7bdba202ea5063c0d84fac
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452708"
---
# <a name="servicetoendpointassociation"></a><span data-ttu-id="377f6-102">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="377f6-102">ServiceToEndpointAssociation</span></span>
<span data-ttu-id="377f6-103">Ordnet einem Endpunkt einen Dienst zu.</span><span class="sxs-lookup"><span data-stu-id="377f6-103">Maps a service to an endpoint.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="377f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="377f6-104">Syntax</span></span>  
  
```csharp
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="377f6-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="377f6-105">Methods</span></span>  
 <span data-ttu-id="377f6-106">Die ServiceToEndpointAssociation-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="377f6-106">The ServiceToEndpointAssociation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="377f6-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="377f6-107">Properties</span></span>  
 <span data-ttu-id="377f6-108">Die ServiceToEndpointAssociation-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="377f6-108">The ServiceToEndpointAssociation class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="377f6-109">ref</span><span class="sxs-lookup"><span data-stu-id="377f6-109">ref</span></span>  
 <span data-ttu-id="377f6-110">Datentyp: Dienst</span><span class="sxs-lookup"><span data-stu-id="377f6-110">Data type: Service</span></span>  
  
 <span data-ttu-id="377f6-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="377f6-111">Access type: Read-only</span></span>  
<span data-ttu-id="377f6-112">Qualifizierer: Schlüssel</span><span class="sxs-lookup"><span data-stu-id="377f6-112">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="377f6-113">Der dem Endpunkt zugeordnete Dienst.</span><span class="sxs-lookup"><span data-stu-id="377f6-113">The service associated with the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="377f6-114">ref</span><span class="sxs-lookup"><span data-stu-id="377f6-114">ref</span></span>  
 <span data-ttu-id="377f6-115">Datentyp: Endpunkt</span><span class="sxs-lookup"><span data-stu-id="377f6-115">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="377f6-116">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="377f6-116">Access type: Read-only</span></span>  
<span data-ttu-id="377f6-117">Qualifizierer: Schlüssel</span><span class="sxs-lookup"><span data-stu-id="377f6-117">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="377f6-118">Der dem Dienst zugeordnete Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="377f6-118">The endpoint associated with the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="377f6-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="377f6-119">Requirements</span></span>  
  
|<span data-ttu-id="377f6-120">MOF</span><span class="sxs-lookup"><span data-stu-id="377f6-120">MOF</span></span>|<span data-ttu-id="377f6-121">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="377f6-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="377f6-122">Namespace</span><span class="sxs-lookup"><span data-stu-id="377f6-122">Namespace</span></span>|<span data-ttu-id="377f6-123">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="377f6-123">Defined in root\ServiceModel</span></span>|

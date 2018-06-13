---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: b1e5b87b053e947432cba9f6e716f7d1ea8f013f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33484328"
---
# <a name="servicetoendpointassociation"></a><span data-ttu-id="0ae04-102">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="0ae04-102">ServiceToEndpointAssociation</span></span>
<span data-ttu-id="0ae04-103">Ordnet einem Endpunkt einen Dienst zu.</span><span class="sxs-lookup"><span data-stu-id="0ae04-103">Maps a service to an endpoint.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ae04-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ae04-104">Syntax</span></span>  
  
```  
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="0ae04-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="0ae04-105">Methods</span></span>  
 <span data-ttu-id="0ae04-106">Die ServiceToEndpointAssociation-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="0ae04-106">The ServiceToEndpointAssociation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0ae04-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0ae04-107">Properties</span></span>  
 <span data-ttu-id="0ae04-108">Die ServiceToEndpointAssociation-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="0ae04-108">The ServiceToEndpointAssociation class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="0ae04-109">ref</span><span class="sxs-lookup"><span data-stu-id="0ae04-109">ref</span></span>  
 <span data-ttu-id="0ae04-110">Datentyp: Dienst</span><span class="sxs-lookup"><span data-stu-id="0ae04-110">Data type: Service</span></span>  
  
 <span data-ttu-id="0ae04-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0ae04-111">Access type: Read-only</span></span>  
<span data-ttu-id="0ae04-112">Qualifizierer: Schlüssel</span><span class="sxs-lookup"><span data-stu-id="0ae04-112">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="0ae04-113">Der dem Endpunkt zugeordnete Dienst.</span><span class="sxs-lookup"><span data-stu-id="0ae04-113">The service associated with the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="0ae04-114">ref</span><span class="sxs-lookup"><span data-stu-id="0ae04-114">ref</span></span>  
 <span data-ttu-id="0ae04-115">Datentyp: Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0ae04-115">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="0ae04-116">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="0ae04-116">Access type: Read-only</span></span>  
<span data-ttu-id="0ae04-117">Qualifizierer: Schlüssel</span><span class="sxs-lookup"><span data-stu-id="0ae04-117">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="0ae04-118">Der dem Dienst zugeordnete Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="0ae04-118">The endpoint associated with the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ae04-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0ae04-119">Requirements</span></span>  
  
|<span data-ttu-id="0ae04-120">MOF</span><span class="sxs-lookup"><span data-stu-id="0ae04-120">MOF</span></span>|<span data-ttu-id="0ae04-121">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="0ae04-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0ae04-122">Namespace</span><span class="sxs-lookup"><span data-stu-id="0ae04-122">Namespace</span></span>|<span data-ttu-id="0ae04-123">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0ae04-123">Defined in root\ServiceModel</span></span>|

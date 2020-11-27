---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: f1978881517fe5010ccc0f5192b21bd6688f063a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291114"
---
# <a name="activitytransfer"></a><span data-ttu-id="80f70-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="80f70-102">ActivityTransfer</span></span>

<span data-ttu-id="80f70-103">Aktivitätsübertragungsereignis</span><span class="sxs-lookup"><span data-stu-id="80f70-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80f70-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="80f70-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="80f70-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="80f70-105">Methods</span></span>  

 <span data-ttu-id="80f70-106">Von der ActivityTransfer-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="80f70-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="80f70-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="80f70-107">Properties</span></span>  

 <span data-ttu-id="80f70-108">Die ActivityTransfer-Klasse besitzt folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="80f70-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="80f70-109">Aktivitäts-ID</span><span class="sxs-lookup"><span data-stu-id="80f70-109">ActivityID</span></span>  
  
- <span data-ttu-id="80f70-110">Datentyp: object</span><span class="sxs-lookup"><span data-stu-id="80f70-110">Data type: object</span></span>  
    <span data-ttu-id="80f70-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="80f70-111">Access type: Read-only</span></span>  
  
- <span data-ttu-id="80f70-112">Aktivitäts-ID</span><span class="sxs-lookup"><span data-stu-id="80f70-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="80f70-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="80f70-113">RelatedActivityID</span></span>  
  
- <span data-ttu-id="80f70-114">Datentyp: object</span><span class="sxs-lookup"><span data-stu-id="80f70-114">Data type: object</span></span>  
    <span data-ttu-id="80f70-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="80f70-115">Access type: Read-only</span></span>  
  
- <span data-ttu-id="80f70-116">Verwandte Aktivitäts-ID</span><span class="sxs-lookup"><span data-stu-id="80f70-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80f70-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="80f70-117">Requirements</span></span>  
  
|<span data-ttu-id="80f70-118">MOF</span><span class="sxs-lookup"><span data-stu-id="80f70-118">MOF</span></span>|<span data-ttu-id="80f70-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="80f70-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="80f70-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="80f70-120">Namespace</span></span>|<span data-ttu-id="80f70-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="80f70-121">Defined in root\ServiceModel.</span></span>|

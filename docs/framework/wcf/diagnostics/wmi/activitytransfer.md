---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 6237d65d6964a4ebca34af895158c83239641593
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662821"
---
# <a name="activitytransfer"></a><span data-ttu-id="a4ec1-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="a4ec1-102">ActivityTransfer</span></span>
<span data-ttu-id="a4ec1-103">Aktivitätsübertragungsereignis</span><span class="sxs-lookup"><span data-stu-id="a4ec1-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4ec1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4ec1-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a4ec1-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a4ec1-105">Methods</span></span>  
 <span data-ttu-id="a4ec1-106">Von der ActivityTransfer-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="a4ec1-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a4ec1-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a4ec1-107">Properties</span></span>  
 <span data-ttu-id="a4ec1-108">Die ActivityTransfer-Klasse besitzt folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="a4ec1-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="a4ec1-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="a4ec1-109">ActivityID</span></span>  
  
- <span data-ttu-id="a4ec1-110">Datentyp: object</span><span class="sxs-lookup"><span data-stu-id="a4ec1-110">Data type: object</span></span>  
    <span data-ttu-id="a4ec1-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a4ec1-111">Access type: Read-only</span></span>  
  
- <span data-ttu-id="a4ec1-112">Aktivitäts-ID</span><span class="sxs-lookup"><span data-stu-id="a4ec1-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="a4ec1-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="a4ec1-113">RelatedActivityID</span></span>  
  
- <span data-ttu-id="a4ec1-114">Datentyp: object</span><span class="sxs-lookup"><span data-stu-id="a4ec1-114">Data type: object</span></span>  
    <span data-ttu-id="a4ec1-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="a4ec1-115">Access type: Read-only</span></span>  
  
- <span data-ttu-id="a4ec1-116">Verwandte Aktivitäts-ID</span><span class="sxs-lookup"><span data-stu-id="a4ec1-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4ec1-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a4ec1-117">Requirements</span></span>  
  
|<span data-ttu-id="a4ec1-118">MOF</span><span class="sxs-lookup"><span data-stu-id="a4ec1-118">MOF</span></span>|<span data-ttu-id="a4ec1-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a4ec1-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a4ec1-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="a4ec1-120">Namespace</span></span>|<span data-ttu-id="a4ec1-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a4ec1-121">Defined in root\ServiceModel.</span></span>|

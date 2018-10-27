---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 936e870c1ec991e2e33acf8a08ccc93975989679
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50034421"
---
# <a name="activitytransfer"></a><span data-ttu-id="2fd98-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="2fd98-102">ActivityTransfer</span></span>
<span data-ttu-id="2fd98-103">Aktivitätsübertragungsereignis</span><span class="sxs-lookup"><span data-stu-id="2fd98-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fd98-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2fd98-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2fd98-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="2fd98-105">Methods</span></span>  
 <span data-ttu-id="2fd98-106">Von der ActivityTransfer-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="2fd98-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2fd98-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2fd98-107">Properties</span></span>  
 <span data-ttu-id="2fd98-108">Die ActivityTransfer-Klasse besitzt folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="2fd98-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="2fd98-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="2fd98-109">ActivityID</span></span>  
  
-   <span data-ttu-id="2fd98-110">Datentyp: object</span><span class="sxs-lookup"><span data-stu-id="2fd98-110">Data type: object</span></span>  
    <span data-ttu-id="2fd98-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2fd98-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="2fd98-112">Aktivitäts-ID</span><span class="sxs-lookup"><span data-stu-id="2fd98-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="2fd98-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="2fd98-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="2fd98-114">Datentyp: object</span><span class="sxs-lookup"><span data-stu-id="2fd98-114">Data type: object</span></span>  
    <span data-ttu-id="2fd98-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="2fd98-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="2fd98-116">Verwandte Aktivitäts-ID</span><span class="sxs-lookup"><span data-stu-id="2fd98-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fd98-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2fd98-117">Requirements</span></span>  
  
|<span data-ttu-id="2fd98-118">MOF</span><span class="sxs-lookup"><span data-stu-id="2fd98-118">MOF</span></span>|<span data-ttu-id="2fd98-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="2fd98-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2fd98-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="2fd98-120">Namespace</span></span>|<span data-ttu-id="2fd98-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2fd98-121">Defined in root\ServiceModel.</span></span>|

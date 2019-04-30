---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 936e870c1ec991e2e33acf8a08ccc93975989679
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61964293"
---
# <a name="activitytransfer"></a><span data-ttu-id="8a840-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="8a840-102">ActivityTransfer</span></span>
<span data-ttu-id="8a840-103">Aktivitätsübertragungsereignis</span><span class="sxs-lookup"><span data-stu-id="8a840-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a840-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a840-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8a840-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="8a840-105">Methods</span></span>  
 <span data-ttu-id="8a840-106">Von der ActivityTransfer-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="8a840-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8a840-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8a840-107">Properties</span></span>  
 <span data-ttu-id="8a840-108">Die ActivityTransfer-Klasse besitzt folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="8a840-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="8a840-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="8a840-109">ActivityID</span></span>  
  
- <span data-ttu-id="8a840-110">Datentyp: object</span><span class="sxs-lookup"><span data-stu-id="8a840-110">Data type: object</span></span>  
    <span data-ttu-id="8a840-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="8a840-111">Access type: Read-only</span></span>  
  
- <span data-ttu-id="8a840-112">Aktivitäts-ID</span><span class="sxs-lookup"><span data-stu-id="8a840-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="8a840-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="8a840-113">RelatedActivityID</span></span>  
  
- <span data-ttu-id="8a840-114">Datentyp: object</span><span class="sxs-lookup"><span data-stu-id="8a840-114">Data type: object</span></span>  
    <span data-ttu-id="8a840-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="8a840-115">Access type: Read-only</span></span>  
  
- <span data-ttu-id="8a840-116">Verwandte Aktivitäts-ID</span><span class="sxs-lookup"><span data-stu-id="8a840-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a840-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8a840-117">Requirements</span></span>  
  
|<span data-ttu-id="8a840-118">MOF</span><span class="sxs-lookup"><span data-stu-id="8a840-118">MOF</span></span>|<span data-ttu-id="8a840-119">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="8a840-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8a840-120">Namespace</span><span class="sxs-lookup"><span data-stu-id="8a840-120">Namespace</span></span>|<span data-ttu-id="8a840-121">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8a840-121">Defined in root\ServiceModel.</span></span>|

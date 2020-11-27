---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 0409277821a7cca3f97fcec1bb383aba9583a1f6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262215"
---
# <a name="wsat_tracerecord"></a><span data-ttu-id="6fa91-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="6fa91-102">WSAT_TraceRecord</span></span>

<span data-ttu-id="6fa91-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="6fa91-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fa91-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6fa91-104">Syntax</span></span>  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6fa91-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="6fa91-105">Methods</span></span>  

 <span data-ttu-id="6fa91-106">Die Klasse WSAT_TraceRecord definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="6fa91-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6fa91-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6fa91-107">Properties</span></span>  

 <span data-ttu-id="6fa91-108">Die Klasse WSAT_TraceRecord weist die folgenden Eigenschaften auf:</span><span class="sxs-lookup"><span data-stu-id="6fa91-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="6fa91-109">Aktivitäts-ID</span><span class="sxs-lookup"><span data-stu-id="6fa91-109">ActivityID</span></span>  

 <span data-ttu-id="6fa91-110">Datentyp: object</span><span class="sxs-lookup"><span data-stu-id="6fa91-110">Data type: object</span></span>  
<span data-ttu-id="6fa91-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6fa91-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6fa91-112">Die Aktivitäts-ID des Ablaufverfolgungsdatensatzes.</span><span class="sxs-lookup"><span data-stu-id="6fa91-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="6fa91-113">EventId</span><span class="sxs-lookup"><span data-stu-id="6fa91-113">EventID</span></span>  

 <span data-ttu-id="6fa91-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="6fa91-114">Data type: sint32</span></span>  
<span data-ttu-id="6fa91-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6fa91-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6fa91-116">Die Ziel-ID des Ablaufverfolgungsdatensatzes.</span><span class="sxs-lookup"><span data-stu-id="6fa91-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="6fa91-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="6fa91-117">TraceRecord</span></span>  

 <span data-ttu-id="6fa91-118">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="6fa91-118">Data type: string</span></span>  
<span data-ttu-id="6fa91-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="6fa91-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6fa91-120">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="6fa91-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fa91-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6fa91-121">Requirements</span></span>  
  
|<span data-ttu-id="6fa91-122">MOF</span><span class="sxs-lookup"><span data-stu-id="6fa91-122">MOF</span></span>|<span data-ttu-id="6fa91-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6fa91-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6fa91-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="6fa91-124">Namespace</span></span>|<span data-ttu-id="6fa91-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6fa91-125">Defined in root\ServiceModel</span></span>|

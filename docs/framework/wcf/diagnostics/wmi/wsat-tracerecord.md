---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 907e764cf032e595c7aba455fd4808a640f68016
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50046278"
---
# <a name="wsattracerecord"></a><span data-ttu-id="9ea61-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="9ea61-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="9ea61-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="9ea61-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ea61-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ea61-104">Syntax</span></span>  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9ea61-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="9ea61-105">Methods</span></span>  
 <span data-ttu-id="9ea61-106">Die Klasse WSAT_TraceRecord definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="9ea61-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9ea61-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9ea61-107">Properties</span></span>  
 <span data-ttu-id="9ea61-108">Die Klasse WSAT_TraceRecord weist die folgenden Eigenschaften auf:</span><span class="sxs-lookup"><span data-stu-id="9ea61-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="9ea61-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="9ea61-109">ActivityID</span></span>  
 <span data-ttu-id="9ea61-110">Datentyp: object</span><span class="sxs-lookup"><span data-stu-id="9ea61-110">Data type: object</span></span>  
<span data-ttu-id="9ea61-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9ea61-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ea61-112">Die Aktivitäts-ID des Ablaufverfolgungsdatensatzes.</span><span class="sxs-lookup"><span data-stu-id="9ea61-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="9ea61-113">EventID</span><span class="sxs-lookup"><span data-stu-id="9ea61-113">EventID</span></span>  
 <span data-ttu-id="9ea61-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="9ea61-114">Data type: sint32</span></span>  
<span data-ttu-id="9ea61-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9ea61-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ea61-116">Die Ziel-ID des Ablaufverfolgungsdatensatzes.</span><span class="sxs-lookup"><span data-stu-id="9ea61-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="9ea61-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="9ea61-117">TraceRecord</span></span>  
 <span data-ttu-id="9ea61-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="9ea61-118">Data type: string</span></span>  
<span data-ttu-id="9ea61-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9ea61-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9ea61-120">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="9ea61-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ea61-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9ea61-121">Requirements</span></span>  
  
|<span data-ttu-id="9ea61-122">MOF</span><span class="sxs-lookup"><span data-stu-id="9ea61-122">MOF</span></span>|<span data-ttu-id="9ea61-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9ea61-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9ea61-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="9ea61-124">Namespace</span></span>|<span data-ttu-id="9ea61-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9ea61-125">Defined in root\ServiceModel</span></span>|

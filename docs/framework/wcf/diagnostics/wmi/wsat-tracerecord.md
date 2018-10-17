---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 907e764cf032e595c7aba455fd4808a640f68016
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "49373995"
---
# <a name="wsattracerecord"></a><span data-ttu-id="53210-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="53210-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="53210-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="53210-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53210-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="53210-104">Syntax</span></span>  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="53210-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="53210-105">Methods</span></span>  
 <span data-ttu-id="53210-106">Die Klasse WSAT_TraceRecord definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="53210-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="53210-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="53210-107">Properties</span></span>  
 <span data-ttu-id="53210-108">Die Klasse WSAT_TraceRecord weist die folgenden Eigenschaften auf:</span><span class="sxs-lookup"><span data-stu-id="53210-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="53210-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="53210-109">ActivityID</span></span>  
 <span data-ttu-id="53210-110">Datentyp: object</span><span class="sxs-lookup"><span data-stu-id="53210-110">Data type: object</span></span>  
<span data-ttu-id="53210-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="53210-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53210-112">Die Aktivitäts-ID des Ablaufverfolgungsdatensatzes.</span><span class="sxs-lookup"><span data-stu-id="53210-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="53210-113">EventID</span><span class="sxs-lookup"><span data-stu-id="53210-113">EventID</span></span>  
 <span data-ttu-id="53210-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="53210-114">Data type: sint32</span></span>  
<span data-ttu-id="53210-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="53210-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53210-116">Die Ziel-ID des Ablaufverfolgungsdatensatzes.</span><span class="sxs-lookup"><span data-stu-id="53210-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="53210-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="53210-117">TraceRecord</span></span>  
 <span data-ttu-id="53210-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="53210-118">Data type: string</span></span>  
<span data-ttu-id="53210-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="53210-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="53210-120">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="53210-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53210-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="53210-121">Requirements</span></span>  
  
|<span data-ttu-id="53210-122">MOF</span><span class="sxs-lookup"><span data-stu-id="53210-122">MOF</span></span>|<span data-ttu-id="53210-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="53210-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="53210-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="53210-124">Namespace</span></span>|<span data-ttu-id="53210-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="53210-125">Defined in root\ServiceModel</span></span>|

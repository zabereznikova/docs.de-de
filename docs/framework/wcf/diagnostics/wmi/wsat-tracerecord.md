---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 907e764cf032e595c7aba455fd4808a640f68016
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923408"
---
# <a name="wsattracerecord"></a><span data-ttu-id="7b027-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="7b027-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="7b027-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="7b027-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b027-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b027-104">Syntax</span></span>  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7b027-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="7b027-105">Methods</span></span>  
 <span data-ttu-id="7b027-106">Die Klasse WSAT_TraceRecord definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="7b027-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7b027-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7b027-107">Properties</span></span>  
 <span data-ttu-id="7b027-108">Die Klasse WSAT_TraceRecord weist die folgenden Eigenschaften auf:</span><span class="sxs-lookup"><span data-stu-id="7b027-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="7b027-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="7b027-109">ActivityID</span></span>  
 <span data-ttu-id="7b027-110">Datentyp: object</span><span class="sxs-lookup"><span data-stu-id="7b027-110">Data type: object</span></span>  
<span data-ttu-id="7b027-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7b027-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b027-112">Die Aktivitäts-ID des Ablaufverfolgungsdatensatzes.</span><span class="sxs-lookup"><span data-stu-id="7b027-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="7b027-113">EventID</span><span class="sxs-lookup"><span data-stu-id="7b027-113">EventID</span></span>  
 <span data-ttu-id="7b027-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="7b027-114">Data type: sint32</span></span>  
<span data-ttu-id="7b027-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7b027-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b027-116">Die Ziel-ID des Ablaufverfolgungsdatensatzes.</span><span class="sxs-lookup"><span data-stu-id="7b027-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="7b027-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="7b027-117">TraceRecord</span></span>  
 <span data-ttu-id="7b027-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="7b027-118">Data type: string</span></span>  
<span data-ttu-id="7b027-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7b027-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b027-120">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="7b027-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b027-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7b027-121">Requirements</span></span>  
  
|<span data-ttu-id="7b027-122">MOF</span><span class="sxs-lookup"><span data-stu-id="7b027-122">MOF</span></span>|<span data-ttu-id="7b027-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7b027-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7b027-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="7b027-124">Namespace</span></span>|<span data-ttu-id="7b027-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7b027-125">Defined in root\ServiceModel</span></span>|

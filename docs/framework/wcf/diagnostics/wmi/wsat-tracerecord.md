---
title: WSAT_TraceRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d24f74d4086a5499d3bfd4ef6183d377528acc21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="wsattracerecord"></a><span data-ttu-id="57f73-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="57f73-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="57f73-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="57f73-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57f73-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="57f73-104">Syntax</span></span>  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="57f73-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="57f73-105">Methods</span></span>  
 <span data-ttu-id="57f73-106">Die Klasse WSAT_TraceRecord definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="57f73-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="57f73-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="57f73-107">Properties</span></span>  
 <span data-ttu-id="57f73-108">Die Klasse WSAT_TraceRecord weist die folgenden Eigenschaften auf:</span><span class="sxs-lookup"><span data-stu-id="57f73-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="57f73-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="57f73-109">ActivityID</span></span>  
 <span data-ttu-id="57f73-110">Datentyp: object</span><span class="sxs-lookup"><span data-stu-id="57f73-110">Data type: object</span></span>  
<span data-ttu-id="57f73-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="57f73-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="57f73-112">Die Aktivitäts-ID des Ablaufverfolgungsdatensatzes.</span><span class="sxs-lookup"><span data-stu-id="57f73-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="57f73-113">EventID</span><span class="sxs-lookup"><span data-stu-id="57f73-113">EventID</span></span>  
 <span data-ttu-id="57f73-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="57f73-114">Data type: sint32</span></span>  
<span data-ttu-id="57f73-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="57f73-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="57f73-116">Die Ziel-ID des Ablaufverfolgungsdatensatzes.</span><span class="sxs-lookup"><span data-stu-id="57f73-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="57f73-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="57f73-117">TraceRecord</span></span>  
 <span data-ttu-id="57f73-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="57f73-118">Data type: string</span></span>  
<span data-ttu-id="57f73-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="57f73-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="57f73-120">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="57f73-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57f73-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="57f73-121">Requirements</span></span>  
  
|<span data-ttu-id="57f73-122">MOF</span><span class="sxs-lookup"><span data-stu-id="57f73-122">MOF</span></span>|<span data-ttu-id="57f73-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="57f73-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="57f73-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="57f73-124">Namespace</span></span>|<span data-ttu-id="57f73-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="57f73-125">Defined in root\ServiceModel</span></span>|

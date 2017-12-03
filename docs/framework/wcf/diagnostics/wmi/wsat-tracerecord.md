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
ms.openlocfilehash: b4e701c2f0d669a04be7f7235c8ab1edb8ce1612
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="wsattracerecord"></a><span data-ttu-id="41850-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="41850-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="41850-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="41850-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41850-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="41850-104">Syntax</span></span>  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="41850-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="41850-105">Methods</span></span>  
 <span data-ttu-id="41850-106">Die Klasse WSAT_TraceRecord definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="41850-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="41850-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="41850-107">Properties</span></span>  
 <span data-ttu-id="41850-108">Die Klasse WSAT_TraceRecord weist die folgenden Eigenschaften auf:</span><span class="sxs-lookup"><span data-stu-id="41850-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="41850-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="41850-109">ActivityID</span></span>  
 <span data-ttu-id="41850-110">Datentyp: object</span><span class="sxs-lookup"><span data-stu-id="41850-110">Data type: object</span></span>  
<span data-ttu-id="41850-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="41850-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="41850-112">Die Aktivitäts-ID des Ablaufverfolgungsdatensatzes.</span><span class="sxs-lookup"><span data-stu-id="41850-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="41850-113">EventID</span><span class="sxs-lookup"><span data-stu-id="41850-113">EventID</span></span>  
 <span data-ttu-id="41850-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="41850-114">Data type: sint32</span></span>  
<span data-ttu-id="41850-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="41850-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="41850-116">Die Ziel-ID des Ablaufverfolgungsdatensatzes.</span><span class="sxs-lookup"><span data-stu-id="41850-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="41850-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="41850-117">TraceRecord</span></span>  
 <span data-ttu-id="41850-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="41850-118">Data type: string</span></span>  
<span data-ttu-id="41850-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="41850-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="41850-120">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="41850-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41850-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="41850-121">Requirements</span></span>  
  
|<span data-ttu-id="41850-122">MOF</span><span class="sxs-lookup"><span data-stu-id="41850-122">MOF</span></span>|<span data-ttu-id="41850-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="41850-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="41850-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="41850-124">Namespace</span></span>|<span data-ttu-id="41850-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="41850-125">Defined in root\ServiceModel</span></span>|

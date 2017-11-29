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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3966311bc10b5ad2ee401ef9e3e13c8f36e14505
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="wsattracerecord"></a><span data-ttu-id="8e8c5-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="8e8c5-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="8e8c5-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="8e8c5-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e8c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e8c5-104">Syntax</span></span>  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8e8c5-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="8e8c5-105">Methods</span></span>  
 <span data-ttu-id="8e8c5-106">Die Klasse WSAT_TraceRecord definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="8e8c5-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8e8c5-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8e8c5-107">Properties</span></span>  
 <span data-ttu-id="8e8c5-108">Die Klasse WSAT_TraceRecord weist die folgenden Eigenschaften auf:</span><span class="sxs-lookup"><span data-stu-id="8e8c5-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="8e8c5-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="8e8c5-109">ActivityID</span></span>  
 <span data-ttu-id="8e8c5-110">Datentyp: object</span><span class="sxs-lookup"><span data-stu-id="8e8c5-110">Data type: object</span></span>  
<span data-ttu-id="8e8c5-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="8e8c5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e8c5-112">Die Aktivitäts-ID des Ablaufverfolgungsdatensatzes.</span><span class="sxs-lookup"><span data-stu-id="8e8c5-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="8e8c5-113">EventID</span><span class="sxs-lookup"><span data-stu-id="8e8c5-113">EventID</span></span>  
 <span data-ttu-id="8e8c5-114">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="8e8c5-114">Data type: sint32</span></span>  
<span data-ttu-id="8e8c5-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="8e8c5-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e8c5-116">Die Ziel-ID des Ablaufverfolgungsdatensatzes.</span><span class="sxs-lookup"><span data-stu-id="8e8c5-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="8e8c5-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="8e8c5-117">TraceRecord</span></span>  
 <span data-ttu-id="8e8c5-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="8e8c5-118">Data type: string</span></span>  
<span data-ttu-id="8e8c5-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="8e8c5-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8e8c5-120">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="8e8c5-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e8c5-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8e8c5-121">Requirements</span></span>  
  
|<span data-ttu-id="8e8c5-122">MOF</span><span class="sxs-lookup"><span data-stu-id="8e8c5-122">MOF</span></span>|<span data-ttu-id="8e8c5-123">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="8e8c5-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8e8c5-124">Namespace</span><span class="sxs-lookup"><span data-stu-id="8e8c5-124">Namespace</span></span>|<span data-ttu-id="8e8c5-125">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8e8c5-125">Defined in root\ServiceModel</span></span>|

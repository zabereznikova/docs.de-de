---
title: ICorDebugThread2::GetConnectionID-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread2.GetConnectionID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetConnectionID
helpviewer_keywords:
- ICorDebugThread2::GetConnectionID method [.NET Framework debugging]
- GetConnectionID method [.NET Framework debugging]
ms.assetid: 9c76b587-f941-4fa1-8b86-f3494fb10c8e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 28fa949de768191061bd747034a5c951a03b8596
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread2getconnectionid-method"></a><span data-ttu-id="f00ae-102">ICorDebugThread2::GetConnectionID-Methode</span><span class="sxs-lookup"><span data-stu-id="f00ae-102">ICorDebugThread2::GetConnectionID Method</span></span>
<span data-ttu-id="f00ae-103">Ruft den Bezeichner der Verbindung für dieses ICorDebugThread2-Objekt.</span><span class="sxs-lookup"><span data-stu-id="f00ae-103">Gets the connection identifier for this ICorDebugThread2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f00ae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f00ae-104">Syntax</span></span>  
  
```  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f00ae-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f00ae-105">Parameters</span></span>  
 `pdwConnectionId`  
 <span data-ttu-id="f00ae-106">[out] Ein `CONNID` , die den Bezeichner der Verbindung darstellt.</span><span class="sxs-lookup"><span data-stu-id="f00ae-106">[out] A `CONNID` that represents the connection identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f00ae-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f00ae-107">Remarks</span></span>  
 <span data-ttu-id="f00ae-108">Die `GetConnectionID` Methodenrückgabe 0 (null), in der `pdwConnectionId` -Parameters, wenn dieser Thread nicht Teil einer Verbindung ist.</span><span class="sxs-lookup"><span data-stu-id="f00ae-108">The `GetConnectionID` method returns zero in the `pdwConnectionId` parameter, if this thread is not part of a connection.</span></span>  
  
 <span data-ttu-id="f00ae-109">Wenn dieser Thread mit einer Instanz von Microsoft SQL Server 2005 Analysis Services (SSAS), besteht die `CONNID` ordnet einen Serverprozessbezeichner (SPID).</span><span class="sxs-lookup"><span data-stu-id="f00ae-109">If this thread is connected to an instance of Microsoft SQL Server 2005 Analysis Services (SSAS), the `CONNID` maps to a server process identifier (SPID).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f00ae-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f00ae-110">Requirements</span></span>  
 <span data-ttu-id="f00ae-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f00ae-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f00ae-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f00ae-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f00ae-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f00ae-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f00ae-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f00ae-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

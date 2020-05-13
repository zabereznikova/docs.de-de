---
title: ICorDebugThread2::GetConnectionID-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: c630daa50d465622c421381ac080eaa8d9d8d01d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379075"
---
# <a name="icordebugthread2getconnectionid-method"></a><span data-ttu-id="20a3b-102">ICorDebugThread2::GetConnectionID-Methode</span><span class="sxs-lookup"><span data-stu-id="20a3b-102">ICorDebugThread2::GetConnectionID Method</span></span>
<span data-ttu-id="20a3b-103">Ruft den Verbindungs Bezeichner für dieses ICorDebugThread2-Objekt ab.</span><span class="sxs-lookup"><span data-stu-id="20a3b-103">Gets the connection identifier for this ICorDebugThread2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20a3b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="20a3b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20a3b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="20a3b-105">Parameters</span></span>  
 `pdwConnectionId`  
 <span data-ttu-id="20a3b-106">vorgenommen Ein `CONNID` , der den Verbindungs Bezeichner darstellt.</span><span class="sxs-lookup"><span data-stu-id="20a3b-106">[out] A `CONNID` that represents the connection identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20a3b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20a3b-107">Remarks</span></span>  
 <span data-ttu-id="20a3b-108">Die- `GetConnectionID` Methode gibt 0 (null) im- `pdwConnectionId` Parameter zurück, wenn dieser Thread nicht Teil einer Verbindung ist.</span><span class="sxs-lookup"><span data-stu-id="20a3b-108">The `GetConnectionID` method returns zero in the `pdwConnectionId` parameter, if this thread is not part of a connection.</span></span>  
  
 <span data-ttu-id="20a3b-109">Wenn dieser Thread mit einer Instanz von Microsoft SQL Server 2005 Analysis Services (SSAS) verbunden ist, wird `CONNID` eine SPID (Server Process Identifier) zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="20a3b-109">If this thread is connected to an instance of Microsoft SQL Server 2005 Analysis Services (SSAS), the `CONNID` maps to a server process identifier (SPID).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20a3b-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="20a3b-110">Requirements</span></span>  
 <span data-ttu-id="20a3b-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20a3b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20a3b-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20a3b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20a3b-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20a3b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20a3b-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20a3b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

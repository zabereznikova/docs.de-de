---
title: ICorDebugAppDomain3::GetCachedWinRTTypes-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes method [.NET Framework debugging]
- GetCachedWinRTTypes method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 9afd0e04-a403-41e2-9528-a6dcbcdcbd4d
topic_type:
- apiref
ms.openlocfilehash: e5fd1730bbe5b6f2905691dce41a7f503227534a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179069"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="607d4-102">ICorDebugAppDomain3::GetCachedWinRTTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="607d4-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="607d4-103">Ruft einen Enumerator für alle zwischengespeicherten Windows-Runtime-Typen ab.</span><span class="sxs-lookup"><span data-stu-id="607d4-103">Gets an enumerator for all cached Windows Runtime types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="607d4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="607d4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypes (
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="607d4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="607d4-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="607d4-106">[out] Ein Zeiger auf ein [ICorDebugGuidToTypeEnum-Schnittstellenobjekt,](icordebugguidtotypeenum-interface.md) das die verwalteten Darstellungen von Windows-Runtime-Typen aufzählen kann, die derzeit in der Anwendungsdomäne geladen sind.</span><span class="sxs-lookup"><span data-stu-id="607d4-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of Windows Runtime types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="607d4-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="607d4-107">Requirements</span></span>  
 <span data-ttu-id="607d4-108">**Plattformen:** Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="607d4-108">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="607d4-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="607d4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="607d4-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="607d4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="607d4-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="607d4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="607d4-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="607d4-112">See also</span></span>

- [<span data-ttu-id="607d4-113">ICorDebugAppDomain3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="607d4-113">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)

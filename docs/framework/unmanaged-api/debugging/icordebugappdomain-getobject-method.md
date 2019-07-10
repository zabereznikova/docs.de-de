---
title: ICorDebugAppDomain::GetObject-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetObject
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1201ac0dca9cbd48c24b2621eba079ae672fd310
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737852"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="29229-102">ICorDebugAppDomain::GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="29229-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="29229-103">Ruft einen Schnittstellenzeiger auf die Anwendungsdomäne der common Language Runtime (CLR) ab.</span><span class="sxs-lookup"><span data-stu-id="29229-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29229-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="29229-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29229-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="29229-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="29229-106">[out] Ein Zeiger auf die Adresse eines Objekts der ICorDebugValue-Schnittstelle, die die CLR die Anwendungsdomäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="29229-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29229-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="29229-107">Return Value</span></span>  
 <span data-ttu-id="29229-108">Wenn eine verwaltete <xref:System.AppDomain?displayProperty=nameWithType> Objekt noch nicht für diese Anwendungsdomäne erstellt wurde, gibt die Methode zurück `S_FALSE` und `NULL` in `*ppObject`.</span><span class="sxs-lookup"><span data-stu-id="29229-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29229-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="29229-109">Remarks</span></span>  
 <span data-ttu-id="29229-110">Jede Anwendungsdomäne, in einem Prozess ist möglicherweise ein verwaltetes <xref:System.AppDomain?displayProperty=nameWithType> Objekt in der Laufzeit, die es darstellt.</span><span class="sxs-lookup"><span data-stu-id="29229-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="29229-111">Diese Funktion ruft ICorDebugValue-Schnittstellenobjekts, das dieser verwalteten entspricht <xref:System.AppDomain?displayProperty=nameWithType> Objekt.</span><span class="sxs-lookup"><span data-stu-id="29229-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29229-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="29229-112">Requirements</span></span>  
 <span data-ttu-id="29229-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29229-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29229-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29229-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29229-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29229-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29229-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29229-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>

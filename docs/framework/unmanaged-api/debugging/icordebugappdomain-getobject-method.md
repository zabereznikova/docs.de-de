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
ms.openlocfilehash: a163667ea7eca1ed817d642efdb8fc4efa2a0651
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676061"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="446fb-102">ICorDebugAppDomain::GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="446fb-102">ICorDebugAppDomain::GetObject Method</span></span>

<span data-ttu-id="446fb-103">Ruft einen Schnittstellen Zeiger auf die Common Language Runtime (CLR)-Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="446fb-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="446fb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="446fb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="446fb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="446fb-105">Parameters</span></span>  

 `ppObject`  
 <span data-ttu-id="446fb-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugValue-Schnittstellen Objekts, das die CLR-Anwendungsdomäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="446fb-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="446fb-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="446fb-107">Return Value</span></span>  

 <span data-ttu-id="446fb-108">Wenn ein verwaltetes <xref:System.AppDomain?displayProperty=nameWithType> Objekt für diese Anwendungsdomäne nicht erstellt wurde, gibt die Methode zurück `S_FALSE` und stellt `NULL` in dar `*ppObject` .</span><span class="sxs-lookup"><span data-stu-id="446fb-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="446fb-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="446fb-109">Remarks</span></span>  

 <span data-ttu-id="446fb-110">Jede Anwendungsdomäne in einem Prozess kann über ein verwaltetes <xref:System.AppDomain?displayProperty=nameWithType> Objekt in der Laufzeit verfügen, das Sie darstellt.</span><span class="sxs-lookup"><span data-stu-id="446fb-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="446fb-111">Diese Funktion Ruft ein ICorDebug Value-Schnittstellen Objekt ab, das diesem verwalteten <xref:System.AppDomain?displayProperty=nameWithType> Objekt entspricht.</span><span class="sxs-lookup"><span data-stu-id="446fb-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="446fb-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="446fb-112">Requirements</span></span>  

 <span data-ttu-id="446fb-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="446fb-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="446fb-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="446fb-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="446fb-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="446fb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="446fb-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="446fb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>

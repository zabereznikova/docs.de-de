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
ms.openlocfilehash: a6f528bcef7d06b503b1ee9d7bd4a61d3d3e9672
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406519"
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="9fa6b-102">ICorDebugAppDomain::GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="9fa6b-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="9fa6b-103">Ruft einen Schnittstellenzeiger auf die common Language Runtime (CLR) Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="9fa6b-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fa6b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9fa6b-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9fa6b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9fa6b-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="9fa6b-106">[out] Ein Zeiger auf die Adresse des ICorDebugValue-Schnittstellenobjekts, das die CLR die Anwendungsdomäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="9fa6b-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9fa6b-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9fa6b-107">Return Value</span></span>  
 <span data-ttu-id="9fa6b-108">Wenn ein verwaltetes <xref:System.AppDomain?displayProperty=nameWithType> Objekt wurde nicht für diese Anwendungsdomäne erstellt wurde, gibt die Methode zurück `S_FALSE` und platziert `NULL` in `*ppObject`.</span><span class="sxs-lookup"><span data-stu-id="9fa6b-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9fa6b-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9fa6b-109">Remarks</span></span>  
 <span data-ttu-id="9fa6b-110">Jede Anwendungsdomäne in einem Prozess ist möglicherweise ein verwaltetes <xref:System.AppDomain?displayProperty=nameWithType> Objekt in der Laufzeit, die es darstellt.</span><span class="sxs-lookup"><span data-stu-id="9fa6b-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="9fa6b-111">Diese Funktion ruft eine ICorDebugValue-Schnittstellenobjekts, das dies verwaltet entspricht <xref:System.AppDomain?displayProperty=nameWithType> Objekt.</span><span class="sxs-lookup"><span data-stu-id="9fa6b-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fa6b-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9fa6b-112">Requirements</span></span>  
 <span data-ttu-id="9fa6b-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fa6b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fa6b-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9fa6b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9fa6b-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fa6b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fa6b-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fa6b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>

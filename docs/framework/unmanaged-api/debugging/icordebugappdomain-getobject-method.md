---
title: ICorDebugAppDomain::GetObject-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.GetObject
api_location: corguids.lib
api_type: COM
f1_keywords: ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5f8206c6e5efbee8522f425f9078d99a39bbdd42
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomaingetobject-method"></a><span data-ttu-id="e67a1-102">ICorDebugAppDomain::GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="e67a1-102">ICorDebugAppDomain::GetObject Method</span></span>
<span data-ttu-id="e67a1-103">Ruft einen Schnittstellenzeiger auf die common Language Runtime (CLR) Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="e67a1-103">Gets an interface pointer to the common language runtime (CLR) application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e67a1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e67a1-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e67a1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e67a1-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="e67a1-106">[out] Ein Zeiger auf die Adresse des ICorDebugValue-Schnittstellenobjekts, das die CLR die Anwendungsdomäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="e67a1-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e67a1-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e67a1-107">Return Value</span></span>  
 <span data-ttu-id="e67a1-108">Wenn ein verwaltetes <xref:System.AppDomain?displayProperty=nameWithType> Objekt wurde nicht für diese Anwendungsdomäne erstellt wurde, gibt die Methode zurück `S_FALSE` und platziert `NULL` in `*ppObject`.</span><span class="sxs-lookup"><span data-stu-id="e67a1-108">If a managed <xref:System.AppDomain?displayProperty=nameWithType> object hasn't been constructed for this application domain, the method returns `S_FALSE` and places `NULL` in `*ppObject`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e67a1-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e67a1-109">Remarks</span></span>  
 <span data-ttu-id="e67a1-110">Jede Anwendungsdomäne in einem Prozess ist möglicherweise ein verwaltetes <xref:System.AppDomain?displayProperty=nameWithType> Objekt in der Laufzeit, die es darstellt.</span><span class="sxs-lookup"><span data-stu-id="e67a1-110">Each application domain in a process may have a managed <xref:System.AppDomain?displayProperty=nameWithType> object in the runtime that represents it.</span></span> <span data-ttu-id="e67a1-111">Diese Funktion ruft eine ICorDebugValue-Schnittstellenobjekts, das dies verwaltet entspricht <xref:System.AppDomain?displayProperty=nameWithType> Objekt.</span><span class="sxs-lookup"><span data-stu-id="e67a1-111">This function gets an ICorDebugValue interface object that corresponds to this managed <xref:System.AppDomain?displayProperty=nameWithType> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e67a1-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e67a1-112">Requirements</span></span>  
 <span data-ttu-id="e67a1-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e67a1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e67a1-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e67a1-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e67a1-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e67a1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e67a1-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e67a1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>

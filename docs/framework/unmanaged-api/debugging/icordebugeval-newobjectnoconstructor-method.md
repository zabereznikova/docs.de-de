---
title: ICorDebugEval::NewObjectNoConstructor-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.NewObjectNoConstructor
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::NewObjectNoConstructor
helpviewer_keywords:
- NewObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval::NewObjectNoConstructor method [.NET Framework debugging]
ms.assetid: 80d509ca-b5e3-4c46-9c14-800db73d9bf7
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ceb35781d4685e3576470da3b99a6666ba233e19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="db333-102">ICorDebugEval::NewObjectNoConstructor-Methode</span><span class="sxs-lookup"><span data-stu-id="db333-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="db333-103">Ordnet eine neue Objektinstanz des angegebenen Typs, ohne zu versuchen, eine Konstruktormethode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="db333-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="db333-104">Diese Methode ist veraltet in .NET Framework, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="db333-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="db333-105">Verwendung [ICorDebugEval2:: NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) stattdessen.</span><span class="sxs-lookup"><span data-stu-id="db333-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db333-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="db333-106">Syntax</span></span>  
  
```  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="db333-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="db333-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="db333-108">[in] Ein Zeiger auf ein ICorDebugClass-Objekt, das den Typ des zu instanziierenden Objekts darstellt.</span><span class="sxs-lookup"><span data-stu-id="db333-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db333-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="db333-109">Requirements</span></span>  
 <span data-ttu-id="db333-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db333-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db333-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db333-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db333-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db333-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db333-113">**.NET Framework-Versionen:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="db333-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db333-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db333-114">See Also</span></span>  
 [<span data-ttu-id="db333-115">NewParameterizedObjectNoConstructor-Methode</span><span class="sxs-lookup"><span data-stu-id="db333-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)

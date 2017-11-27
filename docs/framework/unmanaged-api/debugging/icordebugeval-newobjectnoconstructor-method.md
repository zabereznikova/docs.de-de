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
ms.openlocfilehash: 415c8f2faae44fbdfec5441abaff8b93042ac124
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="8c4d3-102">ICorDebugEval::NewObjectNoConstructor-Methode</span><span class="sxs-lookup"><span data-stu-id="8c4d3-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="8c4d3-103">Ordnet eine neue Objektinstanz des angegebenen Typs, ohne zu versuchen, eine Konstruktormethode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8c4d3-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="8c4d3-104">Diese Methode ist veraltet in .NET Framework, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="8c4d3-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="8c4d3-105">Verwendung [ICorDebugEval2:: NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) stattdessen.</span><span class="sxs-lookup"><span data-stu-id="8c4d3-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c4d3-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c4d3-106">Syntax</span></span>  
  
```  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c4d3-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="8c4d3-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="8c4d3-108">[in] Ein Zeiger auf ein ICorDebugClass-Objekt, das den Typ des zu instanziierenden Objekts darstellt.</span><span class="sxs-lookup"><span data-stu-id="8c4d3-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c4d3-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8c4d3-109">Requirements</span></span>  
 <span data-ttu-id="8c4d3-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c4d3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c4d3-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c4d3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c4d3-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c4d3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c4d3-113">**.NET Framework-Versionen:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="8c4d3-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c4d3-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c4d3-114">See Also</span></span>  
 [<span data-ttu-id="8c4d3-115">NewParameterizedObjectNoConstructor-Methode</span><span class="sxs-lookup"><span data-stu-id="8c4d3-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)

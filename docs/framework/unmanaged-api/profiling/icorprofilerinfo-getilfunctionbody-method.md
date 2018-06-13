---
title: ICorProfilerInfo::GetILFunctionBody-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bde194023ff6913db9a56e30eddaad8d7abc5ad1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452806"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="31946-102">ICorProfilerInfo::GetILFunctionBody-Methode</span><span class="sxs-lookup"><span data-stu-id="31946-102">ICorProfilerInfo::GetILFunctionBody Method</span></span>
<span data-ttu-id="31946-103">Ruft einen Zeiger auf den Text einer Methode in Microsoft intermediate Language (MSIL)-Code, beginnend mit dem Header.</span><span class="sxs-lookup"><span data-stu-id="31946-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31946-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="31946-104">Syntax</span></span>  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="31946-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="31946-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="31946-106">[in] Die ID des Moduls, in dem die Funktion befindet.</span><span class="sxs-lookup"><span data-stu-id="31946-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="31946-107">[in] Das Metadatentoken für die Methode.</span><span class="sxs-lookup"><span data-stu-id="31946-107">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="31946-108">[out] Ein Zeiger auf die Method-Header.</span><span class="sxs-lookup"><span data-stu-id="31946-108">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="31946-109">[out] Eine ganze Zahl, die die Größe der Methode angibt.</span><span class="sxs-lookup"><span data-stu-id="31946-109">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31946-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="31946-110">Remarks</span></span>  
 <span data-ttu-id="31946-111">Eine Methode wird vom Modul begrenzt, in dem er sich befindet.</span><span class="sxs-lookup"><span data-stu-id="31946-111">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="31946-112">Da die `GetILFunctionBody` -Methode entwickelt, um MSIL-Code eine Toolzugriff erteilen, bevor er von der common Language Runtime (CLR) geladen wurde, es verwendet das Metadatentoken der Methode, um die gewünschte Instanz gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="31946-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 <span data-ttu-id="31946-113">`GetILFunctionBody` kann ein HRESULT CORPROF_E_FUNCTION_NOT_IL zurückgeben, wenn die `methodId` verweist auf eine Methode ohne MSIL-code (z. B. eine abstrakte Methode oder eine Plattform invoke PInvoke-Methode).</span><span class="sxs-lookup"><span data-stu-id="31946-113">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31946-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="31946-114">Requirements</span></span>  
 <span data-ttu-id="31946-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31946-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31946-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="31946-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="31946-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31946-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31946-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31946-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31946-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31946-119">See Also</span></span>  
 [<span data-ttu-id="31946-120">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31946-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)

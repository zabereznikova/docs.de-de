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
ms.openlocfilehash: 5984c63f0e1a1859dd5cc2550d6dc37c963affb3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503002"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="01a7f-102">ICorProfilerInfo::GetILFunctionBody-Methode</span><span class="sxs-lookup"><span data-stu-id="01a7f-102">ICorProfilerInfo::GetILFunctionBody Method</span></span>
<span data-ttu-id="01a7f-103">Ruft einen Zeiger auf den Text einer Methode im MSIL-Code (Microsoft Intermediate Language) ab, beginnend bei der Kopfzeile.</span><span class="sxs-lookup"><span data-stu-id="01a7f-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01a7f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="01a7f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01a7f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="01a7f-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="01a7f-106">in Die ID des Moduls, in dem sich die Funktion befindet.</span><span class="sxs-lookup"><span data-stu-id="01a7f-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="01a7f-107">in Das Metadatentoken für die Methode.</span><span class="sxs-lookup"><span data-stu-id="01a7f-107">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="01a7f-108">vorgenommen Ein Zeiger auf den-Header der Methode.</span><span class="sxs-lookup"><span data-stu-id="01a7f-108">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="01a7f-109">vorgenommen Eine ganze Zahl, die die Größe der Methode angibt.</span><span class="sxs-lookup"><span data-stu-id="01a7f-109">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01a7f-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="01a7f-110">Remarks</span></span>  
 <span data-ttu-id="01a7f-111">Eine Methode wird durch das Modul festgelegt, in dem Sie sich befindet.</span><span class="sxs-lookup"><span data-stu-id="01a7f-111">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="01a7f-112">Da die- `GetILFunctionBody` Methode so konzipiert ist, dass ein Tool Zugriff auf den MSIL-Code erhält, bevor Sie von der Common Language Runtime (CLR) geladen wurde, wird das Metadatentoken der-Methode verwendet, um die gewünschte Instanz zu suchen.</span><span class="sxs-lookup"><span data-stu-id="01a7f-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 <span data-ttu-id="01a7f-113">`GetILFunctionBody`kann eine CORPROF_E_FUNCTION_NOT_IL HRESULT zurückgeben, wenn `methodId` auf eine Methode ohne MSIL-Code verweist (z. b. eine abstrakte Methode oder eine Platt Form Aufruf Methode (PInvoke)).</span><span class="sxs-lookup"><span data-stu-id="01a7f-113">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01a7f-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="01a7f-114">Requirements</span></span>  
 <span data-ttu-id="01a7f-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01a7f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01a7f-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="01a7f-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="01a7f-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01a7f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01a7f-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01a7f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01a7f-119">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="01a7f-119">See also</span></span>

- [<span data-ttu-id="01a7f-120">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01a7f-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)

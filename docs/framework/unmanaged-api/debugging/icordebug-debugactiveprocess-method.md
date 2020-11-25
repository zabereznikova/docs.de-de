---
title: ICorDebug::DebugActiveProcess-Methode
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
ms.openlocfilehash: 1713623fa575bea6df649106b37212f7aeaee6db
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723466"
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="67cc8-102">ICorDebug::DebugActiveProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="67cc8-102">ICorDebug::DebugActiveProcess Method</span></span>

<span data-ttu-id="67cc8-103">Fügt den Debugger an einen vorhandenen Prozess an.</span><span class="sxs-lookup"><span data-stu-id="67cc8-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67cc8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="67cc8-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67cc8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="67cc8-105">Parameters</span></span>  

 `id`  
 <span data-ttu-id="67cc8-106">in Die ID des Prozesses, an den der Debugger angefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="67cc8-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="67cc8-107">in Boolescher Wert, der auf festgelegt wird, `true` Wenn sich der Debugger als Win32-Debugger für den Prozessverhalten und die nicht verwalteten Rückrufe verteilen soll, andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="67cc8-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="67cc8-108">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugProcess-Objekts, das den Prozess darstellt, dem der Debugger angefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="67cc8-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67cc8-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="67cc8-109">Remarks</span></span>  

 <span data-ttu-id="67cc8-110">Interop-Debuggen wird auf Win9x-und nicht-x86-Plattformen wie IA-64-basierten und AMD64-basierten Plattformen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="67cc8-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67cc8-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="67cc8-111">Requirements</span></span>  

 <span data-ttu-id="67cc8-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67cc8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67cc8-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67cc8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67cc8-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67cc8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67cc8-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67cc8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67cc8-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="67cc8-116">See also</span></span>

- [<span data-ttu-id="67cc8-117">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67cc8-117">ICorDebug Interface</span></span>](icordebug-interface.md)

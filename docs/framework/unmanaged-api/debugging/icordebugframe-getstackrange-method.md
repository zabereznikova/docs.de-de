---
title: ICorDebugFrame::GetStackRange-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
ms.openlocfilehash: 7a35ce025360e0ec8b7085d68e54548026b7c7fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178900"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="5de0c-102">ICorDebugFrame::GetStackRange-Methode</span><span class="sxs-lookup"><span data-stu-id="5de0c-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="5de0c-103">Ruft den absoluten Adressbereich dieses Stapelrahmens ab.</span><span class="sxs-lookup"><span data-stu-id="5de0c-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5de0c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5de0c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5de0c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5de0c-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="5de0c-106">[out] Ein Zeiger auf `CORDB_ADDRESS` ein, der die Startadresse des `ICorDebugFrame` Stapelrahmens angibt, der durch dieses Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5de0c-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="5de0c-107">[out] Ein Zeiger auf `CORDB_ADDRESS` ein, der die Endadresse des `ICorDebugFrame` Stapelrahmens angibt, der durch dieses Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5de0c-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5de0c-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5de0c-108">Remarks</span></span>  
 <span data-ttu-id="5de0c-109">Der Adressbereich des Stapels ist nützlich, um übereinandergelegte Stapelablaufverfolgungen, die von mehreren Debugging-Engines gesammelt wurden, zusammenzufügen.</span><span class="sxs-lookup"><span data-stu-id="5de0c-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="5de0c-110">Der numerische Bereich enthält keine Informationen über den Inhalt des Stapelrahmens.</span><span class="sxs-lookup"><span data-stu-id="5de0c-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="5de0c-111">Es ist nur für den Vergleich von Stapelrahmenpositionen sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="5de0c-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5de0c-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5de0c-112">Requirements</span></span>  
 <span data-ttu-id="5de0c-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5de0c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5de0c-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5de0c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5de0c-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5de0c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5de0c-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5de0c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

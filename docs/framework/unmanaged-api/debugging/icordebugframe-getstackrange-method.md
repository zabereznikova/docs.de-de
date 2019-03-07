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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 43532888d181adcb7a7e3760f2a5e3d8f664a35c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492282"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="ee463-102">ICorDebugFrame::GetStackRange-Methode</span><span class="sxs-lookup"><span data-stu-id="ee463-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="ee463-103">Ruft den Bereich der absoluten Adresse dieses Stapelrahmens ab.</span><span class="sxs-lookup"><span data-stu-id="ee463-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee463-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee463-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee463-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ee463-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="ee463-106">[out] Ein Zeiger auf eine `CORDB_ADDRESS` , die angibt, dass der Startadresse des Stapelrahmens dargestellt durch diese `ICorDebugFrame` Objekt.</span><span class="sxs-lookup"><span data-stu-id="ee463-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="ee463-107">[out] Ein Zeiger auf eine `CORDB_ADDRESS` , die angibt, dass der Endadresse des Stapelrahmens dargestellt durch diese `ICorDebugFrame` Objekt.</span><span class="sxs-lookup"><span data-stu-id="ee463-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee463-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ee463-108">Remarks</span></span>  
 <span data-ttu-id="ee463-109">Der Adressbereich des Stapels eignet sich für die Zusammenführung von mehrere Debug-Engines erfassten stapelüberwachungen überlappender.</span><span class="sxs-lookup"><span data-stu-id="ee463-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="ee463-110">Der numerische Bereich bietet keine Informationen über den Inhalt des Stapelrahmens.</span><span class="sxs-lookup"><span data-stu-id="ee463-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="ee463-111">Es ist sinnvoll, nur für den Vergleich der Stack-Frame-Standorte.</span><span class="sxs-lookup"><span data-stu-id="ee463-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee463-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ee463-112">Requirements</span></span>  
 <span data-ttu-id="ee463-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee463-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee463-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee463-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee463-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee463-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee463-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee463-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

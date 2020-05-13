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
ms.openlocfilehash: cacdccf5c27cd1d115134d49e754b4ace2870b72
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205162"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="161b0-102">ICorDebugFrame::GetStackRange-Methode</span><span class="sxs-lookup"><span data-stu-id="161b0-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="161b0-103">Ruft den absoluten Adressbereich dieses Stapel Rahmens ab.</span><span class="sxs-lookup"><span data-stu-id="161b0-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="161b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="161b0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="161b0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="161b0-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="161b0-106">vorgenommen Ein Zeiger auf einen `CORDB_ADDRESS` , der die Startadresse des Stapel Rahmens angibt, der durch dieses-Objekt dargestellt wird `ICorDebugFrame` .</span><span class="sxs-lookup"><span data-stu-id="161b0-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="161b0-107">vorgenommen Ein Zeiger auf einen `CORDB_ADDRESS` , der die Endadresse des Stapel Rahmens angibt, der durch dieses-Objekt dargestellt wird `ICorDebugFrame` .</span><span class="sxs-lookup"><span data-stu-id="161b0-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="161b0-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="161b0-108">Remarks</span></span>  
 <span data-ttu-id="161b0-109">Der Adressbereich des Stapels eignet sich für die Zusammenfassung von verschachtelten Stapel Überwachungen, die von mehreren Debugmodulen gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="161b0-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="161b0-110">Der numerische Bereich enthält keine Informationen über den Inhalt des Stapel Rahmens.</span><span class="sxs-lookup"><span data-stu-id="161b0-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="161b0-111">Dies ist nur für den Vergleich von Stapel Rahmen Standorten sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="161b0-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="161b0-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="161b0-112">Requirements</span></span>  
 <span data-ttu-id="161b0-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="161b0-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="161b0-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="161b0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="161b0-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="161b0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="161b0-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="161b0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

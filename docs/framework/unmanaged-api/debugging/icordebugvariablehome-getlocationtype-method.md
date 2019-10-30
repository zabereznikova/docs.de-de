---
title: 'Icordebugvariablehome:: getlocationtype-Methode'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type:
- apiref
ms.openlocfilehash: 1dd4e9510831b4c878e9c1246dabe4add919130c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125111"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="3b4ea-102">Icordebugvariablehome:: getlocationtype-Methode</span><span class="sxs-lookup"><span data-stu-id="3b4ea-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="3b4ea-103">Ruft den Typ des systemeigenen Speicher Orts der Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="3b4ea-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b4ea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3b4ea-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b4ea-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3b4ea-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="3b4ea-106">vorgenommen Ein Zeiger auf den Typ des nativen Speicher Orts der Variablen.</span><span class="sxs-lookup"><span data-stu-id="3b4ea-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="3b4ea-107">Weitere Informationen finden Sie in der [variablelocationtype](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="3b4ea-107">See the [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b4ea-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3b4ea-108">Requirements</span></span>  
 <span data-ttu-id="3b4ea-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b4ea-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b4ea-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b4ea-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b4ea-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b4ea-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b4ea-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b4ea-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b4ea-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b4ea-113">See also</span></span>

- [<span data-ttu-id="3b4ea-114">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3b4ea-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
- [<span data-ttu-id="3b4ea-115">VariableLocationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="3b4ea-115">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)

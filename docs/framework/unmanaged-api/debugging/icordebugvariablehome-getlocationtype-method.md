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
ms.openlocfilehash: 8874deede8b46b93df0e298fb3970fa153b51415
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396574"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="712b5-102">Icordebugvariablehome:: getlocationtype-Methode</span><span class="sxs-lookup"><span data-stu-id="712b5-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="712b5-103">Ruft den Typ des systemeigenen Speicher Orts der Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="712b5-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="712b5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="712b5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="712b5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="712b5-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="712b5-106">vorgenommen Ein Zeiger auf den Typ des nativen Speicher Orts der Variablen.</span><span class="sxs-lookup"><span data-stu-id="712b5-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="712b5-107">Weitere Informationen finden Sie in der [variablelocationtype](variablelocationtype-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="712b5-107">See the [VariableLocationType](variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="712b5-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="712b5-108">Requirements</span></span>  
 <span data-ttu-id="712b5-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="712b5-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="712b5-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="712b5-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="712b5-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="712b5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="712b5-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="712b5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="712b5-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="712b5-113">See also</span></span>

- [<span data-ttu-id="712b5-114">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="712b5-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="712b5-115">VariableLocationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="712b5-115">VariableLocationType Enumeration</span></span>](variablelocationtype-enumeration.md)

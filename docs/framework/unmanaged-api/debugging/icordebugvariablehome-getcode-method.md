---
title: 'Icordebugvariablehome:: GetCode-Methode'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetCode
helpviewer_keywords:
- ICorDebugVariableHome::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: ef002890-4a7b-4a5d-abbf-16c60083f794
topic_type:
- apiref
ms.openlocfilehash: 6f5d99e6dc4290ef69c0a0748fe15ae538e83558
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684225"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="b6cd2-102">Icordebugvariablehome:: GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="b6cd2-102">ICorDebugVariableHome::GetCode Method</span></span>

<span data-ttu-id="b6cd2-103">Ruft die ICorDebugCode-Instanz ab, die dieses [icordebugvariablehome](icordebugvariablehome-interface.md) -Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="b6cd2-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6cd2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6cd2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6cd2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b6cd2-105">Parameters</span></span>  

 `ppCode`  
 <span data-ttu-id="b6cd2-106">vorgenommen Ein Zeiger auf die Adresse der ICorDebugCode-Instanz, die dieses [icordebugvariablehome](icordebugvariablehome-interface.md) -Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="b6cd2-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6cd2-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b6cd2-107">Requirements</span></span>  

 <span data-ttu-id="b6cd2-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6cd2-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6cd2-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6cd2-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6cd2-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6cd2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6cd2-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6cd2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6cd2-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6cd2-112">See also</span></span>

- [<span data-ttu-id="b6cd2-113">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b6cd2-113">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)

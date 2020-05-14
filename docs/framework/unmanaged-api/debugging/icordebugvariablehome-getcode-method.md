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
ms.openlocfilehash: 87d611a7b6e12a9238b00131326e8205778769e6
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396592"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="9b917-102">Icordebugvariablehome:: GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="9b917-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="9b917-103">Ruft die ICorDebugCode-Instanz ab, die dieses [icordebugvariablehome](icordebugvariablehome-interface.md) -Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="9b917-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b917-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b917-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b917-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b917-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="9b917-106">vorgenommen Ein Zeiger auf die Adresse der ICorDebugCode-Instanz, die dieses [icordebugvariablehome](icordebugvariablehome-interface.md) -Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="9b917-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b917-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b917-107">Requirements</span></span>  
 <span data-ttu-id="9b917-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b917-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b917-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b917-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b917-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b917-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b917-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b917-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b917-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b917-112">See also</span></span>

- [<span data-ttu-id="9b917-113">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b917-113">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)

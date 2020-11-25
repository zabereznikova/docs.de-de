---
title: ICorDebugModule::GetBaseAddress-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetBaseAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetBaseAddress
helpviewer_keywords:
- GetBaseAddress method [.NET Framework debugging]
- ICorDebugModule::GetBaseAddress method [.NET Framework debugging]
ms.assetid: 26a82815-1982-4eb7-92d1-5c3d318d5be4
topic_type:
- apiref
ms.openlocfilehash: 4562318c87b79fba5f3d99860ee438c0144e9aae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710245"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="f5a82-102">ICorDebugModule::GetBaseAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="f5a82-102">ICorDebugModule::GetBaseAddress Method</span></span>

<span data-ttu-id="f5a82-103">Ruft die Basisadresse des Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="f5a82-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5a82-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5a82-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5a82-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f5a82-105">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="f5a82-106">vorgenommen Ein `CORDB_ADDRESS` , der die Basisadresse des Moduls angibt.</span><span class="sxs-lookup"><span data-stu-id="f5a82-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5a82-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f5a82-107">Remarks</span></span>  

 <span data-ttu-id="f5a82-108">Wenn es sich bei dem Modul um ein natives Image handelt (d. h., wenn das Modul vom systemeigenen Image Generator, NGen.exe) erstellt wurde, ist die Basisadresse 0 (null).</span><span class="sxs-lookup"><span data-stu-id="f5a82-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5a82-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f5a82-109">Requirements</span></span>  

 <span data-ttu-id="f5a82-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5a82-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5a82-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5a82-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5a82-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5a82-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5a82-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5a82-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a82-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f5a82-114">See also</span></span>

---
title: ICorDebugNativeFrame::GetRegisterSet-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type:
- apiref
ms.openlocfilehash: affab7ae99dbdf85e7eadc89bfd24c42408626ac
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792823"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="0468a-102">ICorDebugNativeFrame::GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="0468a-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="0468a-103">Ruft den Register Satz für diesen Stapel Rahmen ab.</span><span class="sxs-lookup"><span data-stu-id="0468a-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0468a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0468a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0468a-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="0468a-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="0468a-106">vorgenommen Ein Zeiger auf die Adresse eines [ICorDebugRegisterSet](icordebugregisterset-interface.md) -Objekts, das den Register Satz für diesen Stapel Rahmen darstellt.</span><span class="sxs-lookup"><span data-stu-id="0468a-106">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0468a-107">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0468a-107">Requirements</span></span>  
 <span data-ttu-id="0468a-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0468a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0468a-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0468a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0468a-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0468a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0468a-111">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0468a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0468a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0468a-112">See also</span></span>

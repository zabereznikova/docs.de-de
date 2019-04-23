---
title: ICorDebugILCode2::GetLocalVarSigToken-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 17665b77-1342-4115-94fd-9f45b0ecfb0f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9810a8a55fc9c5296bffa5106551f9734dcd61bb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199907"
---
# <a name="icordebugilcode2getlocalvarsigtoken-method"></a><span data-ttu-id="f6f33-102">ICorDebugILCode2::GetLocalVarSigToken-Methode</span><span class="sxs-lookup"><span data-stu-id="f6f33-102">ICorDebugILCode2::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="f6f33-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="f6f33-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="f6f33-104">Ruft den Metadatentoken für die lokale Variablensignatur für die Funktion auf, die in dieser Instanz repräsentiert wird.</span><span class="sxs-lookup"><span data-stu-id="f6f33-104">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6f33-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6f33-105">Syntax</span></span>  
  
```cpp
HRESULT GetLocalVarSigToken(  
   [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6f33-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f6f33-106">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="f6f33-107">[out] Ein Zeiger auf den `mdSignature`-Token für die Signatur der lokalen Variablen für diese Funktion oder `mdSignatureNil`, wenn keine Signatur vorhanden ist (das bedeutet, wenn die Funktion über keine lokalen Variablen verfügt).</span><span class="sxs-lookup"><span data-stu-id="f6f33-107">[out] A pointer to the `mdSignature` token for the local variable signature for this function, or `mdSignatureNil` if there is no signature (that is, if the function doesn't have any local variables).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6f33-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f6f33-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6f33-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f6f33-109">Requirements</span></span>  
 <span data-ttu-id="f6f33-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6f33-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6f33-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6f33-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6f33-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6f33-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6f33-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6f33-113">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6f33-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6f33-114">See also</span></span>

- [<span data-ttu-id="f6f33-115">ICorDebugILCode2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6f33-115">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)
- [<span data-ttu-id="f6f33-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f6f33-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

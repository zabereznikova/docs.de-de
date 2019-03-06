---
title: ICorDebugFunction::GetLocalVarSigToken-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetLocalVarSigToken
helpviewer_keywords:
- ICorDebugFunction::GetLocalVarSigToken method [.NET Framework debugging]
- GetLocalVarSigToken method [.NET Framework debugging]
ms.assetid: 31e53494-bcc9-4981-91a4-f7e0f02cad48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a682999c888a93cef94162a8179673c862dc43ce
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476645"
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a><span data-ttu-id="e5ca6-102">ICorDebugFunction::GetLocalVarSigToken-Methode</span><span class="sxs-lookup"><span data-stu-id="e5ca6-102">ICorDebugFunction::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="e5ca6-103">Ruft den Metadatentoken für die Signatur der lokalen Variablen der Funktion, die von dieser Instanz ICorDebugFunction dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e5ca6-103">Gets the metadata token for the local variable signature of the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5ca6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5ca6-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5ca6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e5ca6-105">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="e5ca6-106">[out] Ein Zeiger auf die `mdSignature` token für die lokale Variablensignatur dieser Funktion oder `mdSignatureNil`, wenn diese Funktion keine lokalen Variablen enthält.</span><span class="sxs-lookup"><span data-stu-id="e5ca6-106">[out] A pointer to the `mdSignature` token for the local variable signature of this function, or `mdSignatureNil`, if this function has no local variables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5ca6-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e5ca6-107">Requirements</span></span>  
 <span data-ttu-id="e5ca6-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5ca6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5ca6-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5ca6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5ca6-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5ca6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5ca6-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5ca6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

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
ms.openlocfilehash: a923701b05f7d283c4fd464d470fb0c9243c1bd5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213607"
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a><span data-ttu-id="21c0b-102">ICorDebugFunction::GetLocalVarSigToken-Methode</span><span class="sxs-lookup"><span data-stu-id="21c0b-102">ICorDebugFunction::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="21c0b-103">Ruft das Metadatentoken für die Signatur der lokalen Variablen der Funktion ab, die von dieser ICorDebugFunction-Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="21c0b-103">Gets the metadata token for the local variable signature of the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21c0b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="21c0b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21c0b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="21c0b-105">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="21c0b-106">vorgenommen Ein Zeiger auf das `mdSignature` Token für die lokale Variablen Signatur dieser Funktion oder `mdSignatureNil` , wenn diese Funktion über keine lokalen Variablen verfügt.</span><span class="sxs-lookup"><span data-stu-id="21c0b-106">[out] A pointer to the `mdSignature` token for the local variable signature of this function, or `mdSignatureNil`, if this function has no local variables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21c0b-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="21c0b-107">Requirements</span></span>  
 <span data-ttu-id="21c0b-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21c0b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21c0b-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21c0b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21c0b-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21c0b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21c0b-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21c0b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

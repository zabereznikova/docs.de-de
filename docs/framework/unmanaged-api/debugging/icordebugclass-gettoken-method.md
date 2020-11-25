---
title: ICorDebugClass::GetToken-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetToken
helpviewer_keywords:
- GetToken method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetToken method [.NET Framework debugging]
ms.assetid: ee5c848a-eac4-4462-b07a-07ccd76a75df
topic_type:
- apiref
ms.openlocfilehash: 59f450117d1a52ce7b900d9d67330fc98281afa0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728419"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="58cec-102">ICorDebugClass::GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="58cec-102">ICorDebugClass::GetToken Method</span></span>

<span data-ttu-id="58cec-103">Ruft das Metadatentoken ab `TypeDef` , das auf die Definition dieser Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="58cec-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58cec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="58cec-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58cec-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="58cec-105">Parameters</span></span>  

 `pTypeDef`  
 <span data-ttu-id="58cec-106">vorgenommen Ein Zeiger auf ein `mdTypeDef` Token, das auf die Definition dieser Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="58cec-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58cec-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="58cec-107">Requirements</span></span>  

 <span data-ttu-id="58cec-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58cec-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58cec-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58cec-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58cec-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58cec-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58cec-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58cec-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58cec-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="58cec-112">See also</span></span>

- [<span data-ttu-id="58cec-113">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="58cec-113">Metadata Interfaces</span></span>](../metadata/metadata-interfaces.md)

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
ms.openlocfilehash: 3433f5f69927afb501c2596571f138e3a69fabb6
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894123"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="67176-102">ICorDebugClass::GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="67176-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="67176-103">Ruft das `TypeDef` Metadatentoken ab, das auf die Definition dieser Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="67176-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67176-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="67176-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67176-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="67176-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="67176-106">vorgenommen Ein Zeiger auf ein `mdTypeDef` Token, das auf die Definition dieser Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="67176-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67176-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="67176-107">Requirements</span></span>  
 <span data-ttu-id="67176-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67176-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67176-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67176-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67176-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67176-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67176-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67176-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67176-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="67176-112">See also</span></span>

- [<span data-ttu-id="67176-113">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="67176-113">Metadata Interfaces</span></span>](../metadata/metadata-interfaces.md)

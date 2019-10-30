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
ms.openlocfilehash: 6964c931307a40f384ad8a8e355cab0aad575ec6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125774"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="8bbbc-102">ICorDebugClass::GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="8bbbc-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="8bbbc-103">Ruft das `TypeDef` Metadatentoken ab, das auf die Definition dieser Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="8bbbc-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bbbc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8bbbc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bbbc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8bbbc-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="8bbbc-106">vorgenommen Ein Zeiger auf ein `mdTypeDef` Token, das auf die Definition dieser Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="8bbbc-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bbbc-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8bbbc-107">Requirements</span></span>  
 <span data-ttu-id="8bbbc-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bbbc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bbbc-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8bbbc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8bbbc-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bbbc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bbbc-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bbbc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bbbc-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bbbc-112">See also</span></span>

- [<span data-ttu-id="8bbbc-113">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="8bbbc-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)

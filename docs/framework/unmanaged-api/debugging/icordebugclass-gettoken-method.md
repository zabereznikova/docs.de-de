---
title: ICorDebugClass::GetToken-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass.GetToken
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass::GetToken
helpviewer_keywords:
- GetToken method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetToken method [.NET Framework debugging]
ms.assetid: ee5c848a-eac4-4462-b07a-07ccd76a75df
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 805ecd7111fd06dfe0d13f60e6dd1e64ec3c37b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="e748c-102">ICorDebugClass::GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="e748c-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="e748c-103">Ruft die `TypeDef` Metadatentoken, das die Definition dieser Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="e748c-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e748c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e748c-104">Syntax</span></span>  
  
```  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e748c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e748c-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="e748c-106">[out] Ein Zeiger auf ein `mdTypeDef` Token, das die Definition dieser Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="e748c-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e748c-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e748c-107">Requirements</span></span>  
 <span data-ttu-id="e748c-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e748c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e748c-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e748c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e748c-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e748c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e748c-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e748c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e748c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e748c-112">See Also</span></span>  
 [<span data-ttu-id="e748c-113">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e748c-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)

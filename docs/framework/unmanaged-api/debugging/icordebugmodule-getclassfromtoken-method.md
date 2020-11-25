---
title: ICorDebugModule::GetClassFromToken-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetClassFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetClassFromToken
helpviewer_keywords:
- GetClassFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetClassFromToken method [.NET Framework debugging]
ms.assetid: 622a4d3c-0425-4c54-a7e4-0735377cdad2
topic_type:
- apiref
ms.openlocfilehash: 011d763ce244e18c7ba1203e18eb0700a8c8b13a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710232"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="719ad-102">ICorDebugModule::GetClassFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="719ad-102">ICorDebugModule::GetClassFromToken Method</span></span>

<span data-ttu-id="719ad-103">Ruft die vom Metadatentoken angegebene Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="719ad-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="719ad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="719ad-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="719ad-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="719ad-105">Parameters</span></span>  

 `typedef`  
 <span data-ttu-id="719ad-106">in Ein `mdTypeDef` Metadatentoken, das auf die Metadaten einer Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="719ad-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="719ad-107">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugClass-Objekts, das die-Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="719ad-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="719ad-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="719ad-108">Requirements</span></span>  

 <span data-ttu-id="719ad-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="719ad-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="719ad-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="719ad-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="719ad-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="719ad-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="719ad-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="719ad-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

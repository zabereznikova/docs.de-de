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
ms.openlocfilehash: f8a56dcf03748c6582bce07fc379113c5cdddd11
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212597"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="c6182-102">ICorDebugModule::GetClassFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="c6182-102">ICorDebugModule::GetClassFromToken Method</span></span>
<span data-ttu-id="c6182-103">Ruft die vom Metadatentoken angegebene Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="c6182-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6182-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6182-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6182-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c6182-105">Parameters</span></span>  
 `typedef`  
 <span data-ttu-id="c6182-106">in Ein `mdTypeDef` Metadatentoken, das auf die Metadaten einer Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="c6182-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="c6182-107">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugClass-Objekts, das die-Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="c6182-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6182-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c6182-108">Requirements</span></span>  
 <span data-ttu-id="c6182-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6182-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6182-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6182-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6182-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6182-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6182-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6182-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

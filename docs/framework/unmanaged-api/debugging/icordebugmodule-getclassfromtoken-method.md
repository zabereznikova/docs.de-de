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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 413e56a65f4966467f487787172973834ac4a65a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988077"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="d1a4f-102">ICorDebugModule::GetClassFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="d1a4f-102">ICorDebugModule::GetClassFromToken Method</span></span>
<span data-ttu-id="d1a4f-103">Ruft das Metadatentoken angegebene Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="d1a4f-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1a4f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1a4f-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1a4f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d1a4f-105">Parameters</span></span>  
 `typedef`  
 <span data-ttu-id="d1a4f-106">[in] Ein `mdTypeDef` Metadatentoken, das die Metadaten einer Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="d1a4f-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="d1a4f-107">[out] Ein Zeiger auf die Adresse eines ICorDebugClass-Objekts, das die Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="d1a4f-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1a4f-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d1a4f-108">Requirements</span></span>  
 <span data-ttu-id="d1a4f-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1a4f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1a4f-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1a4f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1a4f-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1a4f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1a4f-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1a4f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

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
ms.openlocfilehash: 195cea23313d88b636479147faa512889ca94b17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413971"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="4eb20-102">ICorDebugModule::GetClassFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="4eb20-102">ICorDebugModule::GetClassFromToken Method</span></span>
<span data-ttu-id="4eb20-103">Ruft die Klasse, die durch das Metadatentoken angegeben.</span><span class="sxs-lookup"><span data-stu-id="4eb20-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4eb20-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4eb20-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4eb20-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4eb20-105">Parameters</span></span>  
 `typedef`  
 <span data-ttu-id="4eb20-106">[in] Ein `mdTypeDef` Metadatentoken, das die Metadaten einer Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="4eb20-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="4eb20-107">[out] Ein Zeiger auf die Adresse eines ICorDebugClass-Objekts, das die Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="4eb20-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4eb20-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4eb20-108">Requirements</span></span>  
 <span data-ttu-id="4eb20-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4eb20-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4eb20-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4eb20-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4eb20-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4eb20-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4eb20-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4eb20-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

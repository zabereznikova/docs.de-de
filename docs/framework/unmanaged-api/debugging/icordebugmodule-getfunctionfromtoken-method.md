---
title: ICorDebugModule::GetFunctionFromToken-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetFunctionFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetFunctionFromToken
helpviewer_keywords:
- GetFunctionFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetFunctionFromToken method [.NET Framework debugging]
ms.assetid: 6fe12194-4ef7-43c1-9570-ade35ccf127a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1af0f8f792c856c0b27b4d3d9ff557bcc5fce82
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500069"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a><span data-ttu-id="5ee0e-102">ICorDebugModule::GetFunctionFromToken-Methode</span><span class="sxs-lookup"><span data-stu-id="5ee0e-102">ICorDebugModule::GetFunctionFromToken Method</span></span>
<span data-ttu-id="5ee0e-103">Ruft die Funktion, die durch das Metadatentoken angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5ee0e-103">Gets the function that is specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ee0e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ee0e-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ee0e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5ee0e-105">Parameters</span></span>  
 `methodDef`  
 <span data-ttu-id="5ee0e-106">[in] Ein `mdMethodDef` Metadatentoken, das die Metadaten der Funktion verweist.</span><span class="sxs-lookup"><span data-stu-id="5ee0e-106">[in] A `mdMethodDef` metadata token that references the function's metadata.</span></span>  
  
 `ppFunction`  
 <span data-ttu-id="5ee0e-107">[out] Ein Zeiger auf die Adresse eines Objekts der ICorDebugFunction-Schnittstelle, die die Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="5ee0e-107">[out] A pointer to the address of a ICorDebugFunction interface object that represents the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ee0e-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5ee0e-108">Remarks</span></span>  
 <span data-ttu-id="5ee0e-109">Die `GetFunctionFromToken` Methode gibt ein CORDBG_E_FUNCTION_NOT_IL HRESULT zurück, wenn der Wert übergeben `methodDef` verweist nicht auf eine Methode von Microsoft intermediate Language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="5ee0e-109">The `GetFunctionFromToken` method returns a CORDBG_E_FUNCTION_NOT_IL HRESULT if the value passed in `methodDef` does not refer to a Microsoft intermediate language (MSIL) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ee0e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5ee0e-110">Requirements</span></span>  
 <span data-ttu-id="5ee0e-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ee0e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ee0e-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ee0e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ee0e-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ee0e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ee0e-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ee0e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

---
title: ICorDebugAssembly::GetName-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetName
helpviewer_keywords:
- ICorDebugAssembly::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: cdeda721-b214-4503-a291-c70b68b5f36b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3077e0494816a083d97839d66d06b18130e5dac8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487797"
---
# <a name="icordebugassemblygetname-method"></a><span data-ttu-id="dddf0-102">ICorDebugAssembly::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="dddf0-102">ICorDebugAssembly::GetName Method</span></span>
<span data-ttu-id="dddf0-103">Ruft den Namen der Assembly ab, die dies `ICorDebugAssembly` -Instanz darstellt.</span><span class="sxs-lookup"><span data-stu-id="dddf0-103">Gets the name of the assembly that this `ICorDebugAssembly` instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dddf0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dddf0-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dddf0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dddf0-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="dddf0-106">[in] Die Größe des `szName`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="dddf0-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="dddf0-107">[out] Ein Zeiger auf eine ganze Zahl, die die tatsächliche Länge des Namens angibt.</span><span class="sxs-lookup"><span data-stu-id="dddf0-107">[out] A pointer to an integer that specifies the actual length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="dddf0-108">[out] Ein Array, das den Namen speichert.</span><span class="sxs-lookup"><span data-stu-id="dddf0-108">[out] An array that stores the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dddf0-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dddf0-109">Remarks</span></span>  
 <span data-ttu-id="dddf0-110">Die `GetName` Methode gibt den vollständigen Pfad und Namen der Assembly zurück.</span><span class="sxs-lookup"><span data-stu-id="dddf0-110">The `GetName` method returns the full path and file name of the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dddf0-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dddf0-111">Requirements</span></span>  
 <span data-ttu-id="dddf0-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dddf0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dddf0-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dddf0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dddf0-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dddf0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dddf0-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dddf0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

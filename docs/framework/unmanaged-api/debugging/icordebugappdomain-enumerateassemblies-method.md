---
title: ICorDebugAppDomain::EnumerateAssemblies-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateAssemblies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateAssemblies
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateAssemblies method [.NET Framework debugging]
- EnumerateAssemblies method [.NET Framework debugging]
ms.assetid: 7add64f9-19a8-46a9-be62-905d5e7d1bd8
topic_type:
- apiref
ms.openlocfilehash: 386913f8c81ff3c8b98bb0cab4ffc101a4f6085f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723323"
---
# <a name="icordebugappdomainenumerateassemblies-method"></a><span data-ttu-id="ead2d-102">ICorDebugAppDomain::EnumerateAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="ead2d-102">ICorDebugAppDomain::EnumerateAssemblies Method</span></span>

<span data-ttu-id="ead2d-103">Ruft einen Enumerator für die Assemblys in der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="ead2d-103">Gets an enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ead2d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ead2d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateAssemblies (  
    [out] ICorDebugAssemblyEnum  **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ead2d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ead2d-105">Parameters</span></span>  

 `ppAssemblies`  
 <span data-ttu-id="ead2d-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugAssemblyEnum-Objekts, das der Enumerator für die Assemblys in der Anwendungsdomäne ist.</span><span class="sxs-lookup"><span data-stu-id="ead2d-106">[out] A pointer to the address of an ICorDebugAssemblyEnum object that is the enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ead2d-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ead2d-107">Requirements</span></span>  

 <span data-ttu-id="ead2d-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ead2d-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ead2d-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ead2d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ead2d-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ead2d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ead2d-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ead2d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

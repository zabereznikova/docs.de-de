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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13137dcf7c2edd96397916cc7db905c9e48a3d0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401599"
---
# <a name="icordebugappdomainenumerateassemblies-method"></a><span data-ttu-id="3eefe-102">ICorDebugAppDomain::EnumerateAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="3eefe-102">ICorDebugAppDomain::EnumerateAssemblies Method</span></span>
<span data-ttu-id="3eefe-103">Ruft einen Enumerator für die Assemblys in der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="3eefe-103">Gets an enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eefe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3eefe-104">Syntax</span></span>  
  
```  
HRESULT EnumerateAssemblies (  
    [out] ICorDebugAssemblyEnum  **ppAssemblies  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3eefe-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3eefe-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="3eefe-106">[out] Ein Zeiger auf die Adresse eines ICorDebugAssemblyEnum-Objekts, das den Enumerator für die Assemblys in der Anwendungsdomäne ist.</span><span class="sxs-lookup"><span data-stu-id="3eefe-106">[out] A pointer to the address of an ICorDebugAssemblyEnum object that is the enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3eefe-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3eefe-107">Requirements</span></span>  
 <span data-ttu-id="3eefe-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3eefe-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3eefe-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3eefe-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3eefe-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3eefe-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3eefe-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3eefe-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

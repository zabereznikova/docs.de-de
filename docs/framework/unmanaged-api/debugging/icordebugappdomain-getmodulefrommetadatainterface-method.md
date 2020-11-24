---
title: ICorDebugAppDomain::GetModuleFromMetaDataInterface-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetModuleFromMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetModuleFromMetaDataInterface
helpviewer_keywords:
- ICorDebugAppDomain::GetModuleFromMetaDatainterface method [.NET Framework debugging]
- GetModuleFromMetaDatainterface method [.NET Framework debugging]
ms.assetid: f35225b3-5dda-4d5a-913d-b3373e9ab81e
topic_type:
- apiref
ms.openlocfilehash: 5dede67412711736d269386a20446cf45fab1619
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672200"
---
# <a name="icordebugappdomaingetmodulefrommetadatainterface-method"></a><span data-ttu-id="5fab3-102">ICorDebugAppDomain::GetModuleFromMetaDataInterface-Methode</span><span class="sxs-lookup"><span data-stu-id="5fab3-102">ICorDebugAppDomain::GetModuleFromMetaDataInterface Method</span></span>

<span data-ttu-id="5fab3-103">Ruft das Modul ab, das der angegebenen Metadatenschnittstelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="5fab3-103">Gets the module that corresponds to the given metadata interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fab3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5fab3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromMetaDataInterface (  
    [in] IUnknown           *pIMetaData,  
    [out] ICorDebugModule  **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fab3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5fab3-105">Parameters</span></span>  

 `pIMetaData`  
 <span data-ttu-id="5fab3-106">in Ein Zeiger auf ein Objekt, bei dem es sich um eine der [Metadatenschnittstellen](../metadata/metadata-interfaces.md)handelt.</span><span class="sxs-lookup"><span data-stu-id="5fab3-106">[in] A pointer to an object that is one of the [Metadata interfaces](../metadata/metadata-interfaces.md).</span></span>  
  
 `ppModule`  
 <span data-ttu-id="5fab3-107">vorgenommen Ein Zeiger auf die Adresse eines ICorDebug Module-Objekts, das das Modul darstellt, das der angegebenen Metadatenschnittstelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="5fab3-107">[out] A pointer to the address of an ICorDebugModule object that represents the module corresponding to the given metadata interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fab3-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5fab3-108">Requirements</span></span>  

 <span data-ttu-id="5fab3-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fab3-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fab3-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fab3-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fab3-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fab3-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fab3-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fab3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

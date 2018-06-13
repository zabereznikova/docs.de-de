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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ab9773a5056dbfba422a9a53c7cd877e4c29abe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404598"
---
# <a name="icordebugappdomaingetmodulefrommetadatainterface-method"></a><span data-ttu-id="5db38-102">ICorDebugAppDomain::GetModuleFromMetaDataInterface-Methode</span><span class="sxs-lookup"><span data-stu-id="5db38-102">ICorDebugAppDomain::GetModuleFromMetaDataInterface Method</span></span>
<span data-ttu-id="5db38-103">Ruft das Modul, das die angegebenen Metadaten-Schnittstelle entspricht.</span><span class="sxs-lookup"><span data-stu-id="5db38-103">Gets the module that corresponds to the given metadata interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5db38-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5db38-104">Syntax</span></span>  
  
```  
HRESULT GetModuleFromMetaDataInterface (  
    [in] IUnknown           *pIMetaData,  
    [out] ICorDebugModule  **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5db38-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5db38-105">Parameters</span></span>  
 `pIMetaData`  
 <span data-ttu-id="5db38-106">[in] Ein Zeiger auf ein Objekt, das eines der [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="5db38-106">[in] A pointer to an object that is one of the [Metadata interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span>  
  
 `ppModule`  
 <span data-ttu-id="5db38-107">[out] Ein Zeiger auf die Adresse eines ICorDebugModule-Objekts, das das Modul entspricht, auf die angegebenen Metadaten-Schnittstelle darstellt.</span><span class="sxs-lookup"><span data-stu-id="5db38-107">[out] A pointer to the address of an ICorDebugModule object that represents the module corresponding to the given metadata interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5db38-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5db38-108">Requirements</span></span>  
 <span data-ttu-id="5db38-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5db38-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5db38-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5db38-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5db38-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5db38-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5db38-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5db38-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

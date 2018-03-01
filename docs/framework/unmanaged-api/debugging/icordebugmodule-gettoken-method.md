---
title: ICorDebugModule::GetToken-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugModule.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetToken
helpviewer_keywords:
- ICorDebugModule::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: f759f87a-18ae-4c1a-8300-29b803432d0a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 651612b07a69f0cbcc9c818fe7627bf496f6d68e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="3dd29-102">ICorDebugModule::GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="3dd29-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="3dd29-103">Ruft das Token für den Tabelleneintrag für dieses Modul an.</span><span class="sxs-lookup"><span data-stu-id="3dd29-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dd29-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3dd29-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3dd29-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3dd29-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="3dd29-106">[out] Ein Zeiger auf die `mdModule` Token, das Modul Metadaten verweist.</span><span class="sxs-lookup"><span data-stu-id="3dd29-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3dd29-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3dd29-107">Remarks</span></span>  
 <span data-ttu-id="3dd29-108">Das Token übergeben werden kann, um die [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), und [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstellen zum Importieren von Metadaten.</span><span class="sxs-lookup"><span data-stu-id="3dd29-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dd29-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3dd29-109">Requirements</span></span>  
 <span data-ttu-id="3dd29-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3dd29-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dd29-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3dd29-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3dd29-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3dd29-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3dd29-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dd29-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dd29-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3dd29-114">See Also</span></span>  
 [<span data-ttu-id="3dd29-115">Metadaten</span><span class="sxs-lookup"><span data-stu-id="3dd29-115">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)

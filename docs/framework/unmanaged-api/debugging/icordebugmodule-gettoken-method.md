---
title: ICorDebugModule::GetToken-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f87724bda78c1948ae7e1ddfa3d586fe5b7e14e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575735"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="eb8eb-102">ICorDebugModule::GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="eb8eb-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="eb8eb-103">Ruft das Token für den Tabelleneintrag für dieses Modul ab.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb8eb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb8eb-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb8eb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eb8eb-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="eb8eb-106">[out] Ein Zeiger auf die `mdModule` -Token, die Metadaten des Moduls verweist.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb8eb-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eb8eb-107">Remarks</span></span>  
 <span data-ttu-id="eb8eb-108">Das Token übergeben werden kann, um die [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), und [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstellen zum Importieren von Metadaten.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb8eb-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eb8eb-109">Requirements</span></span>  
 <span data-ttu-id="eb8eb-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb8eb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb8eb-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb8eb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb8eb-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb8eb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb8eb-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb8eb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb8eb-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb8eb-114">See also</span></span>
- [<span data-ttu-id="eb8eb-115">Metadaten</span><span class="sxs-lookup"><span data-stu-id="eb8eb-115">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)

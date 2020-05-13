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
ms.openlocfilehash: a6aff37a480460bfed7064d59b4c5276daf3207c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212502"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="bad11-102">ICorDebugModule::GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="bad11-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="bad11-103">Ruft das Token für den Tabelleneintrag für dieses Modul ab.</span><span class="sxs-lookup"><span data-stu-id="bad11-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bad11-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bad11-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bad11-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bad11-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="bad11-106">vorgenommen Ein Zeiger auf das `mdModule` Token, das auf die Metadaten des Moduls verweist.</span><span class="sxs-lookup"><span data-stu-id="bad11-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bad11-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bad11-107">Remarks</span></span>  
 <span data-ttu-id="bad11-108">Das Token kann an die Metadatenimport-Schnittstellen [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)und [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="bad11-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bad11-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bad11-109">Requirements</span></span>  
 <span data-ttu-id="bad11-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bad11-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bad11-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bad11-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bad11-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bad11-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bad11-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bad11-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bad11-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bad11-114">See also</span></span>

- [<span data-ttu-id="bad11-115">Metadaten</span><span class="sxs-lookup"><span data-stu-id="bad11-115">Metadata</span></span>](../metadata/index.md)

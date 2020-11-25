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
ms.openlocfilehash: 6ffc74247a4ecafcc3744923c0def99220b5ca6f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709881"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="fc97a-102">ICorDebugModule::GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="fc97a-102">ICorDebugModule::GetToken Method</span></span>

<span data-ttu-id="fc97a-103">Ruft das Token für den Tabelleneintrag für dieses Modul ab.</span><span class="sxs-lookup"><span data-stu-id="fc97a-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc97a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc97a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc97a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fc97a-105">Parameters</span></span>  

 `pToken`  
 <span data-ttu-id="fc97a-106">vorgenommen Ein Zeiger auf das `mdModule` Token, das auf die Metadaten des Moduls verweist.</span><span class="sxs-lookup"><span data-stu-id="fc97a-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc97a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fc97a-107">Remarks</span></span>  

 <span data-ttu-id="fc97a-108">Das Token kann an die Metadatenimport-Schnittstellen [IMetaDataImport](../metadata/imetadataimport-interface.md), [IMetaDataImport2](../metadata/imetadataimport2-interface.md)und [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="fc97a-108">The token can be passed to the [IMetaDataImport](../metadata/imetadataimport-interface.md), [IMetaDataImport2](../metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc97a-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fc97a-109">Requirements</span></span>  

 <span data-ttu-id="fc97a-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc97a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc97a-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc97a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc97a-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc97a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc97a-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc97a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc97a-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fc97a-114">See also</span></span>

- [<span data-ttu-id="fc97a-115">Metadaten</span><span class="sxs-lookup"><span data-stu-id="fc97a-115">Metadata</span></span>](../metadata/index.md)

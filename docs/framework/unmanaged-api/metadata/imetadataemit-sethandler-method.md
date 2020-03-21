---
title: IMetaDataEmit::SetHandler-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetHandler
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type:
- apiref
ms.openlocfilehash: 375c4b2cece0bdfd763ae383c5412c9e25614baf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177542"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="2a3f4-102">IMetaDataEmit::SetHandler-Methode</span><span class="sxs-lookup"><span data-stu-id="2a3f4-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="2a3f4-103">Legt die Methode, auf `IUnknown` die der angegebene Zeiger verweist, als Benachrichtigungsrückruf für Tokenneuzuordnungen fest.</span><span class="sxs-lookup"><span data-stu-id="2a3f4-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a3f4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a3f4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a3f4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2a3f4-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="2a3f4-106">[in] Der zu registrierende Handler.</span><span class="sxs-lookup"><span data-stu-id="2a3f4-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a3f4-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2a3f4-107">Remarks</span></span>  
 <span data-ttu-id="2a3f4-108">Das Metadatenmodul sendet Benachrichtigungen mithilfe der `SetHandler`Methode, die von bereitgestellt wird, an Compiler, die keine Datensätze auf optimierte Weise generieren und gespeicherte Datensätze optimieren möchten.</span><span class="sxs-lookup"><span data-stu-id="2a3f4-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="2a3f4-109">Wenn die Rückrufmethode nicht `SetHandler`über bereitgestellt wird, wird beim Speichern keine Optimierung durchgeführt, es sei denn, mehrere Importbereiche wurden zusammengeführt, indem `IMapToken` bei Merge für jeden Bereich verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="2a3f4-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a3f4-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2a3f4-110">Requirements</span></span>  
 <span data-ttu-id="2a3f4-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a3f4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a3f4-112">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2a3f4-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a3f4-113">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="2a3f4-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a3f4-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a3f4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a3f4-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2a3f4-115">See also</span></span>

- [<span data-ttu-id="2a3f4-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2a3f4-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2a3f4-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2a3f4-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

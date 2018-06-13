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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 60c9266806ef6b5d7e2e1c3a219a4485bc22d7f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445519"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="0bdc1-102">IMetaDataEmit::SetHandler-Methode</span><span class="sxs-lookup"><span data-stu-id="0bdc1-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="0bdc1-103">Legt die Methode, die auf die verwiesen wird durch das angegebene `IUnknown` Zeiger als eines Rückrufs für token neue Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="0bdc1-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bdc1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0bdc1-104">Syntax</span></span>  
  
```  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0bdc1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0bdc1-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="0bdc1-106">[in] Der Handler registriert.</span><span class="sxs-lookup"><span data-stu-id="0bdc1-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bdc1-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0bdc1-107">Remarks</span></span>  
 <span data-ttu-id="0bdc1-108">Das Metadatenmodul sendet Benachrichtigung mithilfe der Methode, die von bereitgestellte `SetHandler`, Compiler, die Datensätze nicht auf optimierte Weise generieren und die gespeicherte Datensätze optimieren möchten.</span><span class="sxs-lookup"><span data-stu-id="0bdc1-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="0bdc1-109">Wenn die Rückrufmethode nicht über die bereitgestellten `SetHandler`, keine Optimierung erfolgt auf speichern es sei denn, in denen mehrere importtypen Bereiche zusammengeführt wurden mit `IMapToken` auf "Zusammenführen" für die einzelnen Bereiche.</span><span class="sxs-lookup"><span data-stu-id="0bdc1-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bdc1-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0bdc1-110">Requirements</span></span>  
 <span data-ttu-id="0bdc1-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bdc1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bdc1-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0bdc1-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0bdc1-113">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="0bdc1-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0bdc1-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bdc1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bdc1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0bdc1-115">See Also</span></span>  
 [<span data-ttu-id="0bdc1-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0bdc1-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="0bdc1-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0bdc1-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)

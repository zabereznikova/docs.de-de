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
ms.openlocfilehash: 9b03dc5460875af3bb3e5e20799a4d26eb74da05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730369"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="f809a-102">IMetaDataEmit::SetHandler-Methode</span><span class="sxs-lookup"><span data-stu-id="f809a-102">IMetaDataEmit::SetHandler Method</span></span>

<span data-ttu-id="f809a-103">Legt die Methode, auf die der angegebene Zeiger verweist, `IUnknown` als Benachrichtigungs Rückruf für die Tokenneuzuordnung fest.</span><span class="sxs-lookup"><span data-stu-id="f809a-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f809a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f809a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f809a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f809a-105">Parameters</span></span>  

 `pUnk`  
 <span data-ttu-id="f809a-106">in Der zu Registrier gende Handler.</span><span class="sxs-lookup"><span data-stu-id="f809a-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f809a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f809a-107">Remarks</span></span>  

 <span data-ttu-id="f809a-108">Die metadatenengine sendet mithilfe der von bereitgestellten Methode eine Benachrichtigung `SetHandler` an Compiler, die keine Datensätze auf optimierte Weise generieren und gespeicherte Datensätze optimieren möchten.</span><span class="sxs-lookup"><span data-stu-id="f809a-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="f809a-109">Wenn die Rückruf Methode nicht mithilfe von bereitgestellt wird `SetHandler` , wird beim Speichern nur dann eine Optimierung durchgeführt, wenn mehrere Import Bereiche mithilfe `IMapToken` von bei Merge für jeden Bereich zusammengeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="f809a-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f809a-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f809a-110">Requirements</span></span>  

 <span data-ttu-id="f809a-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f809a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f809a-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f809a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f809a-113">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="f809a-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f809a-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f809a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f809a-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f809a-115">See also</span></span>

- [<span data-ttu-id="f809a-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f809a-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="f809a-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f809a-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

---
title: IMapToken::Map-Methode
ms.date: 03/30/2017
api_name:
- IMapToken.Map
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f2633bfadaabf208a2b86fda83375c3a136b93b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448171"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="c2dc6-102">IMapToken::Map-Methode</span><span class="sxs-lookup"><span data-stu-id="c2dc6-102">IMapToken::Map Method</span></span>
<span data-ttu-id="c2dc6-103">Ordnet eine Beziehung zwischen den Assemblys, die mithilfe von Metadatensignaturen an.</span><span class="sxs-lookup"><span data-stu-id="c2dc6-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2dc6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2dc6-104">Syntax</span></span>  
  
```  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2dc6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c2dc6-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="c2dc6-106">[in] Das Metadatentoken, das das importierte Codeobjekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="c2dc6-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="c2dc6-107">[in] Das Metadatentoken, das das Objekt der ausgegebene Code darstellt.</span><span class="sxs-lookup"><span data-stu-id="c2dc6-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2dc6-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c2dc6-108">Remarks</span></span>  
 <span data-ttu-id="c2dc6-109">Wenn das token erneut zuordnen während eines Merge auftritt, das ursprüngliche Token im Metadatenbereich importierten (Quelle) beschränkt, und das neue Token wird im Metadatenbereich ausgegebenen (Ziel) bewertet.</span><span class="sxs-lookup"><span data-stu-id="c2dc6-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2dc6-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c2dc6-110">Requirements</span></span>  
 <span data-ttu-id="c2dc6-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2dc6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2dc6-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c2dc6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2dc6-113">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="c2dc6-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c2dc6-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2dc6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2dc6-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2dc6-115">See Also</span></span>  
 [<span data-ttu-id="c2dc6-116">IMapToken-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2dc6-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)

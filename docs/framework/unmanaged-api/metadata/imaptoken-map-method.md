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
ms.openlocfilehash: 8ac12d5b6bc2911e3bd879285a9a12f65c426f0d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745859"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="5a088-102">IMapToken::Map-Methode</span><span class="sxs-lookup"><span data-stu-id="5a088-102">IMapToken::Map Method</span></span>
<span data-ttu-id="5a088-103">Ordnet eine Beziehung zwischen den Signaturen von Metadaten mit Assemblys.</span><span class="sxs-lookup"><span data-stu-id="5a088-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a088-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a088-104">Syntax</span></span>  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a088-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5a088-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="5a088-106">[in] Das Metadatentoken, das das importierte Codeobjekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="5a088-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="5a088-107">[in] Das Metadatentoken, das ausgegebene Code darstellt.</span><span class="sxs-lookup"><span data-stu-id="5a088-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a088-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5a088-108">Remarks</span></span>  
 <span data-ttu-id="5a088-109">Wenn das token neu zuordnen während eines Merge auftritt, bezieht sich das ursprüngliche Token im Metadatenbereich importiert (Quelle) und das neue Token im Metadatenbereich ausgegeben (Ziel) ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="5a088-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a088-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5a088-110">Requirements</span></span>  
 <span data-ttu-id="5a088-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a088-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a088-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5a088-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5a088-113">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="5a088-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5a088-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a088-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a088-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a088-115">See also</span></span>

- [<span data-ttu-id="5a088-116">IMapToken-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5a088-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)

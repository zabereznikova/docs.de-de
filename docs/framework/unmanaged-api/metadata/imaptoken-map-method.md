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
ms.openlocfilehash: 428b022ed560648f59798154d5987d382938c280
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176070"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="fe8cd-102">IMapToken::Map-Methode</span><span class="sxs-lookup"><span data-stu-id="fe8cd-102">IMapToken::Map Method</span></span>
<span data-ttu-id="fe8cd-103">Ordnet eine Beziehung zwischen den Assemblys mithilfe von Metadatensignaturen zu.</span><span class="sxs-lookup"><span data-stu-id="fe8cd-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe8cd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe8cd-104">Syntax</span></span>  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe8cd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fe8cd-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="fe8cd-106">[in] Das Metadatentoken, das das importierte Codeobjekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="fe8cd-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="fe8cd-107">[in] Das Metadatentoken, das das emittierte Codeobjekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="fe8cd-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe8cd-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fe8cd-108">Remarks</span></span>  
 <span data-ttu-id="fe8cd-109">Wenn die Neuzuordnung des Tokens während einer Zusammenführung auftritt, wird das ursprüngliche Token im importierten (Quell-)Metadatenbereich und das neue Token im emittierten (Ziel-)Metadatenbereich bereichiert.</span><span class="sxs-lookup"><span data-stu-id="fe8cd-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe8cd-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fe8cd-110">Requirements</span></span>  
 <span data-ttu-id="fe8cd-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe8cd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe8cd-112">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fe8cd-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe8cd-113">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="fe8cd-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fe8cd-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe8cd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe8cd-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fe8cd-115">See also</span></span>

- [<span data-ttu-id="fe8cd-116">IMapToken-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fe8cd-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)

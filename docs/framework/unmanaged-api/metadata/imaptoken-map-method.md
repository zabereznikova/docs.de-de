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
ms.openlocfilehash: 51cca1ab61027090b0d22781dfd740038bc9372d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718201"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="13b86-102">IMapToken::Map-Methode</span><span class="sxs-lookup"><span data-stu-id="13b86-102">IMapToken::Map Method</span></span>

<span data-ttu-id="13b86-103">Ordnet mithilfe von Metadatensignaturen eine Beziehung zwischen den Assemblys zu.</span><span class="sxs-lookup"><span data-stu-id="13b86-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13b86-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="13b86-104">Syntax</span></span>  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13b86-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="13b86-105">Parameters</span></span>  

 `tkImp`  
 <span data-ttu-id="13b86-106">in Das Metadatentoken, das das importierte Code Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="13b86-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="13b86-107">in Das Metadatentoken, das das ausgegebene Code Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="13b86-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13b86-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="13b86-108">Remarks</span></span>  

 <span data-ttu-id="13b86-109">Wenn die erneute Zuordnung des Tokens während einer Zusammenführung auftritt, wird das ursprüngliche Token in den importierten (Quell-) Metadatenbereich festgelegt, und das neue Token wird im ausgegebenen (Ziel-) Metadatenbereich festgelegt.</span><span class="sxs-lookup"><span data-stu-id="13b86-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13b86-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="13b86-110">Requirements</span></span>  

 <span data-ttu-id="13b86-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13b86-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13b86-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="13b86-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13b86-113">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="13b86-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13b86-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13b86-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13b86-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="13b86-115">See also</span></span>

- [<span data-ttu-id="13b86-116">IMapToken-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13b86-116">IMapToken Interface</span></span>](imaptoken-interface.md)

---
title: ICeeGen::GetMethodBuffer-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.GetMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetMethodBuffer
helpviewer_keywords:
- ICeeGen::GetMethodBuffer method [.NET Framework metadata]
- GetMethodBuffer method [.NET Framework metadata]
ms.assetid: c7c5b39a-d4ac-41f1-9d1e-44163f563a49
topic_type:
- apiref
ms.openlocfilehash: 8c8ecab9d957e72bb6c0817af07c863fcff97cde
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436328"
---
# <a name="iceegengetmethodbuffer-method"></a><span data-ttu-id="0c05a-102">ICeeGen::GetMethodBuffer-Methode</span><span class="sxs-lookup"><span data-stu-id="0c05a-102">ICeeGen::GetMethodBuffer Method</span></span>
<span data-ttu-id="0c05a-103">Ruft einen Puffer der entsprechenden Größe für die Methode an der angegebenen relativen virtuellen Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="0c05a-103">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="0c05a-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0c05a-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c05a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c05a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodBuffer (  
    [in]  ULONG       RVA,  
    [out] UCHAR       **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c05a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0c05a-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="0c05a-107">in Die relative virtuelle Adresse der Methode, für die ein Puffer zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c05a-107">[in] The relative virtual address of the method for which to return a buffer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="0c05a-108">vorgenommen Ein Zeiger auf den zurückgegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="0c05a-108">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c05a-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0c05a-109">Requirements</span></span>  
 <span data-ttu-id="0c05a-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c05a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c05a-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0c05a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c05a-112">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="0c05a-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0c05a-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c05a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c05a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c05a-114">See also</span></span>

- [<span data-ttu-id="0c05a-115">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0c05a-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

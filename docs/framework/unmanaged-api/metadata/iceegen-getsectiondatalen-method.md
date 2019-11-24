---
title: ICeeGen::GetSectionDataLen-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionDataLen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionDataLen
helpviewer_keywords:
- ICeeGen::GetSectionDataLen method [.NET Framework metadata]
- GetSectionDataLen method [.NET Framework metadata]
ms.assetid: e2a06ee4-b8ee-49c7-935a-c1031a29eef2
topic_type:
- apiref
ms.openlocfilehash: 277e2584049fae397cf91281a65d05b0b49d9454
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448086"
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="9b676-102">ICeeGen::GetSectionDataLen-Methode</span><span class="sxs-lookup"><span data-stu-id="9b676-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="9b676-103">Gets the length of the specified section.</span><span class="sxs-lookup"><span data-stu-id="9b676-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="9b676-104">This method is obsolete and should not be used.</span><span class="sxs-lookup"><span data-stu-id="9b676-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b676-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b676-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b676-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b676-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="9b676-107">[in] The data section whose length will be retrieved.</span><span class="sxs-lookup"><span data-stu-id="9b676-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="9b676-108">[out] The returned length of the specified section.</span><span class="sxs-lookup"><span data-stu-id="9b676-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b676-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b676-109">Remarks</span></span>  
 <span data-ttu-id="9b676-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span><span class="sxs-lookup"><span data-stu-id="9b676-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b676-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b676-111">Requirements</span></span>  
 <span data-ttu-id="9b676-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b676-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b676-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9b676-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9b676-114">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9b676-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9b676-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b676-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b676-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b676-116">See also</span></span>

- [<span data-ttu-id="9b676-117">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b676-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

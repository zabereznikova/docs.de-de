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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ca01f78cf46d4f7543b949c820eb6b1971687e23
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905475"
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="65382-102">ICeeGen::GetSectionDataLen-Methode</span><span class="sxs-lookup"><span data-stu-id="65382-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="65382-103">Ruft die Länge des angegebenen Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="65382-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="65382-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="65382-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65382-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="65382-105">Syntax</span></span>  
  
```  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65382-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="65382-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="65382-107">[in] Der Datenabschnitt, deren Länge abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="65382-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="65382-108">[out] Die zurückgegebene Länge des angegebenen Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="65382-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65382-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="65382-109">Remarks</span></span>  
 <span data-ttu-id="65382-110">Rufen Sie `GetSectionDataLen` nur dann, wenn Sie Anforderungen an die speziellen Bereich verfügen, die nicht von anderen Methoden behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="65382-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65382-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="65382-111">Requirements</span></span>  
 <span data-ttu-id="65382-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65382-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65382-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="65382-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="65382-114">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="65382-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="65382-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65382-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65382-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65382-116">See also</span></span>

- [<span data-ttu-id="65382-117">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65382-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

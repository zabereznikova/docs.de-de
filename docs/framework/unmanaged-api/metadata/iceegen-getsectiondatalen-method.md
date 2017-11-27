---
title: ICeeGen::GetSectionDataLen-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.GetSectionDataLen
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::GetSectionDataLen
helpviewer_keywords:
- ICeeGen::GetSectionDataLen method [.NET Framework metadata]
- GetSectionDataLen method [.NET Framework metadata]
ms.assetid: e2a06ee4-b8ee-49c7-935a-c1031a29eef2
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7d119fdfe5c0202d08ca78026a6917bb4ef51422
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="1d6bf-102">ICeeGen::GetSectionDataLen-Methode</span><span class="sxs-lookup"><span data-stu-id="1d6bf-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="1d6bf-103">Ruft die Länge des angegebenen Abschnitts ab.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="1d6bf-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d6bf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d6bf-105">Syntax</span></span>  
  
```  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d6bf-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1d6bf-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="1d6bf-107">[in] Der Datenabschnitt, deren Länge abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="1d6bf-108">[out] Die zurückgegebene Länge des angegebenen Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d6bf-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1d6bf-109">Remarks</span></span>  
 <span data-ttu-id="1d6bf-110">Rufen Sie `GetSectionDataLen` nur bei besonderen Anforderungen, die nicht von anderen Methoden behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="1d6bf-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d6bf-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1d6bf-111">Requirements</span></span>  
 <span data-ttu-id="1d6bf-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d6bf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d6bf-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1d6bf-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1d6bf-114">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="1d6bf-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1d6bf-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d6bf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d6bf-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d6bf-116">See Also</span></span>  
 [<span data-ttu-id="1d6bf-117">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d6bf-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

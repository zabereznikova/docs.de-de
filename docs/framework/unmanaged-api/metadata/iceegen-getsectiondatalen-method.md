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
ms.openlocfilehash: b45b0a59a29a27e7b0a395f3928215959450f9a5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698467"
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="a22c7-102">ICeeGen::GetSectionDataLen-Methode</span><span class="sxs-lookup"><span data-stu-id="a22c7-102">ICeeGen::GetSectionDataLen Method</span></span>

<span data-ttu-id="a22c7-103">Ruft die Länge des angegebenen Abschnitts ab.</span><span class="sxs-lookup"><span data-stu-id="a22c7-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="a22c7-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a22c7-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a22c7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a22c7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a22c7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a22c7-106">Parameters</span></span>  

 `section`  
 <span data-ttu-id="a22c7-107">in Der Daten Abschnitt, dessen Länge abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a22c7-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="a22c7-108">vorgenommen Die zurückgegebene Länge des angegebenen Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="a22c7-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a22c7-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a22c7-109">Remarks</span></span>  

 <span data-ttu-id="a22c7-110">`GetSectionDataLen`Wird nur aufgerufen, wenn Sie besondere Abschnitts Anforderungen haben, die nicht von anderen Methoden behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="a22c7-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a22c7-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a22c7-111">Requirements</span></span>  

 <span data-ttu-id="a22c7-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a22c7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a22c7-113">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a22c7-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a22c7-114">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="a22c7-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a22c7-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a22c7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a22c7-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a22c7-116">See also</span></span>

- [<span data-ttu-id="a22c7-117">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a22c7-117">ICeeGen Interface</span></span>](iceegen-interface.md)

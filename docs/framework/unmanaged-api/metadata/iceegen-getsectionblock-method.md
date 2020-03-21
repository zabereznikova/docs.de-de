---
title: ICeeGen::GetSectionBlock-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
ms.openlocfilehash: a494b1aaa762549528e92ab93d18929ef73eb8da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176083"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="36ced-102">ICeeGen::GetSectionBlock-Methode</span><span class="sxs-lookup"><span data-stu-id="36ced-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="36ced-103">Ruft einen Abschnittsblock der Codebasis ab.</span><span class="sxs-lookup"><span data-stu-id="36ced-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="36ced-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="36ced-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36ced-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="36ced-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="36ced-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="36ced-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="36ced-107">[in] Der Abschnitt, aus dem ein Block der Codebasis abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="36ced-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="36ced-108">[in] Die Länge des abrufbaren Blocks.</span><span class="sxs-lookup"><span data-stu-id="36ced-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="36ced-109">[in] Das Byte relativ zum Anfang des Abschnitts, mit dem das erste Byte des Blocks ausgerichtet werden soll.</span><span class="sxs-lookup"><span data-stu-id="36ced-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="36ced-110">Dies ist die Position des Blocks innerhalb des Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="36ced-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="36ced-111">[out] Ein Zeiger auf eine Position, die die Adresse des abgerufenen Blocks empfängt.</span><span class="sxs-lookup"><span data-stu-id="36ced-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36ced-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="36ced-112">Remarks</span></span>  
 <span data-ttu-id="36ced-113">Rufen `GetSectionBlock` Sie nur an, wenn Sie spezielle Abschnittsanforderungen haben, die nicht von anderen Methoden verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="36ced-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36ced-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="36ced-114">Requirements</span></span>  
 <span data-ttu-id="36ced-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36ced-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36ced-116">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="36ced-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="36ced-117">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="36ced-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="36ced-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36ced-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36ced-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="36ced-119">See also</span></span>

- [<span data-ttu-id="36ced-120">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="36ced-120">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

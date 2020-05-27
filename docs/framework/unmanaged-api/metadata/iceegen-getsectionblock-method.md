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
ms.openlocfilehash: ed534890fc90d3b8543a1166c85903f10163f0a8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008321"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="8ddef-102">ICeeGen::GetSectionBlock-Methode</span><span class="sxs-lookup"><span data-stu-id="8ddef-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="8ddef-103">Ruft einen Abschnitts Block der Codebasis ab.</span><span class="sxs-lookup"><span data-stu-id="8ddef-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="8ddef-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8ddef-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ddef-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ddef-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="8ddef-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8ddef-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="8ddef-107">in Der Abschnitt, aus dem ein Block der Codebasis abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8ddef-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="8ddef-108">in Die Länge des abzurufenden Blocks.</span><span class="sxs-lookup"><span data-stu-id="8ddef-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="8ddef-109">in Das Byte relativ zum Anfang des Abschnitts, mit dem das erste Byte des Blocks ausgerichtet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8ddef-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="8ddef-110">Dies ist die Position des-Blocks innerhalb des-Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="8ddef-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="8ddef-111">vorgenommen Ein Zeiger auf einen Speicherort, der die Adresse des abgerufenen Blocks empfängt.</span><span class="sxs-lookup"><span data-stu-id="8ddef-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ddef-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8ddef-112">Remarks</span></span>  
 <span data-ttu-id="8ddef-113">`GetSectionBlock`Wird nur aufgerufen, wenn Sie besondere Abschnitts Anforderungen haben, die nicht von anderen Methoden behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="8ddef-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ddef-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8ddef-114">Requirements</span></span>  
 <span data-ttu-id="8ddef-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ddef-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ddef-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8ddef-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ddef-117">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="8ddef-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8ddef-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ddef-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ddef-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ddef-119">See also</span></span>

- [<span data-ttu-id="8ddef-120">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ddef-120">ICeeGen Interface</span></span>](iceegen-interface.md)

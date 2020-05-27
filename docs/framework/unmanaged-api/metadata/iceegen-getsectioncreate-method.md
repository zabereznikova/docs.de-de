---
title: ICeeGen::GetSectionCreate-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionCreate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type:
- apiref
ms.openlocfilehash: 0cf7b15392c90694db659f6faff6feecbef65466
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008329"
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="739d4-102">ICeeGen::GetSectionCreate-Methode</span><span class="sxs-lookup"><span data-stu-id="739d4-102">ICeeGen::GetSectionCreate Method</span></span>
<span data-ttu-id="739d4-103">Generiert einen Code Abschnitt unter Verwendung des angegebenen Namens und der Flagwerte und ruft diesen ab.</span><span class="sxs-lookup"><span data-stu-id="739d4-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="739d4-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="739d4-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="739d4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="739d4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="739d4-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="739d4-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="739d4-107">in Ein Zeiger auf eine Zeichenfolge, die den Namen des zu erstellenden Abschnitts angibt.</span><span class="sxs-lookup"><span data-stu-id="739d4-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="739d4-108">in Flags, die Optionen angeben.</span><span class="sxs-lookup"><span data-stu-id="739d4-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="739d4-109">vorgenommen Ein Zeiger auf den neu erstellten Code Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="739d4-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="739d4-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="739d4-110">Remarks</span></span>  
 <span data-ttu-id="739d4-111">`GetSectionCreate`Wird nur aufgerufen, wenn Sie besondere Abschnitts Anforderungen haben, die nicht von anderen Methoden behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="739d4-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="739d4-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="739d4-112">Requirements</span></span>  
 <span data-ttu-id="739d4-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="739d4-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="739d4-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="739d4-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="739d4-115">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="739d4-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="739d4-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="739d4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="739d4-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="739d4-117">See also</span></span>

- [<span data-ttu-id="739d4-118">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="739d4-118">ICeeGen Interface</span></span>](iceegen-interface.md)

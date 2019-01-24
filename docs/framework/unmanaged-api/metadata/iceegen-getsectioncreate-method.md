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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 93e96e7804a3b5ecc64e9e50ce700435be83b77a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643363"
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="4a644-102">ICeeGen::GetSectionCreate-Methode</span><span class="sxs-lookup"><span data-stu-id="4a644-102">ICeeGen::GetSectionCreate Method</span></span>
<span data-ttu-id="4a644-103">Wird generiert, und ruft einen Codeabschnitt, der mit dem angegebenen Namen und der Flagwerte.</span><span class="sxs-lookup"><span data-stu-id="4a644-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="4a644-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4a644-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a644-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a644-105">Syntax</span></span>  
  
```  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a644-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4a644-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="4a644-107">[in] Ein Zeiger auf eine Zeichenfolge, die den Namen des zu erstellenden Abschnitts angibt.</span><span class="sxs-lookup"><span data-stu-id="4a644-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="4a644-108">[in] Flags, die Optionen angeben.</span><span class="sxs-lookup"><span data-stu-id="4a644-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="4a644-109">[out] Ein Zeiger auf die im Abschnitt neu erstellten Code.</span><span class="sxs-lookup"><span data-stu-id="4a644-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a644-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4a644-110">Remarks</span></span>  
 <span data-ttu-id="4a644-111">Rufen Sie `GetSectionCreate` nur dann, wenn Sie Anforderungen an die speziellen Bereich verfügen, die nicht von anderen Methoden behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="4a644-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a644-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4a644-112">Requirements</span></span>  
 <span data-ttu-id="4a644-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a644-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a644-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4a644-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4a644-115">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="4a644-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4a644-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a644-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a644-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a644-117">See also</span></span>
- [<span data-ttu-id="4a644-118">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4a644-118">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

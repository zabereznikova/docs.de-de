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
ms.openlocfilehash: 4ef3992d840f539ca07c411c2d740fa32b14edbc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722946"
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="a4737-102">ICeeGen::GetSectionCreate-Methode</span><span class="sxs-lookup"><span data-stu-id="a4737-102">ICeeGen::GetSectionCreate Method</span></span>

<span data-ttu-id="a4737-103">Generiert einen Code Abschnitt unter Verwendung des angegebenen Namens und der Flagwerte und ruft diesen ab.</span><span class="sxs-lookup"><span data-stu-id="a4737-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="a4737-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4737-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4737-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4737-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4737-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a4737-106">Parameters</span></span>  

 `name`  
 <span data-ttu-id="a4737-107">in Ein Zeiger auf eine Zeichenfolge, die den Namen des zu erstellenden Abschnitts angibt.</span><span class="sxs-lookup"><span data-stu-id="a4737-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="a4737-108">in Flags, die Optionen angeben.</span><span class="sxs-lookup"><span data-stu-id="a4737-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="a4737-109">vorgenommen Ein Zeiger auf den neu erstellten Code Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a4737-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4737-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a4737-110">Remarks</span></span>  

 <span data-ttu-id="a4737-111">`GetSectionCreate`Wird nur aufgerufen, wenn Sie besondere Abschnitts Anforderungen haben, die nicht von anderen Methoden behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="a4737-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4737-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a4737-112">Requirements</span></span>  

 <span data-ttu-id="a4737-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4737-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4737-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a4737-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a4737-115">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="a4737-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a4737-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4737-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4737-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a4737-117">See also</span></span>

- [<span data-ttu-id="a4737-118">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a4737-118">ICeeGen Interface</span></span>](iceegen-interface.md)

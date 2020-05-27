---
title: ICeeGen::GetIlSection-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.GetIlSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetIlSection
helpviewer_keywords:
- GetIlSection method [.NET Framework metadata]
- ICeeGen::GetIlSection method [.NET Framework metadata]
ms.assetid: 6f2db2ca-203f-4ac3-9530-208642ca385e
topic_type:
- apiref
ms.openlocfilehash: 05f39befa8966046cd71db82da37c44f20992cff
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008806"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="0fb0f-102">ICeeGen::GetIlSection-Methode</span><span class="sxs-lookup"><span data-stu-id="0fb0f-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="0fb0f-103">Ruft den Abschnitt der zwischen Sprachen-Codebasis ab, auf die vom angegebenen Handle verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="0fb0f-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="0fb0f-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0fb0f-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fb0f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0fb0f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fb0f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0fb0f-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="0fb0f-107">in Das Handle des abzuzurufden Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="0fb0f-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fb0f-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0fb0f-108">Requirements</span></span>  
 <span data-ttu-id="0fb0f-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fb0f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fb0f-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0fb0f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0fb0f-111">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="0fb0f-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0fb0f-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fb0f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fb0f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0fb0f-113">See also</span></span>

- [<span data-ttu-id="0fb0f-114">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0fb0f-114">ICeeGen Interface</span></span>](iceegen-interface.md)

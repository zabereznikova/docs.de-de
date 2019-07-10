---
title: ICeeGen::GetStringSection-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.GetStringSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetStringSection
helpviewer_keywords:
- ICeeGen::GetStringSection method [.NET Framework metadata]
- GetStringSection method [.NET Framework metadata]
ms.assetid: a2267d39-69d1-4de1-bf37-f752cafacc71
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 68dc80c657c3794a416f6e142f70cfb05bee2c77
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745896"
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="15b54-102">ICeeGen::GetStringSection-Methode</span><span class="sxs-lookup"><span data-stu-id="15b54-102">ICeeGen::GetStringSection Method</span></span>
<span data-ttu-id="15b54-103">Ruft eine Zeichenfolgendarstellung der Codeabschnitt, der auf die verwiesen wird durch das angegebene Handle ab.</span><span class="sxs-lookup"><span data-stu-id="15b54-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="15b54-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="15b54-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15b54-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="15b54-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15b54-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="15b54-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="15b54-107">[in, out] Das Handle für den Codeabschnitt.</span><span class="sxs-lookup"><span data-stu-id="15b54-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15b54-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="15b54-108">Requirements</span></span>  
 <span data-ttu-id="15b54-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15b54-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15b54-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="15b54-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="15b54-111">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="15b54-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="15b54-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15b54-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15b54-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15b54-113">See also</span></span>

- [<span data-ttu-id="15b54-114">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15b54-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

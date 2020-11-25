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
ms.openlocfilehash: bd284bced625de39791377a9248796ca3dd76f5c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722920"
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="1801a-102">ICeeGen::GetStringSection-Methode</span><span class="sxs-lookup"><span data-stu-id="1801a-102">ICeeGen::GetStringSection Method</span></span>

<span data-ttu-id="1801a-103">Ruft eine Zeichen folgen Darstellung des Code Abschnitts ab, auf den vom angegebenen Handle verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1801a-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="1801a-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1801a-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1801a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1801a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1801a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1801a-106">Parameters</span></span>  

 `section`  
 <span data-ttu-id="1801a-107">[in, out] Das Handle für den Code Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="1801a-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1801a-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1801a-108">Requirements</span></span>  

 <span data-ttu-id="1801a-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1801a-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1801a-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1801a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1801a-111">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="1801a-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1801a-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1801a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1801a-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1801a-113">See also</span></span>

- [<span data-ttu-id="1801a-114">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1801a-114">ICeeGen Interface</span></span>](iceegen-interface.md)

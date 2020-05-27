---
title: ICeeGen::GetString-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
ms.openlocfilehash: b7b15261d825c1bd5f217c4cecd82ed36a716d0e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008260"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="fd0af-102">ICeeGen::GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="fd0af-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="fd0af-103">Ruft die Zeichenfolge ab, die bei der angegebenen relativen virtuellen Adresse gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="fd0af-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="fd0af-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fd0af-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd0af-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd0af-105">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in]  ULONG      RVA,
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd0af-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="fd0af-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="fd0af-107">in Die relative virtuelle Adresse der zurück zugebende Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="fd0af-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="fd0af-108">vorgenommen Die zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="fd0af-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd0af-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fd0af-109">Requirements</span></span>  
 <span data-ttu-id="fd0af-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd0af-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd0af-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fd0af-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fd0af-112">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd0af-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fd0af-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd0af-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd0af-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd0af-114">See also</span></span>

- [<span data-ttu-id="fd0af-115">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd0af-115">ICeeGen Interface</span></span>](iceegen-interface.md)

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
ms.openlocfilehash: c4ccbff4a4967e7525ee4e51650a4f53e5458666
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605517"
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="9b36e-102">ICeeGen::GetStringSection-Methode</span><span class="sxs-lookup"><span data-stu-id="9b36e-102">ICeeGen::GetStringSection Method</span></span>
<span data-ttu-id="9b36e-103">Ruft eine Zeichenfolgendarstellung der Codeabschnitt, der auf die verwiesen wird durch das angegebene Handle ab.</span><span class="sxs-lookup"><span data-stu-id="9b36e-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="9b36e-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9b36e-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b36e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b36e-105">Syntax</span></span>  
  
```  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b36e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b36e-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="9b36e-107">[in, out] Das Handle für den Codeabschnitt.</span><span class="sxs-lookup"><span data-stu-id="9b36e-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b36e-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b36e-108">Requirements</span></span>  
 <span data-ttu-id="9b36e-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b36e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b36e-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9b36e-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9b36e-111">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="9b36e-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9b36e-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b36e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b36e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b36e-113">See also</span></span>
- [<span data-ttu-id="9b36e-114">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b36e-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

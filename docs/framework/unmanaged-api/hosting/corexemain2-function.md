---
title: _CorExeMain2-Funktion
ms.date: 03/30/2017
api_name:
- _CorExeMain2
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain2
helpviewer_keywords:
- _CorExeMain2 function [.NET Framework hosting]
ms.assetid: 72ea68b4-689f-4733-9416-9664b75e8892
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f968d84ae695eb1da127538ebdc5e4f55d6ebf39
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183156"
---
# <a name="corexemain2-function"></a><span data-ttu-id="b7e15-102">_CorExeMain2-Funktion</span><span class="sxs-lookup"><span data-stu-id="b7e15-102">_CorExeMain2 Function</span></span>
<span data-ttu-id="b7e15-103">Führt den Einstiegspunkt im angegebenen Speicherabbildcode aus.</span><span class="sxs-lookup"><span data-stu-id="b7e15-103">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="b7e15-104">Diese Funktion wird vom Betriebssystemladeprogramm aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b7e15-104">This function is called by the operating system loader.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7e15-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7e15-105">Syntax</span></span>  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7e15-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b7e15-106">Parameters</span></span>  
 `pUnmappedPE`  
 <span data-ttu-id="b7e15-107">[in] Ein Zeiger auf den Speicher abgebildeten Code.</span><span class="sxs-lookup"><span data-stu-id="b7e15-107">[in] A pointer to the memory-mapped code.</span></span>  
  
 `cUnmappedPE`  
 <span data-ttu-id="b7e15-108">[in] Die Anzahl der Elemente `pUnmappedPE` enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="b7e15-108">[in] The number of elements `pUnmappedPE` can hold.</span></span>  
  
 `pImageNameIn`  
 <span data-ttu-id="b7e15-109">[in] Ein Zeiger auf den Namen des ausführbaren Images.</span><span class="sxs-lookup"><span data-stu-id="b7e15-109">[in] A pointer to the name of the executable image.</span></span>  
  
 `pLoadersFileName`  
 <span data-ttu-id="b7e15-110">[in] Der Name der Ladeprogrammdatei.</span><span class="sxs-lookup"><span data-stu-id="b7e15-110">[in] The name of the loader file.</span></span>  
  
 `pCmdLine`  
 <span data-ttu-id="b7e15-111">[in] Befehlszeilenparameter, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="b7e15-111">[in] Command-line parameters, if any.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7e15-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b7e15-112">Requirements</span></span>  
 <span data-ttu-id="b7e15-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7e15-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7e15-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b7e15-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b7e15-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b7e15-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="b7e15-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="b7e15-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b7e15-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7e15-117">See also</span></span>

- [<span data-ttu-id="b7e15-118">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="b7e15-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)

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
ms.openlocfilehash: cc5324683daa9a02a6a89b2a3fb57ee9fd5dbe72
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136963"
---
# <a name="_corexemain2-function"></a><span data-ttu-id="7ce63-102">_CorExeMain2-Funktion</span><span class="sxs-lookup"><span data-stu-id="7ce63-102">_CorExeMain2 Function</span></span>
<span data-ttu-id="7ce63-103">Führt den Einstiegspunkt im angegebenen Speicherabbildcode aus.</span><span class="sxs-lookup"><span data-stu-id="7ce63-103">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="7ce63-104">Diese Funktion wird vom Betriebssystemladeprogramm aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="7ce63-104">This function is called by the operating system loader.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ce63-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ce63-105">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ce63-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="7ce63-106">Parameters</span></span>  
 `pUnmappedPE`  
 <span data-ttu-id="7ce63-107">in Ein Zeiger auf den Speicher Abbild-Code.</span><span class="sxs-lookup"><span data-stu-id="7ce63-107">[in] A pointer to the memory-mapped code.</span></span>  
  
 `cUnmappedPE`  
 <span data-ttu-id="7ce63-108">in Die Anzahl der Elemente, die `pUnmappedPE` enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="7ce63-108">[in] The number of elements `pUnmappedPE` can hold.</span></span>  
  
 `pImageNameIn`  
 <span data-ttu-id="7ce63-109">in Ein Zeiger auf den Namen des ausführbaren Bilds.</span><span class="sxs-lookup"><span data-stu-id="7ce63-109">[in] A pointer to the name of the executable image.</span></span>  
  
 `pLoadersFileName`  
 <span data-ttu-id="7ce63-110">in Der Name der Lade Datei.</span><span class="sxs-lookup"><span data-stu-id="7ce63-110">[in] The name of the loader file.</span></span>  
  
 `pCmdLine`  
 <span data-ttu-id="7ce63-111">in Befehlszeilenparameter (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="7ce63-111">[in] Command-line parameters, if any.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ce63-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7ce63-112">Requirements</span></span>  
 <span data-ttu-id="7ce63-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ce63-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ce63-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7ce63-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7ce63-115">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7ce63-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7ce63-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ce63-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ce63-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ce63-117">See also</span></span>

- [<span data-ttu-id="7ce63-118">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="7ce63-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)

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
ms.openlocfilehash: a3fb9d87b6433d46dad081619e0692a42219408d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673620"
---
# <a name="_corexemain2-function"></a><span data-ttu-id="51bb9-102">_CorExeMain2-Funktion</span><span class="sxs-lookup"><span data-stu-id="51bb9-102">_CorExeMain2 Function</span></span>

<span data-ttu-id="51bb9-103">Führt den Einstiegspunkt im angegebenen Speicherabbildcode aus.</span><span class="sxs-lookup"><span data-stu-id="51bb9-103">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="51bb9-104">Diese Funktion wird vom Betriebssystemladeprogramm aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="51bb9-104">This function is called by the operating system loader.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51bb9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="51bb9-105">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain2 (  
   [in] PBYTE           pUnmappedPE,  
   [in] DWORD           cUnmappedPE,  
   [in] __in LPWSTR     pImageNameIn,  
   [in] __in LPWSTR     pLoadersFileName,  
   [in] __in LPWSTR     pCmdLine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51bb9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="51bb9-106">Parameters</span></span>  

 `pUnmappedPE`  
 <span data-ttu-id="51bb9-107">in Ein Zeiger auf den Speicher Abbild-Code.</span><span class="sxs-lookup"><span data-stu-id="51bb9-107">[in] A pointer to the memory-mapped code.</span></span>  
  
 `cUnmappedPE`  
 <span data-ttu-id="51bb9-108">in Die Anzahl der Elemente, die `pUnmappedPE` enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="51bb9-108">[in] The number of elements `pUnmappedPE` can hold.</span></span>  
  
 `pImageNameIn`  
 <span data-ttu-id="51bb9-109">in Ein Zeiger auf den Namen des ausführbaren Bilds.</span><span class="sxs-lookup"><span data-stu-id="51bb9-109">[in] A pointer to the name of the executable image.</span></span>  
  
 `pLoadersFileName`  
 <span data-ttu-id="51bb9-110">in Der Name der Lade Datei.</span><span class="sxs-lookup"><span data-stu-id="51bb9-110">[in] The name of the loader file.</span></span>  
  
 `pCmdLine`  
 <span data-ttu-id="51bb9-111">in Befehlszeilenparameter (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="51bb9-111">[in] Command-line parameters, if any.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51bb9-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="51bb9-112">Requirements</span></span>  

 <span data-ttu-id="51bb9-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51bb9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51bb9-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="51bb9-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="51bb9-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="51bb9-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="51bb9-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51bb9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51bb9-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51bb9-117">See also</span></span>

- [<span data-ttu-id="51bb9-118">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="51bb9-118">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)

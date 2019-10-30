---
title: StrongNameCompareAssemblies-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
ms.openlocfilehash: adde52dddb63b83dcd7ff10703a43928d9601c92
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140619"
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="36452-102">StrongNameCompareAssemblies-Funktion</span><span class="sxs-lookup"><span data-stu-id="36452-102">StrongNameCompareAssemblies Function</span></span>
<span data-ttu-id="36452-103">Bestimmt, ob sich zwei Assemblys nur durch die Signaturen ihrer starken Namen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="36452-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="36452-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="36452-104">This function has been deprecated.</span></span> <span data-ttu-id="36452-105">Verwenden Sie stattdessen die [ICLRStrongName:: strongnamecompareassemblymethode](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) .</span><span class="sxs-lookup"><span data-stu-id="36452-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36452-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="36452-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36452-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="36452-107">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="36452-108">in Der Pfad zur ersten Assembly.</span><span class="sxs-lookup"><span data-stu-id="36452-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="36452-109">in Der Pfad zur zweiten Assembly.</span><span class="sxs-lookup"><span data-stu-id="36452-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="36452-110">vorgenommen Einer der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="36452-110">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="36452-111">`SN_CMP_DIFFERENT` (0): gibt an, dass die Assemblys unterschiedliche Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="36452-111">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="36452-112">`SN_CMP_IDENTICAL` (1): gibt an, dass die Assemblys exakt identisch sind, einschließlich ihrer Signaturen und Prüfsumme.</span><span class="sxs-lookup"><span data-stu-id="36452-112">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="36452-113">`SN_CMP_SIGONLY` (2): gibt an, dass sich die Assemblys nur durch Signatur und Prüfsumme unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="36452-113">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36452-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="36452-114">Return Value</span></span>  
 <span data-ttu-id="36452-115">`true` nach erfolgreichem Abschluss. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="36452-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36452-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="36452-116">Requirements</span></span>  
 <span data-ttu-id="36452-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36452-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36452-118">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="36452-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="36452-119">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="36452-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="36452-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36452-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36452-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="36452-121">Remarks</span></span>  
 <span data-ttu-id="36452-122">Die starke namens Signatur einer Assembly besteht aus dem Textnamen, der Version, der Kultur und dem öffentlichen Schlüssel Token der Assembly.</span><span class="sxs-lookup"><span data-stu-id="36452-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="36452-123">Wenn die `StrongNameCompareAssemblies`-Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="36452-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36452-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36452-124">See also</span></span>

- [<span data-ttu-id="36452-125">StrongNameCompareAssemblies-Methode</span><span class="sxs-lookup"><span data-stu-id="36452-125">StrongNameCompareAssemblies Method</span></span>](../hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [<span data-ttu-id="36452-126">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="36452-126">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

---
title: GetHashFromFile-Funktion
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
ms.openlocfilehash: ea2b70f37668587fb02513ab54da6c1915e2918d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176980"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="c8b1d-102">GetHashFromFile-Funktion</span><span class="sxs-lookup"><span data-stu-id="c8b1d-102">GetHashFromFile Function</span></span>
<span data-ttu-id="c8b1d-103">Generiert einen Hashwert für den Inhalt der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="c8b1d-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="c8b1d-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="c8b1d-104">This function has been deprecated.</span></span> <span data-ttu-id="c8b1d-105">Verwenden Sie stattdessen die [ICLRStrongName::GetHashFromFile-Methode.](../hosting/iclrstrongname-gethashfromfile-method.md)</span><span class="sxs-lookup"><span data-stu-id="c8b1d-105">Use the [ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8b1d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8b1d-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8b1d-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="c8b1d-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="c8b1d-108">[in] Der Name der zu hashenden Datei.</span><span class="sxs-lookup"><span data-stu-id="c8b1d-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="c8b1d-109">[in, out] Der Algorithmus, der beim Generieren des Hashs verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c8b1d-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="c8b1d-110">Gültige Algorithmen sind die, die von der Win32 CryptoAPI definiert werden.</span><span class="sxs-lookup"><span data-stu-id="c8b1d-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="c8b1d-111">Wenn `piHashAlg` auf 0 gesetzt ist, wird der Standardalgorithmus CALG_SHA-1 verwendet.</span><span class="sxs-lookup"><span data-stu-id="c8b1d-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="c8b1d-112">[out] Ein Bytearray, das den generierten Hash enthält.</span><span class="sxs-lookup"><span data-stu-id="c8b1d-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="c8b1d-113">[in] Die maximale Größe des `pbHash` Puffers, auf den verweist.</span><span class="sxs-lookup"><span data-stu-id="c8b1d-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="c8b1d-114">[out] Die Größe der zurückgegebenen `pbHash`in Bytes .</span><span class="sxs-lookup"><span data-stu-id="c8b1d-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8b1d-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c8b1d-115">Remarks</span></span>  
 <span data-ttu-id="c8b1d-116">Diese Funktion ist die gleiche wie [GetHashFromFileW](gethashfromfilew-function.md), mit der Ausnahme, dass die Dateinamenspezifikation ANSI anstelle von Unicode ist.</span><span class="sxs-lookup"><span data-stu-id="c8b1d-116">This function is the same as [GetHashFromFileW](gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8b1d-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c8b1d-117">Requirements</span></span>  
 <span data-ttu-id="c8b1d-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8b1d-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8b1d-119">**Kopfzeile:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="c8b1d-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c8b1d-120">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c8b1d-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c8b1d-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8b1d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8b1d-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8b1d-122">See also</span></span>

- [<span data-ttu-id="c8b1d-123">GetHashFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="c8b1d-123">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="c8b1d-124">GetHashFromFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="c8b1d-124">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="c8b1d-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c8b1d-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

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
ms.openlocfilehash: ffa25b1ec6fda80099f333c1d0a4cf57b76379e2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140690"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="d7fb9-102">GetHashFromFile-Funktion</span><span class="sxs-lookup"><span data-stu-id="d7fb9-102">GetHashFromFile Function</span></span>
<span data-ttu-id="d7fb9-103">Generiert einen Hashwert für den Inhalt der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="d7fb9-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="d7fb9-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="d7fb9-104">This function has been deprecated.</span></span> <span data-ttu-id="d7fb9-105">Verwenden Sie stattdessen die [ICLRStrongName:: GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="d7fb9-105">Use the [ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7fb9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7fb9-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7fb9-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="d7fb9-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="d7fb9-108">in Der Name der zu hashenden Datei.</span><span class="sxs-lookup"><span data-stu-id="d7fb9-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="d7fb9-109">[in, out] Der Algorithmus, der beim Erzeugen des Hashwerts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d7fb9-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="d7fb9-110">Gültige Algorithmen sind die, die von der Win32-CryptoAPI definiert werden.</span><span class="sxs-lookup"><span data-stu-id="d7fb9-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="d7fb9-111">Wenn `piHashAlg` auf 0 festgelegt ist, wird der Standard Algorithmus CALG_SHA-1 verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7fb9-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="d7fb9-112">vorgenommen Ein Bytearray, das den generierten Hash enthält.</span><span class="sxs-lookup"><span data-stu-id="d7fb9-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="d7fb9-113">in Die maximale Puffergröße, auf die `pbHash` zeigt.</span><span class="sxs-lookup"><span data-stu-id="d7fb9-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="d7fb9-114">vorgenommen Die Größe (in Bytes) des zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d7fb9-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7fb9-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d7fb9-115">Remarks</span></span>  
 <span data-ttu-id="d7fb9-116">Diese Funktion ist mit [GetHashFromFileW](gethashfromfilew-function.md)identisch, mit der Ausnahme, dass die Dateinamen Spezifikation ANSI anstelle von Unicode ist.</span><span class="sxs-lookup"><span data-stu-id="d7fb9-116">This function is the same as [GetHashFromFileW](gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7fb9-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d7fb9-117">Requirements</span></span>  
 <span data-ttu-id="d7fb9-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7fb9-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7fb9-119">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="d7fb9-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d7fb9-120">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d7fb9-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d7fb9-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7fb9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7fb9-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7fb9-122">See also</span></span>

- [<span data-ttu-id="d7fb9-123">GetHashFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="d7fb9-123">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="d7fb9-124">GetHashFromFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="d7fb9-124">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="d7fb9-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d7fb9-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

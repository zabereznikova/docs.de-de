---
title: ICLRStrongName::GetHashFromFile-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type:
- apiref
ms.openlocfilehash: e4a5f6440a016176cf06704b342c173b29748e78
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762109"
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="d4739-102">ICLRStrongName::GetHashFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="d4739-102">ICLRStrongName::GetHashFromFile Method</span></span>
<span data-ttu-id="d4739-103">Generiert einen Hashwert für den Inhalt der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="d4739-103">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4739-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4739-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4739-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d4739-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="d4739-106">in Der Name der zu hashenden Datei.</span><span class="sxs-lookup"><span data-stu-id="d4739-106">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="d4739-107">[in, out] Der Algorithmus, der beim Erzeugen des Hashwerts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d4739-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="d4739-108">Gültige Algorithmen sind die, die von der Win32-CryptoAPI definiert werden.</span><span class="sxs-lookup"><span data-stu-id="d4739-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="d4739-109">Wenn `piHashAlg` auf 0 festgelegt ist, wird der Standard Algorithmus CALG_SHA-1 verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4739-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="d4739-110">vorgenommen Ein Bytearray, das den generierten Hash enthält.</span><span class="sxs-lookup"><span data-stu-id="d4739-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="d4739-111">in Die maximale Größe des Puffers, `pbHash` auf den verweist.</span><span class="sxs-lookup"><span data-stu-id="d4739-111">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="d4739-112">vorgenommen Die Größe (in Bytes) des zurückgegebenen `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="d4739-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4739-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d4739-113">Return Value</span></span>  
 <span data-ttu-id="d4739-114">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="d4739-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4739-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d4739-115">Remarks</span></span>  
 <span data-ttu-id="d4739-116">Diese Methode ist identisch mit der [ICLRStrongName:: GetHashFromFileW](iclrstrongname-gethashfromfilew-method.md) -Methode, mit der Ausnahme, dass die Dateinamen Spezifikation ANSI anstelle von Unicode ist.</span><span class="sxs-lookup"><span data-stu-id="d4739-116">This method is the same as the [ICLRStrongName::GetHashFromFileW](iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4739-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d4739-117">Requirements</span></span>  
 <span data-ttu-id="d4739-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4739-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4739-119">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="d4739-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d4739-120">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d4739-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d4739-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4739-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4739-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d4739-122">See also</span></span>

- [<span data-ttu-id="d4739-123">GetHashFromFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="d4739-123">GetHashFromFileW Method</span></span>](iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="d4739-124">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d4739-124">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

---
title: ICLRStrongName::GetHashFromFileW-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
ms.openlocfilehash: 8f2d74531233f2ba423c39126ddc43e499cbb5d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176369"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="39d0d-102">ICLRStrongName::GetHashFromFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="39d0d-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="39d0d-103">Generiert einen Hashwert für den Inhalt der durch eine Unicode-Zeichenfolge angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="39d0d-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39d0d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="39d0d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="39d0d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="39d0d-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="39d0d-106">[in] Der Unicode-Name der zu hashenden Datei.</span><span class="sxs-lookup"><span data-stu-id="39d0d-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="39d0d-107">[in, out] Der Algorithmus, der beim Generieren des Hashs verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="39d0d-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="39d0d-108">Gültige Algorithmen sind die, die von der Win32 CryptoAPI definiert werden.</span><span class="sxs-lookup"><span data-stu-id="39d0d-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="39d0d-109">Wenn `piHashAlg` auf 0 gesetzt ist, wird der Standardalgorithmus CALG_SHA-1 verwendet.</span><span class="sxs-lookup"><span data-stu-id="39d0d-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="39d0d-110">[out] Ein Bytearray, das den generierten Hash enthält.</span><span class="sxs-lookup"><span data-stu-id="39d0d-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="39d0d-111">[in] Die maximale Größe des Puffers, auf die von `pbHash`verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="39d0d-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="39d0d-112">[out] Die Größe von in `pbHash`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="39d0d-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39d0d-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="39d0d-113">Return Value</span></span>  
 <span data-ttu-id="39d0d-114">`S_OK`wenn die Methode erfolgreich abgeschlossen wurde; Andernfalls ein HRESULT-Wert, der auf einen Fehler hinweist (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="39d0d-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39d0d-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="39d0d-115">Remarks</span></span>  
 <span data-ttu-id="39d0d-116">Diese Methode ist die gleiche wie die [ICLRStrongName::GetHashFromFile-Methode,](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) mit der Ausnahme, dass die Dateinamenspezifikation Unicode anstelle von ANSI ist.</span><span class="sxs-lookup"><span data-stu-id="39d0d-116">This method is the same as the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39d0d-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="39d0d-117">Requirements</span></span>  
 <span data-ttu-id="39d0d-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39d0d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39d0d-119">**Kopfzeile:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="39d0d-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="39d0d-120">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="39d0d-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39d0d-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39d0d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39d0d-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="39d0d-122">See also</span></span>

- [<span data-ttu-id="39d0d-123">GetHashFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="39d0d-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="39d0d-124">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="39d0d-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

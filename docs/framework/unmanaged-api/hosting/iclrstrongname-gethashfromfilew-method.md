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
ms.openlocfilehash: 6dbb3360132186c38c007fb5fa12a3724ca145aa
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762096"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="06b35-102">ICLRStrongName::GetHashFromFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="06b35-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="06b35-103">Generiert einen Hashwert für den Inhalt der durch eine Unicode-Zeichenfolge angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="06b35-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06b35-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="06b35-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="06b35-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="06b35-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="06b35-106">in Der Unicode-Name der zu hashenden Datei.</span><span class="sxs-lookup"><span data-stu-id="06b35-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="06b35-107">[in, out] Der Algorithmus, der beim Erzeugen des Hashwerts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="06b35-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="06b35-108">Gültige Algorithmen sind die, die von der Win32-CryptoAPI definiert werden.</span><span class="sxs-lookup"><span data-stu-id="06b35-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="06b35-109">Wenn `piHashAlg` auf 0 festgelegt ist, wird der Standard Algorithmus CALG_SHA-1 verwendet.</span><span class="sxs-lookup"><span data-stu-id="06b35-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="06b35-110">vorgenommen Ein Bytearray, das den generierten Hash enthält.</span><span class="sxs-lookup"><span data-stu-id="06b35-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="06b35-111">in Die maximale Puffergröße, auf die von verwiesen wird `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="06b35-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="06b35-112">vorgenommen Die Größe von in Bytes `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="06b35-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06b35-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="06b35-113">Return Value</span></span>  
 <span data-ttu-id="06b35-114">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="06b35-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06b35-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="06b35-115">Remarks</span></span>  
 <span data-ttu-id="06b35-116">Diese Methode ist identisch mit der [ICLRStrongName:: GetHashFromFile](iclrstrongname-gethashfromfile-method.md) -Methode, mit der Ausnahme, dass die Dateinamen Spezifikation anstelle von ANSI Unicode ist.</span><span class="sxs-lookup"><span data-stu-id="06b35-116">This method is the same as the [ICLRStrongName::GetHashFromFile](iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06b35-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="06b35-117">Requirements</span></span>  
 <span data-ttu-id="06b35-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06b35-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06b35-119">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="06b35-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="06b35-120">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="06b35-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06b35-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06b35-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06b35-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06b35-122">See also</span></span>

- [<span data-ttu-id="06b35-123">GetHashFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="06b35-123">GetHashFromFile Method</span></span>](iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="06b35-124">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="06b35-124">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

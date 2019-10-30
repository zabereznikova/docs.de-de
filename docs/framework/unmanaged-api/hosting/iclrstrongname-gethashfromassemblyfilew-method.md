---
title: ICLRStrongName::GetHashFromAssemblyFileW-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type:
- apiref
ms.openlocfilehash: 43a5cd57a8eeaba70f1bb1ffb9cab5bb1a067914
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130953"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="97b07-102">ICLRStrongName::GetHashFromAssemblyFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="97b07-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>
<span data-ttu-id="97b07-103">Generiert einen Hashwert für den Inhalt der durch eine Unicode-Zeichenfolge angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="97b07-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97b07-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="97b07-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97b07-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="97b07-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="97b07-106">in Der Pfad zu der Datei, für die der Hashwert verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="97b07-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="97b07-107">Dieser Parameter muss eine Unicode-Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="97b07-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="97b07-108">[in, out] Eine-Konstante, die den Hash Algorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="97b07-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="97b07-109">Verwenden Sie 0 für den Standard Hash Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="97b07-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="97b07-110">vorgenommen Der zurückgegebene Hash Puffer.</span><span class="sxs-lookup"><span data-stu-id="97b07-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="97b07-111">in Die angeforderte maximale Größe `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="97b07-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="97b07-112">vorgenommen Die zurückgegebene Größe (in Bytes) der `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="97b07-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97b07-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="97b07-113">Return Value</span></span>  
 <span data-ttu-id="97b07-114">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="97b07-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97b07-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="97b07-115">Requirements</span></span>  
 <span data-ttu-id="97b07-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97b07-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97b07-117">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="97b07-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="97b07-118">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="97b07-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="97b07-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97b07-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97b07-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97b07-120">See also</span></span>

- [<span data-ttu-id="97b07-121">GetHashFromAssemblyFile-Methode</span><span class="sxs-lookup"><span data-stu-id="97b07-121">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="97b07-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="97b07-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

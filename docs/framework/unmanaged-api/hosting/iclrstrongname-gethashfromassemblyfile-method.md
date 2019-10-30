---
title: ICLRStrongName::GetHashFromAssemblyFile-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type:
- apiref
ms.openlocfilehash: 3fd9efd3961be1d6e6e91b881327628c598e364e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092726"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="a3712-102">ICLRStrongName::GetHashFromAssemblyFile-Methode</span><span class="sxs-lookup"><span data-stu-id="a3712-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="a3712-103">Ruft einen Hash der angegebenen Assemblydatei unter Verwendung des angegebenen Hashalgorithmus ab.</span><span class="sxs-lookup"><span data-stu-id="a3712-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3712-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3712-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3712-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a3712-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="a3712-106">in Der Pfad zu der Datei, für die der Hashwert verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a3712-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="a3712-107">[in, out] Eine-Konstante, die den Hash Algorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="a3712-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="a3712-108">Verwenden Sie 0 für den Standard Hash Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="a3712-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="a3712-109">vorgenommen Der zurückgegebene Hash Puffer.</span><span class="sxs-lookup"><span data-stu-id="a3712-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="a3712-110">in Die angeforderte maximale Größe `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="a3712-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="a3712-111">vorgenommen Die zurückgegebene Größe (in Bytes) der `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="a3712-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3712-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a3712-112">Return Value</span></span>  
 <span data-ttu-id="a3712-113">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="a3712-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3712-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a3712-114">Requirements</span></span>  
 <span data-ttu-id="a3712-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3712-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3712-116">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="a3712-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a3712-117">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a3712-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3712-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3712-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3712-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3712-119">See also</span></span>

- [<span data-ttu-id="a3712-120">GetHashFromAssemblyFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="a3712-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="a3712-121">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a3712-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

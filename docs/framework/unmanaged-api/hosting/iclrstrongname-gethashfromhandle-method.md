---
title: ICLRStrongName::GetHashFromHandle-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromHandle
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromHandle method [.NET Framework hosting]
ms.assetid: 3bedbb7d-3cdd-4175-b370-10ae734062db
topic_type:
- apiref
ms.openlocfilehash: c095c99ee60d6b2ea0e5bce7010a66d40160443d
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899685"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="491fa-102">ICLRStrongName::GetHashFromHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="491fa-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="491fa-103">Generiert einen Hash über den Inhalt der Datei mit dem angegebenen Datei Handle unter Verwendung des angegebenen Hash Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="491fa-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="491fa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="491fa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="491fa-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="491fa-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="491fa-106">in Das Handle der Datei, für die der Hashwert verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="491fa-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="491fa-107">[in, out] Eine-Konstante, die den Hash Algorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="491fa-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="491fa-108">Verwenden Sie 0 (null) für den Standard Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="491fa-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="491fa-109">vorgenommen Der zurückgegebene Hash Puffer.</span><span class="sxs-lookup"><span data-stu-id="491fa-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="491fa-110">in Die angeforderte maximale Größe `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="491fa-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="491fa-111">vorgenommen Die Größe (in Bytes) des zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="491fa-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="491fa-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="491fa-112">Return Value</span></span>  
 <span data-ttu-id="491fa-113">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="491fa-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="491fa-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="491fa-114">Requirements</span></span>  
 <span data-ttu-id="491fa-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="491fa-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="491fa-116">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="491fa-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="491fa-117">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="491fa-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="491fa-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="491fa-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="491fa-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="491fa-119">See also</span></span>

- [<span data-ttu-id="491fa-120">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="491fa-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

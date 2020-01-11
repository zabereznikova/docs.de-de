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
ms.openlocfilehash: 8131a9838cc958405ca23c75c702db5ec65a41c8
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901192"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="35394-102">ICLRStrongName::GetHashFromAssemblyFile-Methode</span><span class="sxs-lookup"><span data-stu-id="35394-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="35394-103">Ruft einen Hash der angegebenen Assemblydatei unter Verwendung des angegebenen Hashalgorithmus ab.</span><span class="sxs-lookup"><span data-stu-id="35394-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35394-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="35394-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35394-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="35394-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="35394-106">in Der Pfad zu der Datei, für die der Hashwert verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="35394-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="35394-107">[in, out] Eine-Konstante, die den Hash Algorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="35394-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="35394-108">Verwenden Sie 0 für den Standard Hash Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="35394-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="35394-109">vorgenommen Der zurückgegebene Hash Puffer.</span><span class="sxs-lookup"><span data-stu-id="35394-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="35394-110">in Die angeforderte maximale Größe `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="35394-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="35394-111">vorgenommen Die zurückgegebene Größe (in Bytes) der `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="35394-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35394-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="35394-112">Return Value</span></span>  
 <span data-ttu-id="35394-113">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="35394-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35394-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="35394-114">Requirements</span></span>  
 <span data-ttu-id="35394-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35394-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35394-116">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="35394-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="35394-117">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="35394-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35394-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35394-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35394-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35394-119">See also</span></span>

- [<span data-ttu-id="35394-120">GetHashFromAssemblyFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="35394-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="35394-121">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="35394-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

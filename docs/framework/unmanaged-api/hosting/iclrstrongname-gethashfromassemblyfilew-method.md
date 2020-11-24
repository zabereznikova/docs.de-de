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
ms.openlocfilehash: e94bfe6151ed42886355423a838f21e13748ec61
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685772"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="1dc03-102">ICLRStrongName::GetHashFromAssemblyFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="1dc03-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>

<span data-ttu-id="1dc03-103">Generiert einen Hashwert für den Inhalt der durch eine Unicode-Zeichenfolge angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="1dc03-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dc03-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1dc03-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1dc03-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1dc03-105">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="1dc03-106">in Der Pfad zu der Datei, für die der Hashwert verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1dc03-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="1dc03-107">Dieser Parameter muss eine Unicode-Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="1dc03-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="1dc03-108">[in, out] Eine-Konstante, die den Hash Algorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="1dc03-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="1dc03-109">Verwenden Sie 0 für den Standard Hash Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="1dc03-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="1dc03-110">vorgenommen Der zurückgegebene Hash Puffer.</span><span class="sxs-lookup"><span data-stu-id="1dc03-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="1dc03-111">in Die angeforderte maximale Größe von `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="1dc03-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="1dc03-112">vorgenommen Die zurückgegebene Größe von in Bytes `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="1dc03-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1dc03-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1dc03-113">Return Value</span></span>  

 <span data-ttu-id="1dc03-114">`S_OK` , wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="1dc03-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dc03-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1dc03-115">Requirements</span></span>  

 <span data-ttu-id="1dc03-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1dc03-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dc03-117">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="1dc03-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1dc03-118">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1dc03-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1dc03-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dc03-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dc03-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1dc03-120">See also</span></span>

- [<span data-ttu-id="1dc03-121">GetHashFromAssemblyFile-Methode</span><span class="sxs-lookup"><span data-stu-id="1dc03-121">GetHashFromAssemblyFile Method</span></span>](iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="1dc03-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1dc03-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

---
title: ICLRStrongName::StrongNameKeyGenEx-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type:
- apiref
ms.openlocfilehash: 1a5bcfb7a272af694126025f28ca3efe5a881c15
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135021"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="2a9e8-102">ICLRStrongName::StrongNameKeyGenEx-Methode</span><span class="sxs-lookup"><span data-stu-id="2a9e8-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="2a9e8-103">Generiert ein neues öffentliches/privates Schlüsselpaar mit der angegebenen Schlüsselgröße für eine starke namens Verwendung.</span><span class="sxs-lookup"><span data-stu-id="2a9e8-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a9e8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a9e8-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a9e8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2a9e8-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="2a9e8-106">in Der angeforderte Schlüssel Container Name.</span><span class="sxs-lookup"><span data-stu-id="2a9e8-106">[in] The requested key container name.</span></span> <span data-ttu-id="2a9e8-107">`wszKeyContainer` müssen entweder eine nicht leere Zeichenfolge oder NULL sein, um einen temporären Namen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="2a9e8-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="2a9e8-108">in Ein-Wert, der angibt, ob der Schlüssel registriert bleiben soll.</span><span class="sxs-lookup"><span data-stu-id="2a9e8-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="2a9e8-109">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="2a9e8-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="2a9e8-110">0x00000000-wird verwendet, wenn `wszKeyContainer` NULL ist, um einen temporären Schlüssel Container Namen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="2a9e8-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="2a9e8-111">0x00000001 (`SN_LEAVE_KEY`): gibt an, dass der Schlüssel registriert bleiben soll.</span><span class="sxs-lookup"><span data-stu-id="2a9e8-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="2a9e8-112">in Die angeforderte Größe des Schlüssels in Bits.</span><span class="sxs-lookup"><span data-stu-id="2a9e8-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="2a9e8-113">vorgenommen Das zurückgegebene Paar aus öffentlichem und privatem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="2a9e8-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="2a9e8-114">vorgenommen Die Größe `ppbKeyBlob`in Byte.</span><span class="sxs-lookup"><span data-stu-id="2a9e8-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a9e8-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2a9e8-115">Return Value</span></span>  
 <span data-ttu-id="2a9e8-116">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="2a9e8-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a9e8-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2a9e8-117">Remarks</span></span>  
 <span data-ttu-id="2a9e8-118">Die .NET Framework Versionen 1,0 und 1,1 erfordern eine `dwKeySize` von 1024 Bits, um eine Assembly mit einem starken Namen zu signieren. in Version 2,0 werden Unterstützung für 2048-Bit-Schlüssel hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2a9e8-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="2a9e8-119">Nachdem der Schlüssel abgerufen wurde, sollten Sie die [ICLRStrongName:: strongnamefrebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) -Methode abrufen, um den zugewiesenen Speicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="2a9e8-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a9e8-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2a9e8-120">Requirements</span></span>  
 <span data-ttu-id="2a9e8-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a9e8-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a9e8-122">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="2a9e8-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2a9e8-123">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2a9e8-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a9e8-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a9e8-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a9e8-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a9e8-125">See also</span></span>

- [<span data-ttu-id="2a9e8-126">StrongNameKeyGen-Methode</span><span class="sxs-lookup"><span data-stu-id="2a9e8-126">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="2a9e8-127">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2a9e8-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

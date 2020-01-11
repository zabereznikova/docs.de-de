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
ms.openlocfilehash: b09677a45c5d515aacb2cac709599140039a9dd8
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899554"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="17d54-102">ICLRStrongName::StrongNameKeyGenEx-Methode</span><span class="sxs-lookup"><span data-stu-id="17d54-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="17d54-103">Generiert ein neues öffentliches/privates Schlüsselpaar mit der angegebenen Schlüsselgröße für eine starke namens Verwendung.</span><span class="sxs-lookup"><span data-stu-id="17d54-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17d54-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="17d54-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17d54-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="17d54-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="17d54-106">in Der angeforderte Schlüssel Container Name.</span><span class="sxs-lookup"><span data-stu-id="17d54-106">[in] The requested key container name.</span></span> <span data-ttu-id="17d54-107">`wszKeyContainer` müssen entweder eine nicht leere Zeichenfolge oder NULL sein, um einen temporären Namen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="17d54-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="17d54-108">in Ein-Wert, der angibt, ob der Schlüssel registriert bleiben soll.</span><span class="sxs-lookup"><span data-stu-id="17d54-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="17d54-109">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="17d54-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="17d54-110">0x00000000-wird verwendet, wenn `wszKeyContainer` NULL ist, um einen temporären Schlüssel Container Namen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="17d54-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="17d54-111">0x00000001 (`SN_LEAVE_KEY`): gibt an, dass der Schlüssel registriert bleiben soll.</span><span class="sxs-lookup"><span data-stu-id="17d54-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="17d54-112">in Die angeforderte Größe des Schlüssels in Bits.</span><span class="sxs-lookup"><span data-stu-id="17d54-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="17d54-113">vorgenommen Das zurückgegebene Paar aus öffentlichem und privatem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="17d54-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="17d54-114">vorgenommen Die Größe `ppbKeyBlob`in Byte.</span><span class="sxs-lookup"><span data-stu-id="17d54-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17d54-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="17d54-115">Return Value</span></span>  
 <span data-ttu-id="17d54-116">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="17d54-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17d54-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="17d54-117">Remarks</span></span>  
 <span data-ttu-id="17d54-118">Die .NET Framework Versionen 1,0 und 1,1 erfordern eine `dwKeySize` von 1024 Bits, um eine Assembly mit einem starken Namen zu signieren. in Version 2,0 werden Unterstützung für 2048-Bit-Schlüssel hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="17d54-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="17d54-119">Nachdem der Schlüssel abgerufen wurde, sollten Sie die [ICLRStrongName:: strongnamefrebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) -Methode abrufen, um den zugewiesenen Speicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="17d54-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17d54-120">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="17d54-120">Requirements</span></span>  
 <span data-ttu-id="17d54-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17d54-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17d54-122">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="17d54-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="17d54-123">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="17d54-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="17d54-124">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17d54-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17d54-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17d54-125">See also</span></span>

- [<span data-ttu-id="17d54-126">StrongNameKeyGen-Methode</span><span class="sxs-lookup"><span data-stu-id="17d54-126">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="17d54-127">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="17d54-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

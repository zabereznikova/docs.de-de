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
ms.openlocfilehash: fb18b7b5ac73a1f270af6fae95a23e04b17ca5f1
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763071"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="71e00-102">ICLRStrongName::StrongNameKeyGenEx-Methode</span><span class="sxs-lookup"><span data-stu-id="71e00-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="71e00-103">Generiert ein neues öffentliches/privates Schlüsselpaar mit der angegebenen Schlüsselgröße für eine starke namens Verwendung.</span><span class="sxs-lookup"><span data-stu-id="71e00-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71e00-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="71e00-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71e00-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="71e00-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="71e00-106">in Der angeforderte Schlüssel Container Name.</span><span class="sxs-lookup"><span data-stu-id="71e00-106">[in] The requested key container name.</span></span> <span data-ttu-id="71e00-107">`wszKeyContainer`muss entweder eine nicht leere Zeichenfolge oder NULL sein, um einen temporären Namen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="71e00-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="71e00-108">in Ein-Wert, der angibt, ob der Schlüssel registriert bleiben soll.</span><span class="sxs-lookup"><span data-stu-id="71e00-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="71e00-109">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="71e00-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="71e00-110">0x00000000-wird verwendet `wszKeyContainer` , wenn den Wert NULL hat, um einen temporären Schlüssel Container Namen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="71e00-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="71e00-111">0x00000001 ( `SN_LEAVE_KEY` ): gibt an, dass der Schlüssel registriert bleiben soll.</span><span class="sxs-lookup"><span data-stu-id="71e00-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="71e00-112">in Die angeforderte Größe des Schlüssels in Bits.</span><span class="sxs-lookup"><span data-stu-id="71e00-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="71e00-113">vorgenommen Das zurückgegebene Paar aus öffentlichem und privatem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="71e00-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="71e00-114">vorgenommen Die Größe von in Bytes `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="71e00-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71e00-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="71e00-115">Return Value</span></span>  
 <span data-ttu-id="71e00-116">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="71e00-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71e00-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="71e00-117">Remarks</span></span>  
 <span data-ttu-id="71e00-118">Die .NET Framework Versionen 1,0 und 1,1 erfordern eine `dwKeySize` von 1024 Bits zum Signieren einer Assembly mit einem starken Namen; Version 2,0 fügt Unterstützung für 2048-Bit-Schlüssel hinzu.</span><span class="sxs-lookup"><span data-stu-id="71e00-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="71e00-119">Nachdem der Schlüssel abgerufen wurde, sollten Sie die [ICLRStrongName:: strongnamefrebuffer](iclrstrongname-strongnamefreebuffer-method.md) -Methode abrufen, um den zugewiesenen Speicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="71e00-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71e00-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="71e00-120">Requirements</span></span>  
 <span data-ttu-id="71e00-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71e00-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71e00-122">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="71e00-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="71e00-123">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="71e00-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71e00-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71e00-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71e00-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="71e00-125">See also</span></span>

- [<span data-ttu-id="71e00-126">StrongNameKeyGen-Methode</span><span class="sxs-lookup"><span data-stu-id="71e00-126">StrongNameKeyGen Method</span></span>](iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="71e00-127">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71e00-127">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

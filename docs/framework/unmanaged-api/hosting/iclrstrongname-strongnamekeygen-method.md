---
title: ICLRStrongName::StrongNameKeyGen-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type:
- apiref
ms.openlocfilehash: db5c0dbe57607c7a3bf8b97cee734415aa934336
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763084"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="0bbcb-102">ICLRStrongName::StrongNameKeyGen-Methode</span><span class="sxs-lookup"><span data-stu-id="0bbcb-102">ICLRStrongName::StrongNameKeyGen Method</span></span>
<span data-ttu-id="0bbcb-103">Erstellt ein neues öffentliches/privates Schlüsselpaar für die Verwendung starker Namen.</span><span class="sxs-lookup"><span data-stu-id="0bbcb-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bbcb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0bbcb-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bbcb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0bbcb-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="0bbcb-106">in Der angeforderte Schlüssel Container Name.</span><span class="sxs-lookup"><span data-stu-id="0bbcb-106">[in] The requested key container name.</span></span> <span data-ttu-id="0bbcb-107">`wszKeyContainer`muss entweder eine nicht leere Zeichenfolge oder NULL sein, um einen temporären Namen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="0bbcb-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0bbcb-108">in Ein-Wert, der angibt, ob der Schlüssel registriert bleiben soll.</span><span class="sxs-lookup"><span data-stu-id="0bbcb-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="0bbcb-109">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="0bbcb-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="0bbcb-110">0x00000000-wird verwendet `wszKeyContainer` , wenn den Wert NULL hat, um einen temporären Schlüssel Container Namen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="0bbcb-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="0bbcb-111">0x00000001 ( `SN_LEAVE_KEY` ): gibt an, dass der Schlüssel registriert bleiben soll.</span><span class="sxs-lookup"><span data-stu-id="0bbcb-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="0bbcb-112">vorgenommen Das zurückgegebene Paar aus öffentlichem und privatem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="0bbcb-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="0bbcb-113">vorgenommen Die Größe von in Bytes `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="0bbcb-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0bbcb-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0bbcb-114">Return Value</span></span>  
 <span data-ttu-id="0bbcb-115">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="0bbcb-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bbcb-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0bbcb-116">Remarks</span></span>  
 <span data-ttu-id="0bbcb-117">Die [ICLRStrongName:: StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) -Methode erstellt einen 1024-Bit-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="0bbcb-117">The [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="0bbcb-118">Nachdem der Schlüssel abgerufen wurde, sollten Sie die [ICLRStrongName:: strongnamefrebuffer](iclrstrongname-strongnamefreebuffer-method.md) -Methode abrufen, um den zugewiesenen Speicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="0bbcb-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bbcb-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0bbcb-119">Requirements</span></span>  
 <span data-ttu-id="0bbcb-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bbcb-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bbcb-121">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="0bbcb-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0bbcb-122">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0bbcb-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0bbcb-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bbcb-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bbcb-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0bbcb-124">See also</span></span>

- [<span data-ttu-id="0bbcb-125">StrongNameKeyGenEx-Methode</span><span class="sxs-lookup"><span data-stu-id="0bbcb-125">StrongNameKeyGenEx Method</span></span>](iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="0bbcb-126">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0bbcb-126">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

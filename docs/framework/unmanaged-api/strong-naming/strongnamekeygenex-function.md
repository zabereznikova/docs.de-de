---
title: StrongNameKeyGenEx-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGenEx
helpviewer_keywords:
- StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type:
- apiref
ms.openlocfilehash: f28ee5767997240018d182b8303e4f65be81c702
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708542"
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="07308-102">StrongNameKeyGenEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="07308-102">StrongNameKeyGenEx Function</span></span>

<span data-ttu-id="07308-103">Generiert ein neues öffentliches/privates Schlüsselpaar mit der angegebenen Schlüsselgröße für eine starke namens Verwendung.</span><span class="sxs-lookup"><span data-stu-id="07308-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="07308-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="07308-104">This function has been deprecated.</span></span> <span data-ttu-id="07308-105">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="07308-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07308-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="07308-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07308-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="07308-107">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="07308-108">in Der angeforderte Schlüssel Container Name.</span><span class="sxs-lookup"><span data-stu-id="07308-108">[in] The requested key container name.</span></span> <span data-ttu-id="07308-109">`wszKeyContainer` muss eine nicht leere Zeichenfolge oder NULL sein, um einen temporären Namen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="07308-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="07308-110">in Gibt an, ob der Schlüssel registriert bleiben soll.</span><span class="sxs-lookup"><span data-stu-id="07308-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="07308-111">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="07308-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="07308-112">0x00000000-wird verwendet `wszKeyContainer` , wenn den Wert NULL hat, um einen temporären Schlüssel Container Namen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="07308-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="07308-113">0x00000001 ( `SN_LEAVE_KEY` ): gibt an, dass der Schlüssel registriert bleiben soll.</span><span class="sxs-lookup"><span data-stu-id="07308-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="07308-114">in Die angeforderte Größe des Schlüssels in Bits.</span><span class="sxs-lookup"><span data-stu-id="07308-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="07308-115">vorgenommen Das zurückgegebene Paar aus öffentlichem und privatem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="07308-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="07308-116">vorgenommen Die Größe von in Bytes `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="07308-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07308-117">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="07308-117">Return Value</span></span>  

 <span data-ttu-id="07308-118">`true` nach erfolgreichem Abschluss: andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="07308-118">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07308-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="07308-119">Remarks</span></span>  

 <span data-ttu-id="07308-120">Die .NET Framework Versionen 1,0 und 1,1 erfordern eine `dwKeySize` von 1024 Bits zum Signieren einer Assembly mit einem starken Namen; Version 2,0 fügt Unterstützung für 2048-Bit-Schlüssel hinzu.</span><span class="sxs-lookup"><span data-stu-id="07308-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="07308-121">Nachdem der Schlüssel abgerufen wurde, sollten Sie die [strongnamefrebuffer](strongnamefreebuffer-function.md) -Funktion zum Freigeben des zugewiesenen Speichers abrufen.</span><span class="sxs-lookup"><span data-stu-id="07308-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="07308-122">Wenn die `StrongNameKeyGenEx` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="07308-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07308-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="07308-123">Requirements</span></span>  

 <span data-ttu-id="07308-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07308-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07308-125">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="07308-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="07308-126">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="07308-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="07308-127">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07308-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07308-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="07308-128">See also</span></span>

- [<span data-ttu-id="07308-129">StrongNameKeyGenEx-Methode</span><span class="sxs-lookup"><span data-stu-id="07308-129">StrongNameKeyGenEx Method</span></span>](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="07308-130">StrongNameKeyGen-Methode</span><span class="sxs-lookup"><span data-stu-id="07308-130">StrongNameKeyGen Method</span></span>](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="07308-131">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07308-131">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

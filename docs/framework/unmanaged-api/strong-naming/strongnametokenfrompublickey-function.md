---
title: StrongNameTokenFromPublicKey-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
ms.openlocfilehash: 20be3114908ef78966eead05ae8ba6333a491404
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175056"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="fcf86-102">StrongNameTokenFromPublicKey-Funktion</span><span class="sxs-lookup"><span data-stu-id="fcf86-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="fcf86-103">Ruft ein Token ab, das einen öffentlichen Schlüssel darstellt.</span><span class="sxs-lookup"><span data-stu-id="fcf86-103">Gets a token representing a public key.</span></span> <span data-ttu-id="fcf86-104">Ein Token mit starkem Namen ist die verkürzte Form eines öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="fcf86-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="fcf86-105">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="fcf86-105">This function has been deprecated.</span></span> <span data-ttu-id="fcf86-106">Verwenden Sie stattdessen die [ICLRStrongName::StrongNameTokenFromPublicKey-Methode.](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)</span><span class="sxs-lookup"><span data-stu-id="fcf86-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcf86-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="fcf86-107">Syntax</span></span>  
  
```cpp  
BOOLEANStrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcf86-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="fcf86-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="fcf86-109">[in] Eine Struktur vom Typ [PublicKeyBlob,](publickeyblob-structure.md) die den öffentlichen Teil des Schlüsselpaars enthält, der zum Generieren der Signatur mit starkem Namen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fcf86-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="fcf86-110">[in] Die Größe von in `pbPublicKeyBlob`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="fcf86-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="fcf86-111">[out] Das Token mit starkem Namen, das dem in `pbPublicKeyBlob`übergebenen Schlüssel entspricht.</span><span class="sxs-lookup"><span data-stu-id="fcf86-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="fcf86-112">Die Common Language Runtime weist den Speicher zu, in dem das Token zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="fcf86-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="fcf86-113">Der Aufrufer muss diesen Speicher mithilfe der [StrongNameFreeBuffer-Funktion](strongnamefreebuffer-function.md) freizugeben.</span><span class="sxs-lookup"><span data-stu-id="fcf86-113">The caller must free this memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="fcf86-114">[out] Die Größe des zurückgegebenen Tokens für starken Namen in Bytes.</span><span class="sxs-lookup"><span data-stu-id="fcf86-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fcf86-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fcf86-115">Return Value</span></span>  
 <span data-ttu-id="fcf86-116">`true`bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="fcf86-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcf86-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fcf86-117">Remarks</span></span>  
 <span data-ttu-id="fcf86-118">Ein Token mit starkem Namen ist die verkürzte Form eines öffentlichen Schlüssels, der zum Speichern von Schlüsselinformationen in Metadaten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fcf86-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="fcf86-119">Insbesondere werden Token mit starkem Namen in Assemblyverweisen verwendet, um auf die abhängige Assembly zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="fcf86-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="fcf86-120">Wenn `StrongNameTokenFromPublicKey` die Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo-Funktion](strongnameerrorinfo-function.md) auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fcf86-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcf86-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fcf86-121">Requirements</span></span>  
 <span data-ttu-id="fcf86-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcf86-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcf86-123">**Kopfzeile:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="fcf86-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="fcf86-124">**Bibliothek:** Als Ressource in mscoree.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fcf86-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="fcf86-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcf86-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcf86-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fcf86-126">See also</span></span>

- [<span data-ttu-id="fcf86-127">StrongNameTokenFromPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="fcf86-127">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="fcf86-128">StrongNameGetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="fcf86-128">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="fcf86-129">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="fcf86-129">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)

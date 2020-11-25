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
ms.openlocfilehash: 89556cf0e1ef65c35278a526e10fc791063ea2c6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708347"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="8445a-102">StrongNameTokenFromPublicKey-Funktion</span><span class="sxs-lookup"><span data-stu-id="8445a-102">StrongNameTokenFromPublicKey Function</span></span>

<span data-ttu-id="8445a-103">Ruft ein Token ab, das einen öffentlichen Schlüssel darstellt.</span><span class="sxs-lookup"><span data-stu-id="8445a-103">Gets a token representing a public key.</span></span> <span data-ttu-id="8445a-104">Ein Token mit starkem Namen ist die verkürzte Form eines öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="8445a-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="8445a-105">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="8445a-105">This function has been deprecated.</span></span> <span data-ttu-id="8445a-106">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="8445a-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8445a-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="8445a-107">Syntax</span></span>  
  
```cpp  
BOOLEANStrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8445a-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="8445a-108">Parameters</span></span>  

 `pbPublicKeyBlob`  
 <span data-ttu-id="8445a-109">in Eine Struktur vom Typ [PublicKeyBlob](publickeyblob-structure.md) , die den öffentlichen Teil des Schlüssel Paars enthält, das zum Generieren der starken Namens Signatur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8445a-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="8445a-110">in Die Größe von in Bytes `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="8445a-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="8445a-111">vorgenommen Das Token für den starken Namen, das dem übergebenen Schlüssel entspricht `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="8445a-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="8445a-112">Der Common Language Runtime ordnet den Speicher zu, in den das Token zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="8445a-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="8445a-113">Der Aufrufer muss diesen Arbeitsspeicher mithilfe der [StrongNameFreeBuffer](strongnamefreebuffer-function.md) -Funktion freigeben.</span><span class="sxs-lookup"><span data-stu-id="8445a-113">The caller must free this memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="8445a-114">vorgenommen Die Größe (in Bytes) des zurückgegebenen Token für den starken Namen.</span><span class="sxs-lookup"><span data-stu-id="8445a-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8445a-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8445a-115">Return Value</span></span>  

 <span data-ttu-id="8445a-116">`true` nach erfolgreichem Abschluss: andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="8445a-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8445a-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8445a-117">Remarks</span></span>  

 <span data-ttu-id="8445a-118">Ein Token mit starkem Namen ist die verkürzte Form eines öffentlichen Schlüssels, mit dem Speicherplatz beim Speichern von Schlüsselinformationen in Metadaten eingespart wird.</span><span class="sxs-lookup"><span data-stu-id="8445a-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="8445a-119">Insbesondere werden starke namens Token in Assemblyverweisen verwendet, um auf die abhängige Assembly zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="8445a-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="8445a-120">Wenn die `StrongNameTokenFromPublicKey` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8445a-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8445a-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8445a-121">Requirements</span></span>  

 <span data-ttu-id="8445a-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8445a-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8445a-123">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="8445a-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="8445a-124">**Bibliothek:** Als Ressource in mscoree.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8445a-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="8445a-125">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8445a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8445a-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8445a-126">See also</span></span>

- [<span data-ttu-id="8445a-127">StrongNameTokenFromPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="8445a-127">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="8445a-128">StrongNameGetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="8445a-128">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="8445a-129">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="8445a-129">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)

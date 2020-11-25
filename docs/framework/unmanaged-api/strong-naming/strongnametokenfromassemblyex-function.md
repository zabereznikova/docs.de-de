---
title: StrongNameTokenFromAssemblyEx-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx function [.NET Framework strong naming]
ms.assetid: 67a8a9f2-dee3-44b2-a1c0-f307a3bdf90f
topic_type:
- apiref
ms.openlocfilehash: 566bba09f6bfac2f7616dc5caf32ef431f2e1e67
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719800"
---
# <a name="strongnametokenfromassemblyex-function"></a><span data-ttu-id="4214b-102">StrongNameTokenFromAssemblyEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="4214b-102">StrongNameTokenFromAssemblyEx Function</span></span>

<span data-ttu-id="4214b-103">Erstellt ein Token für einen starken Namen aus der angegebenen Assemblydatei und gibt den öffentlichen Schlüssel zurück, den das Token darstellt.</span><span class="sxs-lookup"><span data-stu-id="4214b-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
 <span data-ttu-id="4214b-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="4214b-104">This function has been deprecated.</span></span> <span data-ttu-id="4214b-105">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameTokenFromAssemblyEx](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="4214b-105">Use the [ICLRStrongName::StrongNameTokenFromAssemblyEx](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4214b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4214b-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4214b-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="4214b-107">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="4214b-108">in Der Pfad zur PE-Datei (portable ausführbare Datei) für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="4214b-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="4214b-109">vorgenommen Das zurückgegebene Token für den starken Namen.</span><span class="sxs-lookup"><span data-stu-id="4214b-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="4214b-110">vorgenommen Die Größe (in Bytes) des Tokens für einen starken Namen.</span><span class="sxs-lookup"><span data-stu-id="4214b-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="4214b-111">vorgenommen Der zurückgegebene öffentliche Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="4214b-111">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="4214b-112">vorgenommen Die Größe des öffentlichen Schlüssels in Bytes.</span><span class="sxs-lookup"><span data-stu-id="4214b-112">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4214b-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4214b-113">Return Value</span></span>  

 <span data-ttu-id="4214b-114">`true` nach erfolgreichem Abschluss: andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="4214b-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4214b-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4214b-115">Remarks</span></span>  

 <span data-ttu-id="4214b-116">Ein Token mit starkem Namen ist die verkürzte Form eines öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="4214b-116">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="4214b-117">Das Token ist ein 64-Bit-Hash, der aus dem öffentlichen Schlüssel, der zum Signieren der Assembly verwendet wird, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4214b-117">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="4214b-118">Das Token ist Teil des starken Namens für die Assembly und kann aus den Assemblymetadaten gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="4214b-118">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="4214b-119">Nachdem der Schlüssel abgerufen und das Token erstellt wurde, sollten Sie die [strongnamefrebuffer](strongnamefreebuffer-function.md) -Funktion zum Freigeben des zugewiesenen Speichers aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="4214b-119">After the key is retrieved and the token is created, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="4214b-120">Wenn die `StrongNameTokenFromAssemblyEx` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4214b-120">If the `StrongNameTokenFromAssemblyEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4214b-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4214b-121">Requirements</span></span>  

 <span data-ttu-id="4214b-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4214b-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4214b-123">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="4214b-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="4214b-124">**Bibliothek:** Als Ressource in mscoree.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4214b-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="4214b-125">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4214b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4214b-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4214b-126">See also</span></span>

- [<span data-ttu-id="4214b-127">StrongNameTokenFromAssemblyEx-Methode</span><span class="sxs-lookup"><span data-stu-id="4214b-127">StrongNameTokenFromAssemblyEx Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="4214b-128">StrongNameTokenFromAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="4214b-128">StrongNameTokenFromAssembly Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="4214b-129">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4214b-129">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

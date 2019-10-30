---
title: StrongNameTokenFromAssembly-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssembly
helpviewer_keywords:
- StrongNameTokenFromAssembly function [.NET Framework strong naming]
ms.assetid: 0a4b47ee-02f6-4a98-864e-a6f11ca3f2d9
topic_type:
- apiref
ms.openlocfilehash: 6b9eca3f2f0267870866874ea27dc65812795f41
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121130"
---
# <a name="strongnametokenfromassembly-function"></a><span data-ttu-id="351d9-102">StrongNameTokenFromAssembly-Funktion</span><span class="sxs-lookup"><span data-stu-id="351d9-102">StrongNameTokenFromAssembly Function</span></span>
<span data-ttu-id="351d9-103">Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei.</span><span class="sxs-lookup"><span data-stu-id="351d9-103">Creates a strong name token from the specified assembly file.</span></span>  
  
 <span data-ttu-id="351d9-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="351d9-104">This function has been deprecated.</span></span> <span data-ttu-id="351d9-105">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="351d9-105">Use the [ICLRStrongName::StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="351d9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="351d9-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="351d9-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="351d9-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="351d9-108">in Der Pfad zur PE-Datei (portable ausführbare Datei) für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="351d9-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="351d9-109">vorgenommen Das zurückgegebene Token für den starken Namen.</span><span class="sxs-lookup"><span data-stu-id="351d9-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="351d9-110">vorgenommen Die Größe (in Bytes) des Tokens für einen starken Namen.</span><span class="sxs-lookup"><span data-stu-id="351d9-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="351d9-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="351d9-111">Return Value</span></span>  
 <span data-ttu-id="351d9-112">`true` nach erfolgreichem Abschluss. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="351d9-112">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="351d9-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="351d9-113">Remarks</span></span>  
 <span data-ttu-id="351d9-114">Ein Token mit starkem Namen ist die verkürzte Form eines öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="351d9-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="351d9-115">Das Token ist ein 64-Bit-Hash, der aus dem öffentlichen Schlüssel, der zum Signieren der Assembly verwendet wird, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="351d9-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="351d9-116">Das Token ist Teil des starken Namens für die Assembly und kann aus den Assemblymetadaten gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="351d9-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="351d9-117">Nachdem das Token erstellt wurde, sollten Sie die [strongnamefrebuffer](strongnamefreebuffer-function.md) -Funktion zum Freigeben des zugewiesenen Speichers aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="351d9-117">After the token is created, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="351d9-118">Wenn die `StrongNameTokenFromAssembly`-Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="351d9-118">If the `StrongNameTokenFromAssembly` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="351d9-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="351d9-119">Requirements</span></span>  
 <span data-ttu-id="351d9-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="351d9-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="351d9-121">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="351d9-121">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="351d9-122">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="351d9-122">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="351d9-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="351d9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="351d9-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="351d9-124">See also</span></span>

- [<span data-ttu-id="351d9-125">StrongNameTokenFromAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="351d9-125">StrongNameTokenFromAssembly Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="351d9-126">StrongNameTokenFromAssemblyEx-Methode</span><span class="sxs-lookup"><span data-stu-id="351d9-126">StrongNameTokenFromAssemblyEx Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="351d9-127">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="351d9-127">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

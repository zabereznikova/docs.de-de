---
title: ICLRStrongName::StrongNameTokenFromAssembly-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName.StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly method [.NET Framework hosting]
- StrongNameTokenFromAssembly method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: fc725afb-b66b-4015-aa44-1c0d1304197f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 455a04c3c5465ec263c5d2131ac8f3c4e34ea610
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a><span data-ttu-id="94133-102">ICLRStrongName::StrongNameTokenFromAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="94133-102">ICLRStrongName::StrongNameTokenFromAssembly Method</span></span>
<span data-ttu-id="94133-103">Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei an.</span><span class="sxs-lookup"><span data-stu-id="94133-103">Creates a strong name token from the specified assembly file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94133-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="94133-104">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="94133-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="94133-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="94133-106">[in] Der Pfad zur Datei (portable Executable)-Datei für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="94133-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="94133-107">[out] Das zurückgegebene strong Name-Token.</span><span class="sxs-lookup"><span data-stu-id="94133-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="94133-108">[out] Die Größe in Bytes, der das Token mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="94133-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94133-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="94133-109">Return Value</span></span>  
 <span data-ttu-id="94133-110">`S_OK`Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="94133-110">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94133-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="94133-111">Remarks</span></span>  
 <span data-ttu-id="94133-112">Ein starker Name-Token ist die Kurzform eines öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="94133-112">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="94133-113">Das Token ist ein 64-Bit-Hash, der aus dem öffentlichen Schlüssel zum Signieren der Assembly erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="94133-113">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="94133-114">Das Token ist ein Teil des starken Namens für die Assembly und kann aus den Metadaten der Assembly gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="94133-114">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="94133-115">Nachdem das Token erstellt wurde, sollten Sie rufen die [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) Methode, um den belegten Speicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="94133-115">After the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94133-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="94133-116">Requirements</span></span>  
 <span data-ttu-id="94133-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94133-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94133-118">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="94133-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="94133-119">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="94133-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94133-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94133-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94133-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94133-121">See Also</span></span>  
 [<span data-ttu-id="94133-122">StrongNameTokenFromAssemblyEx-Methode</span><span class="sxs-lookup"><span data-stu-id="94133-122">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)  
 [<span data-ttu-id="94133-123">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94133-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

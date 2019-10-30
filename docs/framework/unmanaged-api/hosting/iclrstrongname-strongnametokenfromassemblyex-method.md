---
title: ICLRStrongName::StrongNameTokenFromAssemblyEx-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameTokenFromAssemblyEx method [.NET Framework hosting]
ms.assetid: 648ea90e-5e60-40a0-a56a-3e61bf2fba7c
topic_type:
- apiref
ms.openlocfilehash: 71fda266c22c4beb1e1f9c81c84d6c56a0a6110e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092577"
---
# <a name="iclrstrongnamestrongnametokenfromassemblyex-method"></a><span data-ttu-id="634fb-102">ICLRStrongName::StrongNameTokenFromAssemblyEx-Methode</span><span class="sxs-lookup"><span data-stu-id="634fb-102">ICLRStrongName::StrongNameTokenFromAssemblyEx Method</span></span>
<span data-ttu-id="634fb-103">Erstellt ein Token für einen starken Namen aus der angegebenen Assemblydatei und gibt den öffentlichen Schlüssel zurück, den das Token darstellt.</span><span class="sxs-lookup"><span data-stu-id="634fb-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="634fb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="634fb-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="634fb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="634fb-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="634fb-106">in Der Pfad zur PE-Datei (portable ausführbare Datei) für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="634fb-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="634fb-107">vorgenommen Das zurückgegebene Token für den starken Namen.</span><span class="sxs-lookup"><span data-stu-id="634fb-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="634fb-108">vorgenommen Die Größe (in Bytes) des Tokens für einen starken Namen.</span><span class="sxs-lookup"><span data-stu-id="634fb-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="634fb-109">vorgenommen Der zurückgegebene öffentliche Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="634fb-109">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="634fb-110">vorgenommen Die Größe des öffentlichen Schlüssels in Bytes.</span><span class="sxs-lookup"><span data-stu-id="634fb-110">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="634fb-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="634fb-111">Return Value</span></span>  
 <span data-ttu-id="634fb-112">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="634fb-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="634fb-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="634fb-113">Remarks</span></span>  
 <span data-ttu-id="634fb-114">Ein Token mit starkem Namen ist die verkürzte Form eines öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="634fb-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="634fb-115">Das Token ist ein 64-Bit-Hash, der aus dem öffentlichen Schlüssel, der zum Signieren der Assembly verwendet wird, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="634fb-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="634fb-116">Das Token ist Teil des starken Namens für die Assembly und kann aus den Assemblymetadaten gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="634fb-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="634fb-117">Nachdem der Schlüssel abgerufen und das Token erstellt wurde, sollten Sie die [ICLRStrongName:: strongnamefrebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) -Methode abrufen, um den zugeordneten Arbeitsspeicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="634fb-117">After the key is retrieved and the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="634fb-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="634fb-118">Requirements</span></span>  
 <span data-ttu-id="634fb-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="634fb-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="634fb-120">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="634fb-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="634fb-121">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="634fb-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="634fb-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="634fb-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="634fb-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="634fb-123">See also</span></span>

- [<span data-ttu-id="634fb-124">StrongNameTokenFromAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="634fb-124">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="634fb-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="634fb-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

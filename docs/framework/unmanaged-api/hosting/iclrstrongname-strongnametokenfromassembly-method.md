---
title: ICLRStrongName::StrongNameTokenFromAssembly-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a2931c16e13d08c1e3e7d5b62e6583102a1b8cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229250"
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a><span data-ttu-id="f312e-102">ICLRStrongName::StrongNameTokenFromAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="f312e-102">ICLRStrongName::StrongNameTokenFromAssembly Method</span></span>
<span data-ttu-id="f312e-103">Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei.</span><span class="sxs-lookup"><span data-stu-id="f312e-103">Creates a strong name token from the specified assembly file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f312e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f312e-104">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f312e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f312e-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="f312e-106">[in] Der Pfad zu der PE (portable Executable)-Datei für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="f312e-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="f312e-107">[out] Das zurückgegebene strong Name-Token.</span><span class="sxs-lookup"><span data-stu-id="f312e-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="f312e-108">[out] Die Größe in Bytes, der das Token mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="f312e-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f312e-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f312e-109">Return Value</span></span>  
 `S_OK` <span data-ttu-id="f312e-110">Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="f312e-110">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f312e-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f312e-111">Remarks</span></span>  
 <span data-ttu-id="f312e-112">Ein starker Name-Token ist die Kurzform für einen öffentlichen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="f312e-112">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="f312e-113">Das Token ist ein 64-Bit-Hash, der aus dem öffentlichen Schlüssel zum Signieren der Assembly erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f312e-113">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="f312e-114">Das Token ist ein Bestandteil des starken Namens für die Assembly, und Sie können aus den Metadaten der Assembly gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="f312e-114">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="f312e-115">Nachdem das Token erstellt wurde, sollten Sie rufen die [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) Methode, um den belegten Arbeitsspeicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="f312e-115">After the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f312e-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f312e-116">Requirements</span></span>  
 <span data-ttu-id="f312e-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f312e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f312e-118">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f312e-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f312e-119">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f312e-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f312e-120">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="f312e-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f312e-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f312e-121">See also</span></span>

- [<span data-ttu-id="f312e-122">StrongNameTokenFromAssemblyEx-Methode</span><span class="sxs-lookup"><span data-stu-id="f312e-122">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="f312e-123">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f312e-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

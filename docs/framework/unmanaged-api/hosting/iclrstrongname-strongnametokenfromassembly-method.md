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
ms.openlocfilehash: 12677799136e9ca887809e58fba838cb421ea183
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901066"
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a><span data-ttu-id="ec5ed-102">ICLRStrongName::StrongNameTokenFromAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="ec5ed-102">ICLRStrongName::StrongNameTokenFromAssembly Method</span></span>
<span data-ttu-id="ec5ed-103">Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei.</span><span class="sxs-lookup"><span data-stu-id="ec5ed-103">Creates a strong name token from the specified assembly file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec5ed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec5ed-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec5ed-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="ec5ed-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="ec5ed-106">in Der Pfad zur PE-Datei (portable ausführbare Datei) für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="ec5ed-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="ec5ed-107">vorgenommen Das zurückgegebene Token für den starken Namen.</span><span class="sxs-lookup"><span data-stu-id="ec5ed-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="ec5ed-108">vorgenommen Die Größe (in Bytes) des Tokens für einen starken Namen.</span><span class="sxs-lookup"><span data-stu-id="ec5ed-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec5ed-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ec5ed-109">Return Value</span></span>  
 <span data-ttu-id="ec5ed-110">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="ec5ed-110">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec5ed-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ec5ed-111">Remarks</span></span>  
 <span data-ttu-id="ec5ed-112">Ein Token mit starkem Namen ist die verkürzte Form eines öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="ec5ed-112">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="ec5ed-113">Das Token ist ein 64-Bit-Hash, der aus dem öffentlichen Schlüssel, der zum Signieren der Assembly verwendet wird, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ec5ed-113">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="ec5ed-114">Das Token ist Teil des starken Namens für die Assembly und kann aus den Assemblymetadaten gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="ec5ed-114">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="ec5ed-115">Nachdem das Token erstellt wurde, sollten Sie die [ICLRStrongName:: strongnamefrebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) -Methode abrufen, um den zugewiesenen Speicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="ec5ed-115">After the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec5ed-116">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ec5ed-116">Requirements</span></span>  
 <span data-ttu-id="ec5ed-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec5ed-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec5ed-118">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="ec5ed-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ec5ed-119">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ec5ed-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec5ed-120">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec5ed-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec5ed-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec5ed-121">See also</span></span>

- [<span data-ttu-id="ec5ed-122">StrongNameTokenFromAssemblyEx-Methode</span><span class="sxs-lookup"><span data-stu-id="ec5ed-122">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="ec5ed-123">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ec5ed-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

---
title: ICLRStrongName::StrongNameSignatureSize-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameSignatureSize
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameSignatureSize
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureSize method [.NET Framework hosting]
- StrongNameSignatureSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 76d4f93a-5e25-4399-abcc-a1389549481d
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 91a420e520a48f3a33c4ac8c127ccefc064c23bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="e351a-102">ICLRStrongName::StrongNameSignatureSize-Methode</span><span class="sxs-lookup"><span data-stu-id="e351a-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="e351a-103">Gibt die Größe der Signatur des starken Namens.</span><span class="sxs-lookup"><span data-stu-id="e351a-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="e351a-104">Diese Methode wird vom Compiler in der Regel verwendet, um zu bestimmen, wie viel Speicherplatz in der Datei reserviert, beim Erstellen einer Assembly verzögert signiert wird.</span><span class="sxs-lookup"><span data-stu-id="e351a-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e351a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e351a-105">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="e351a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e351a-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="e351a-107">[in] Eine Struktur des Typs [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) , enthält den öffentlichen Teil des Schlüsselpaars verwendet, um die Signatur mit starkem Namen generieren.</span><span class="sxs-lookup"><span data-stu-id="e351a-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="e351a-108">[in] Die Größe in Bytes, der `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="e351a-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="e351a-109">[in] Die Anzahl der Bytes, die zum Speichern der Signatur mit starkem Namen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e351a-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e351a-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e351a-110">Return Value</span></span>  
 <span data-ttu-id="e351a-111">`S_OK`Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="e351a-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e351a-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e351a-112">Requirements</span></span>  
 <span data-ttu-id="e351a-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e351a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e351a-114">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e351a-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e351a-115">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e351a-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e351a-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e351a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e351a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e351a-117">See Also</span></span>  
 [<span data-ttu-id="e351a-118">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e351a-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

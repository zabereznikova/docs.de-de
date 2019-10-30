---
title: ICLRStrongName::StrongNameGetBlobFromImage-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetBlobFromImage method [.NET Framework hosting]
ms.assetid: 0f5a2ec8-e776-4fd8-bda6-937b6834575a
topic_type:
- apiref
ms.openlocfilehash: ad3b151165eb233bd3a4a78d8f4d612a696b7e93
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135097"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a><span data-ttu-id="af623-102">ICLRStrongName::StrongNameGetBlobFromImage-Methode</span><span class="sxs-lookup"><span data-stu-id="af623-102">ICLRStrongName::StrongNameGetBlobFromImage Method</span></span>
<span data-ttu-id="af623-103">Ruft eine binäre Darstellung des Assemblyimages an der angegebenen Speicheradresse ab.</span><span class="sxs-lookup"><span data-stu-id="af623-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af623-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="af623-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af623-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="af623-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="af623-106">in Die Speicheradresse des zugeordneten Assemblymanifests.</span><span class="sxs-lookup"><span data-stu-id="af623-106">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="af623-107">in Die Größe des Bilds in `pbBase`in Byte.</span><span class="sxs-lookup"><span data-stu-id="af623-107">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="af623-108">in Ein Puffer, der die binäre Darstellung des Bilds enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="af623-108">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="af623-109">[in, out] Die angeforderte maximale Größe des `pbBlob`in Byte.</span><span class="sxs-lookup"><span data-stu-id="af623-109">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="af623-110">Bei der Rückgabe die tatsächliche Größe (in Bytes) der `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="af623-110">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af623-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="af623-111">Return Value</span></span>  
 <span data-ttu-id="af623-112">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="af623-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af623-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af623-113">Requirements</span></span>  
 <span data-ttu-id="af623-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af623-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af623-115">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="af623-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="af623-116">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="af623-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af623-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af623-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af623-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af623-118">See also</span></span>

- [<span data-ttu-id="af623-119">StrongNameGetBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="af623-119">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="af623-120">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af623-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

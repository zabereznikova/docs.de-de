---
title: ICLRStrongName::StrongNameGetBlob-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlob
- ICLRStrongName.StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlob
helpviewer_keywords:
- ICLRStrongName::StrongNameGetBlob method [.NET Framework hosting]
- StrongNameGetBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: a24218f8-7196-44be-b7a2-ee9cdd7a85c4
topic_type:
- apiref
ms.openlocfilehash: 9d7f1a71658b53a1b4167c767eb89c873308421b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135131"
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="92dab-102">ICLRStrongName::StrongNameGetBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="92dab-102">ICLRStrongName::StrongNameGetBlob Method</span></span>
<span data-ttu-id="92dab-103">Füllt den angegebenen Puffer mit der binären Darstellung der ausführbaren Datei an der angegebenen Adresse auf.</span><span class="sxs-lookup"><span data-stu-id="92dab-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92dab-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="92dab-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92dab-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="92dab-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="92dab-106">in Ein gültiger Pfad zur ausführbaren Datei, die geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="92dab-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="92dab-107">in Der Puffer, in den die ausführbare Datei geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="92dab-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="92dab-108">[in, out] Die angeforderte maximale Größe des `pbBlob`in Byte.</span><span class="sxs-lookup"><span data-stu-id="92dab-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="92dab-109">Bei der Rückgabe die tatsächliche Größe (in Bytes) der `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="92dab-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="92dab-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="92dab-110">Return Value</span></span>  
 <span data-ttu-id="92dab-111">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="92dab-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92dab-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="92dab-112">Requirements</span></span>  
 <span data-ttu-id="92dab-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92dab-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92dab-114">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="92dab-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="92dab-115">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="92dab-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="92dab-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92dab-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92dab-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92dab-117">See also</span></span>

- [<span data-ttu-id="92dab-118">StrongNameGetBlobFromImage-Methode</span><span class="sxs-lookup"><span data-stu-id="92dab-118">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="92dab-119">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92dab-119">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81e2c59a538bd436606c226855c002cecd501e33
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433665"
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="ccb01-102">ICLRStrongName::StrongNameGetBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="ccb01-102">ICLRStrongName::StrongNameGetBlob Method</span></span>
<span data-ttu-id="ccb01-103">Füllt den angegebenen Puffer mit der binären Darstellung der ausführbaren Datei an der angegebenen Adresse an.</span><span class="sxs-lookup"><span data-stu-id="ccb01-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccb01-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ccb01-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ccb01-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ccb01-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="ccb01-106">[in] Einen gültigen Pfad zur ausführbaren Datei geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="ccb01-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="ccb01-107">[in] Der Puffer, in dem die ausführbare Datei geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="ccb01-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="ccb01-108">[in, out] Die maximale Größe in Bytes, des angeforderten `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="ccb01-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="ccb01-109">Nach der Rückgabe der tatsächlichen Größe in Bytes, der `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="ccb01-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ccb01-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ccb01-110">Return Value</span></span>  
 <span data-ttu-id="ccb01-111">`S_OK` Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="ccb01-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccb01-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ccb01-112">Requirements</span></span>  
 <span data-ttu-id="ccb01-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccb01-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccb01-114">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ccb01-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ccb01-115">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ccb01-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccb01-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccb01-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccb01-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ccb01-117">See Also</span></span>  
 [<span data-ttu-id="ccb01-118">StrongNameGetBlobFromImage-Methode</span><span class="sxs-lookup"><span data-stu-id="ccb01-118">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [<span data-ttu-id="ccb01-119">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ccb01-119">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)

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
ms.openlocfilehash: f93d3f0322de89b2e9ce596329c06b58db9fdcdc
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760302"
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="a327d-102">ICLRStrongName::StrongNameGetBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="a327d-102">ICLRStrongName::StrongNameGetBlob Method</span></span>
<span data-ttu-id="a327d-103">Füllt den angegebenen Puffer mit der binären Darstellung der ausführbaren Datei an der angegebenen Adresse auf.</span><span class="sxs-lookup"><span data-stu-id="a327d-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a327d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a327d-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a327d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a327d-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="a327d-106">in Ein gültiger Pfad zur ausführbaren Datei, die geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="a327d-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="a327d-107">in Der Puffer, in den die ausführbare Datei geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="a327d-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="a327d-108">[in, out] Die angeforderte maximale Größe von in Bytes `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="a327d-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="a327d-109">Bei der Rückgabe die tatsächliche Größe von in Bytes `pbBlob` .</span><span class="sxs-lookup"><span data-stu-id="a327d-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a327d-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a327d-110">Return Value</span></span>  
 <span data-ttu-id="a327d-111">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="a327d-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a327d-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a327d-112">Requirements</span></span>  
 <span data-ttu-id="a327d-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a327d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a327d-114">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="a327d-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a327d-115">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a327d-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a327d-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a327d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a327d-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a327d-117">See also</span></span>

- [<span data-ttu-id="a327d-118">StrongNameGetBlobFromImage-Methode</span><span class="sxs-lookup"><span data-stu-id="a327d-118">StrongNameGetBlobFromImage Method</span></span>](iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="a327d-119">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a327d-119">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

---
title: ICLRStrongName::StrongNameKeyInstall-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyInstall
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyInstall method [.NET Framework hosting]
- StrongNameKeyInstall method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5c15cf3b-164c-49d1-8e57-e42949d55acf
topic_type:
- apiref
ms.openlocfilehash: 7e0c689dad0c288e3af3a3d64ee1bba1c44053c1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674527"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="56e3d-102">ICLRStrongName::StrongNameKeyInstall-Methode</span><span class="sxs-lookup"><span data-stu-id="56e3d-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>

<span data-ttu-id="56e3d-103">Importiert ein öffentliches/privates Schlüsselpaar in einen Container.</span><span class="sxs-lookup"><span data-stu-id="56e3d-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56e3d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="56e3d-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56e3d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="56e3d-105">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="56e3d-106">in Der Name des Schlüssel Containers.</span><span class="sxs-lookup"><span data-stu-id="56e3d-106">[in] The name of the key container.</span></span> <span data-ttu-id="56e3d-107">`wszKeyContainer` muss eine nicht leere Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="56e3d-107">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="56e3d-108">in Das binäre Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="56e3d-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="56e3d-109">in Die Größe von in Bytes `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="56e3d-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56e3d-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="56e3d-110">Return Value</span></span>  

 <span data-ttu-id="56e3d-111">`S_OK` , wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="56e3d-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56e3d-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="56e3d-112">Remarks</span></span>  

 <span data-ttu-id="56e3d-113">Verwenden Sie die [ICLRStrongName:: StrongNameKeyDelete](iclrstrongname-strongnamekeydelete-method.md) -Methode, um den Schlüssel Container zu löschen.</span><span class="sxs-lookup"><span data-stu-id="56e3d-113">Use the [ICLRStrongName::StrongNameKeyDelete](iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56e3d-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="56e3d-114">Requirements</span></span>  

 <span data-ttu-id="56e3d-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56e3d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56e3d-116">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="56e3d-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="56e3d-117">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="56e3d-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="56e3d-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56e3d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56e3d-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56e3d-119">See also</span></span>

- [<span data-ttu-id="56e3d-120">StrongNameKeyDelete-Methode</span><span class="sxs-lookup"><span data-stu-id="56e3d-120">StrongNameKeyDelete Method</span></span>](iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="56e3d-121">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="56e3d-121">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)

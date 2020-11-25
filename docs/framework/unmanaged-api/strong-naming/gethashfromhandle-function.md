---
title: GetHashFromHandle-Funktion
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
ms.openlocfilehash: 904dcb707e704cfec2dba4e6587f7e3acaf7b538
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732330"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="5633e-102">GetHashFromHandle-Funktion</span><span class="sxs-lookup"><span data-stu-id="5633e-102">GetHashFromHandle Function</span></span>

<span data-ttu-id="5633e-103">Generiert einen Hashwert für den Inhalt der Datei mit dem angegebenen Dateihandle unter Verwendung des angegebenen Hashalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="5633e-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="5633e-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="5633e-104">This function has been deprecated.</span></span> <span data-ttu-id="5633e-105">Verwenden Sie stattdessen die [ICLRStrongName:: GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="5633e-105">Use the [ICLRStrongName::GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5633e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5633e-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5633e-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="5633e-107">Parameters</span></span>  

 `hFile`  
 <span data-ttu-id="5633e-108">in Das Handle der Datei, für die der Hashwert verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5633e-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="5633e-109">[in, out] Eine-Konstante, die den Hash Algorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="5633e-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="5633e-110">Verwenden Sie 0 (null) für den Standard Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="5633e-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="5633e-111">vorgenommen Der zurückgegebene Hash Puffer.</span><span class="sxs-lookup"><span data-stu-id="5633e-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="5633e-112">in Die angeforderte maximale Größe von `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="5633e-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="5633e-113">vorgenommen Die Größe (in Bytes) des zurückgegebenen `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="5633e-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5633e-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5633e-114">Requirements</span></span>  

 <span data-ttu-id="5633e-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5633e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5633e-116">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="5633e-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5633e-117">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5633e-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5633e-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5633e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5633e-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5633e-119">See also</span></span>

- [<span data-ttu-id="5633e-120">GetHashFromHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="5633e-120">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="5633e-121">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5633e-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

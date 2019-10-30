---
title: GetHashFromAssemblyFile-Funktion
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
ms.openlocfilehash: 866b34acae333f043d8e13f4d0ebd55f32046334
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140726"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="d4825-102">GetHashFromAssemblyFile-Funktion</span><span class="sxs-lookup"><span data-stu-id="d4825-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="d4825-103">Ruft einen Hash der angegebenen Assemblydatei unter Verwendung des angegebenen Hashalgorithmus ab.</span><span class="sxs-lookup"><span data-stu-id="d4825-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="d4825-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="d4825-104">This function has been deprecated.</span></span> <span data-ttu-id="d4825-105">Verwenden Sie stattdessen die [ICLRStrongName:: GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="d4825-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4825-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4825-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4825-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="d4825-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="d4825-108">in Der Pfad zu der Datei, für die der Hashwert verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d4825-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="d4825-109">[in, out] Eine-Konstante, die den Hash Algorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="d4825-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="d4825-110">Verwenden Sie 0 für den Standard Hash Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="d4825-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="d4825-111">vorgenommen Der zurückgegebene Hash Puffer.</span><span class="sxs-lookup"><span data-stu-id="d4825-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="d4825-112">in Die angeforderte maximale Größe `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d4825-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="d4825-113">vorgenommen Die zurückgegebene Größe (in Bytes) der `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d4825-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4825-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d4825-114">Requirements</span></span>  
 <span data-ttu-id="d4825-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4825-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4825-116">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="d4825-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d4825-117">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d4825-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d4825-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4825-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4825-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4825-119">See also</span></span>

- [<span data-ttu-id="d4825-120">GetHashFromAssemblyFile-Methode</span><span class="sxs-lookup"><span data-stu-id="d4825-120">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="d4825-121">GetHashFromAssemblyFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="d4825-121">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="d4825-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d4825-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

---
title: GetHashFromBlob-Funktion
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59b4df08157ce14a58393e54b671e8f41b8998ed
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799232"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="8abfe-102">GetHashFromBlob-Funktion</span><span class="sxs-lookup"><span data-stu-id="8abfe-102">GetHashFromBlob Function</span></span>

<span data-ttu-id="8abfe-103">Ruft einen Hash der Assembly unter der angegebenen Speicheradresse unter Verwendung des angegebenen Hashalgorithmus ab.</span><span class="sxs-lookup"><span data-stu-id="8abfe-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>

<span data-ttu-id="8abfe-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="8abfe-104">This function has been deprecated.</span></span> <span data-ttu-id="8abfe-105">Verwenden Sie stattdessen die [ICLRStrongName:: GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="8abfe-105">Use the [ICLRStrongName::GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="8abfe-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8abfe-106">Syntax</span></span>

```cpp
HRESULT GetHashFromBlob (
    [in]  BYTE    *pbBlob,
    [in]  DWORD   cchBlob,
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE    *pbHash,
    [in]  DWORD   cchHash,
    [out] DWORD   *pchHash
);
```

## <a name="parameters"></a><span data-ttu-id="8abfe-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="8abfe-107">Parameters</span></span>

`pbBlob`\
<span data-ttu-id="8abfe-108">in Ein Zeiger auf die Adresse des Speicherblocks, für den der Hashwert verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8abfe-108">[in] A pointer to the address of the memory block to be hashed.</span></span>

`cchBlob`\
<span data-ttu-id="8abfe-109">in Die Länge des Speicherblocks in Bytes.</span><span class="sxs-lookup"><span data-stu-id="8abfe-109">[in] The length, in bytes, of the memory block.</span></span>

`piHashAlg`\
<span data-ttu-id="8abfe-110">[in, out] Eine-Konstante, die den Hash Algorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="8abfe-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="8abfe-111">Verwenden Sie 0 (null) für den Standard Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="8abfe-111">Use zero for the default algorithm.</span></span>

`pbHash`\
<span data-ttu-id="8abfe-112">vorgenommen Der zurückgegebene Hash Puffer.</span><span class="sxs-lookup"><span data-stu-id="8abfe-112">[out] The returned hash buffer.</span></span>

`cchHash`\
<span data-ttu-id="8abfe-113">in Die angeforderte maximale Größe `pbHash`von.</span><span class="sxs-lookup"><span data-stu-id="8abfe-113">[in] The requested maximum size of `pbHash`.</span></span>

`pchHash`\
<span data-ttu-id="8abfe-114">vorgenommen Die Größe (in Bytes) des zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="8abfe-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>

## <a name="requirements"></a><span data-ttu-id="8abfe-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8abfe-115">Requirements</span></span>

<span data-ttu-id="8abfe-116">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8abfe-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="8abfe-117">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="8abfe-117">**Header:** StrongName.h</span></span>

<span data-ttu-id="8abfe-118">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8abfe-118">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="8abfe-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8abfe-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8abfe-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8abfe-120">See also</span></span>

- [<span data-ttu-id="8abfe-121">GetHashFromBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="8abfe-121">GetHashFromBlob Method</span></span>](../hosting/iclrstrongname-gethashfromblob-method.md)
- [<span data-ttu-id="8abfe-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8abfe-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

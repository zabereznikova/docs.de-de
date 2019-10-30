---
title: GetHashFromFileW-Funktion
ms.date: 03/30/2017
api_name:
- GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type:
- apiref
ms.openlocfilehash: db6f39119d143d27c0d3a80a9c65565d4dfd0d39
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140675"
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="68118-102">GetHashFromFileW-Funktion</span><span class="sxs-lookup"><span data-stu-id="68118-102">GetHashFromFileW Function</span></span>
<span data-ttu-id="68118-103">Generiert einen Hashwert für den Inhalt der durch eine Unicode-Zeichenfolge angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="68118-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="68118-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="68118-104">This function has been deprecated.</span></span> <span data-ttu-id="68118-105">Verwenden Sie stattdessen die [ICLRStrongName:: GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="68118-105">Use the [ICLRStrongName::GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68118-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="68118-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="68118-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="68118-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="68118-108">in Der Unicode-Name der zu hashenden Datei.</span><span class="sxs-lookup"><span data-stu-id="68118-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="68118-109">[in, out] Der Algorithmus, der beim Erzeugen des Hashwerts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="68118-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="68118-110">Gültige Algorithmen sind die, die von der Win32-CryptoAPI definiert werden.</span><span class="sxs-lookup"><span data-stu-id="68118-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="68118-111">Wenn `piHashAlg` auf 0 festgelegt ist, wird der Standard Algorithmus CALG_SHA-1 verwendet.</span><span class="sxs-lookup"><span data-stu-id="68118-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="68118-112">vorgenommen Ein Bytearray, das den generierten Hash enthält.</span><span class="sxs-lookup"><span data-stu-id="68118-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="68118-113">in Die maximale Größe des Puffers, auf den `pbHash`zeigt.</span><span class="sxs-lookup"><span data-stu-id="68118-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="68118-114">vorgenommen Die Größe `pbHash`in Byte.</span><span class="sxs-lookup"><span data-stu-id="68118-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68118-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="68118-115">Remarks</span></span>  
 <span data-ttu-id="68118-116">Diese Funktion ist mit [GetHashFromFile](gethashfromfile-function.md)identisch, mit der Ausnahme, dass die Dateinamen Spezifikation anstelle von ANSI Unicode ist.</span><span class="sxs-lookup"><span data-stu-id="68118-116">This function is the same as [GetHashFromFile](gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68118-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="68118-117">Requirements</span></span>  
 <span data-ttu-id="68118-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68118-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68118-119">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="68118-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="68118-120">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="68118-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="68118-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68118-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68118-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68118-122">See also</span></span>

- [<span data-ttu-id="68118-123">GetHashFromFileW-Methode</span><span class="sxs-lookup"><span data-stu-id="68118-123">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="68118-124">GetHashFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="68118-124">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="68118-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68118-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

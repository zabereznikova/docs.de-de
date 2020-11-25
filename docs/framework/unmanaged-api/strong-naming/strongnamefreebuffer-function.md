---
title: StrongNameFreeBuffer-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
ms.openlocfilehash: d93bda046a79dbdec2195eee48fefc1e5538b2e4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732254"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="c4321-102">StrongNameFreeBuffer-Funktion</span><span class="sxs-lookup"><span data-stu-id="c4321-102">StrongNameFreeBuffer Function</span></span>

<span data-ttu-id="c4321-103">Gibt Speicher frei, der bei einem vorherigen Aufruf einer Funktion für starke Namen wie [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) oder [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md) zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="c4321-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="c4321-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="c4321-104">This function has been deprecated.</span></span> <span data-ttu-id="c4321-105">Verwenden Sie stattdessen die [ICLRStrongName:: strongnamefrebuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="c4321-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4321-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4321-106">Syntax</span></span>  
  
```cpp  
VOID StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4321-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4321-107">Parameters</span></span>  

 `pbMemory`  
 <span data-ttu-id="c4321-108">in Ein Zeiger auf den frei verfügbaren Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="c4321-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4321-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c4321-109">Requirements</span></span>  

 <span data-ttu-id="c4321-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4321-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4321-111">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="c4321-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c4321-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c4321-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c4321-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4321-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4321-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c4321-114">See also</span></span>

- [<span data-ttu-id="c4321-115">StrongNameFreeBuffer-Methode</span><span class="sxs-lookup"><span data-stu-id="c4321-115">StrongNameFreeBuffer Method</span></span>](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="c4321-116">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4321-116">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

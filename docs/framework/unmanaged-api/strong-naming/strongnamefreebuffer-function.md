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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 639664c6ce5714b554f30bff2569a12bf48d1671
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799124"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="70911-102">StrongNameFreeBuffer-Funktion</span><span class="sxs-lookup"><span data-stu-id="70911-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="70911-103">Gibt Speicher frei, der bei einem vorherigen Aufruf einer Funktion für starke Namen wie [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) oder [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md) zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="70911-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="70911-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="70911-104">This function has been deprecated.</span></span> <span data-ttu-id="70911-105">Verwenden Sie stattdessen die [ICLRStrongName:: strongnamefrebuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="70911-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70911-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="70911-106">Syntax</span></span>  
  
```cpp  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70911-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="70911-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="70911-108">in Ein Zeiger auf den frei verfügbaren Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="70911-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70911-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="70911-109">Requirements</span></span>  
 <span data-ttu-id="70911-110">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70911-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70911-111">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="70911-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="70911-112">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="70911-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="70911-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70911-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70911-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70911-114">See also</span></span>

- [<span data-ttu-id="70911-115">StrongNameFreeBuffer-Methode</span><span class="sxs-lookup"><span data-stu-id="70911-115">StrongNameFreeBuffer Method</span></span>](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="70911-116">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="70911-116">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)

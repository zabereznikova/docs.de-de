---
title: ISymUnmanagedReader::GetMethodVersion-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethodVersion
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5b57407cb12e4315b6a144d157a201f857614d9f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="4e58f-102">ISymUnmanagedReader::GetMethodVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="4e58f-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="4e58f-103">Ruft die Methodenversion ab.</span><span class="sxs-lookup"><span data-stu-id="4e58f-103">Gets the method version.</span></span> <span data-ttu-id="4e58f-104">Die Methodenversion beginnt mit 1 und erhöht, wird jedes Mal, wenn die Methode erneut kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="4e58f-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="4e58f-105">Neukompilierung möglich, ohne Änderungen an die Methode.</span><span class="sxs-lookup"><span data-stu-id="4e58f-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e58f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e58f-106">Syntax</span></span>  
  
```  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e58f-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="4e58f-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="4e58f-108">[in] Die Methode für die die Version zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4e58f-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="4e58f-109">[out] Ein Zeiger auf eine Variable, die Methodenversion empfängt.</span><span class="sxs-lookup"><span data-stu-id="4e58f-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e58f-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4e58f-110">Return Value</span></span>  
 <span data-ttu-id="4e58f-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="4e58f-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e58f-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4e58f-112">Requirements</span></span>  
 <span data-ttu-id="4e58f-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4e58f-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e58f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e58f-114">See Also</span></span>  
 [<span data-ttu-id="4e58f-115">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e58f-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

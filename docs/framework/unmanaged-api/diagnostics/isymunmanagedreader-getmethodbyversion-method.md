---
title: ISymUnmanagedReader::GetMethodByVersion-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedReader.GetMethodByVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 810cc5cda9de7c61c1b23d1574ceff19bfec3bc8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="69cb3-102">ISymUnmanagedReader::GetMethodByVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="69cb3-102">ISymUnmanagedReader::GetMethodByVersion Method</span></span>
<span data-ttu-id="69cb3-103">Ruft ein Methodenobjekt des Symbolreaders, erhält ein Methodentoken und eine Versionsnummer für bearbeiten und kopieren.</span><span class="sxs-lookup"><span data-stu-id="69cb3-103">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="69cb3-104">Versionsnummern beginnen bei 1 und werden jedes Mal inkrementiert, wenn die Methode als Ergebnis eines Vorgangs bearbeiten und kopieren geändert wird.</span><span class="sxs-lookup"><span data-stu-id="69cb3-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69cb3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="69cb3-105">Syntax</span></span>  
  
```  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69cb3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="69cb3-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="69cb3-107">[in] Das Token der Methode.</span><span class="sxs-lookup"><span data-stu-id="69cb3-107">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="69cb3-108">[in] Die Methodenversion.</span><span class="sxs-lookup"><span data-stu-id="69cb3-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="69cb3-109">[out] Ein Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="69cb3-109">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="69cb3-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="69cb3-110">Return Value</span></span>  
 <span data-ttu-id="69cb3-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="69cb3-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69cb3-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="69cb3-112">Requirements</span></span>  
 <span data-ttu-id="69cb3-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="69cb3-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69cb3-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69cb3-114">See Also</span></span>  
 [<span data-ttu-id="69cb3-115">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="69cb3-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

---
title: ISymUnmanagedReader::GetMethodByVersion-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethodByVersion
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ba4c3ae5b1883c3113d205eab44375cbd1034c29
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="54e82-102">ISymUnmanagedReader::GetMethodByVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="54e82-102">ISymUnmanagedReader::GetMethodByVersion Method</span></span>
<span data-ttu-id="54e82-103">Ruft ein Methodenobjekt des Symbolreaders, erhält ein Methodentoken und eine Versionsnummer für bearbeiten und kopieren.</span><span class="sxs-lookup"><span data-stu-id="54e82-103">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="54e82-104">Versionsnummern beginnen bei 1 und werden jedes Mal inkrementiert, wenn die Methode als Ergebnis eines Vorgangs bearbeiten und kopieren geändert wird.</span><span class="sxs-lookup"><span data-stu-id="54e82-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54e82-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="54e82-105">Syntax</span></span>  
  
```  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54e82-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="54e82-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="54e82-107">[in] Das Token der Methode.</span><span class="sxs-lookup"><span data-stu-id="54e82-107">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="54e82-108">[in] Die Methodenversion.</span><span class="sxs-lookup"><span data-stu-id="54e82-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="54e82-109">[out] Ein Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="54e82-109">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54e82-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="54e82-110">Return Value</span></span>  
 <span data-ttu-id="54e82-111">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="54e82-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54e82-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="54e82-112">Requirements</span></span>  
 <span data-ttu-id="54e82-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="54e82-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54e82-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54e82-114">See Also</span></span>  
 [<span data-ttu-id="54e82-115">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="54e82-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

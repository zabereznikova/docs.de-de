---
title: ISymUnmanagedDocument::GetSourceLength-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetSourceLength
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetSourceLength
helpviewer_keywords:
- GetSourceLength method [.NET Framework debugging]
- ISymUnmanagedDocument::GetSourceLength method [.NET Framework debugging]
ms.assetid: e087dbbb-f4fb-4fbe-8292-e4f1a14d0df2
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61d9bd99a08f428993f38fb5b6889c9659607782
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="8a051-102">ISymUnmanagedDocument::GetSourceLength-Methode</span><span class="sxs-lookup"><span data-stu-id="8a051-102">ISymUnmanagedDocument::GetSourceLength Method</span></span>
<span data-ttu-id="8a051-103">Ruft die Länge der eingebetteten Quelle in Byte ab.</span><span class="sxs-lookup"><span data-stu-id="8a051-103">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a051-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a051-104">Syntax</span></span>  
  
```  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a051-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8a051-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="8a051-106">[out] Ein Zeiger auf eine Variable, die die Länge der eingebetteten Quelle in Byte angibt.</span><span class="sxs-lookup"><span data-stu-id="8a051-106">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a051-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8a051-107">Return Value</span></span>  
 <span data-ttu-id="8a051-108">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="8a051-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a051-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a051-109">See Also</span></span>  
 [<span data-ttu-id="8a051-110">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8a051-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

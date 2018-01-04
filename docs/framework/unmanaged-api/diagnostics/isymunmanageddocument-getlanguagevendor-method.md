---
title: ISymUnmanagedDocument::GetLanguageVendor-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetLanguageVendor
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc0d05e3d0536f596fc305e32863a39d27a77fe9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="65893-102">ISymUnmanagedDocument::GetLanguageVendor-Methode</span><span class="sxs-lookup"><span data-stu-id="65893-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="65893-103">Ruft den Compilerhersteller dieses Dokuments ab.</span><span class="sxs-lookup"><span data-stu-id="65893-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65893-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="65893-104">Syntax</span></span>  
  
```  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65893-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="65893-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="65893-106">[out] Ein Zeiger auf eine Variable, die den Compilerhersteller empfängt.</span><span class="sxs-lookup"><span data-stu-id="65893-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65893-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="65893-107">Return Value</span></span>  
 <span data-ttu-id="65893-108">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="65893-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65893-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65893-109">See Also</span></span>  
 [<span data-ttu-id="65893-110">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65893-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

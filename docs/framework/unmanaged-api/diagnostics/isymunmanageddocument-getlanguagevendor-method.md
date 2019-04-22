---
title: ISymUnmanagedDocument::GetLanguageVendor-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguageVendor
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cd01dcbd45ecae84ccccffb510c20f580ae8c598
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080808"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="33c02-102">ISymUnmanagedDocument::GetLanguageVendor-Methode</span><span class="sxs-lookup"><span data-stu-id="33c02-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="33c02-103">Ruft den Compilerhersteller des in diesem Dokument ab.</span><span class="sxs-lookup"><span data-stu-id="33c02-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33c02-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="33c02-104">Syntax</span></span>  
  
```  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33c02-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="33c02-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="33c02-106">[out] Ein Zeiger auf eine Variable, die den Compilerhersteller empfängt.</span><span class="sxs-lookup"><span data-stu-id="33c02-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33c02-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="33c02-107">Return Value</span></span>  
 <span data-ttu-id="33c02-108">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="33c02-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33c02-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33c02-109">See also</span></span>

- [<span data-ttu-id="33c02-110">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33c02-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

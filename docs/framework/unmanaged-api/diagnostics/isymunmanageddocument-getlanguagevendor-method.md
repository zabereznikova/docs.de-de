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
ms.openlocfilehash: 0a6830f47d5cac2cf9c84144c18486489b0ec581
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424530"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="118cd-102">ISymUnmanagedDocument::GetLanguageVendor-Methode</span><span class="sxs-lookup"><span data-stu-id="118cd-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="118cd-103">Ruft den Compilerhersteller dieses Dokuments ab.</span><span class="sxs-lookup"><span data-stu-id="118cd-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="118cd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="118cd-104">Syntax</span></span>  
  
```  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="118cd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="118cd-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="118cd-106">[out] Ein Zeiger auf eine Variable, die den Compilerhersteller empfängt.</span><span class="sxs-lookup"><span data-stu-id="118cd-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="118cd-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="118cd-107">Return Value</span></span>  
 <span data-ttu-id="118cd-108">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="118cd-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="118cd-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="118cd-109">See Also</span></span>  
 [<span data-ttu-id="118cd-110">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="118cd-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

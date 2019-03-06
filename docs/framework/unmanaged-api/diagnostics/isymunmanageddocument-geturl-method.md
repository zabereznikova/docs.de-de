---
title: ISymUnmanagedDocument::GetURL-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetURL
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetURL
helpviewer_keywords:
- GetURL method [.NET Framework debugging]
- ISymUnmanagedDocument::GetURL method [.NET Framework debugging]
ms.assetid: 60600178-c2b5-4cab-b3a5-f0f61acebaf1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b4e501629198c9bac627979547a5603d3e7866a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57467124"
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="fc518-102">ISymUnmanagedDocument::GetURL-Methode</span><span class="sxs-lookup"><span data-stu-id="fc518-102">ISymUnmanagedDocument::GetURL Method</span></span>
<span data-ttu-id="fc518-103">Gibt die URL (uniform Resource Locator) für dieses Dokument zurück.</span><span class="sxs-lookup"><span data-stu-id="fc518-103">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc518-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc518-104">Syntax</span></span>  
  
```  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc518-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fc518-105">Parameters</span></span>  
 `cchUrl`  
 <span data-ttu-id="fc518-106">[in] Die Größe des `szURL`-Puffers in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="fc518-106">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="fc518-107">[out] Ein Zeiger auf eine Variable, die Größe der URL, einschließlich der null-Terminierung empfängt.</span><span class="sxs-lookup"><span data-stu-id="fc518-107">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="fc518-108">[out] Der Puffer mit der URL.</span><span class="sxs-lookup"><span data-stu-id="fc518-108">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc518-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fc518-109">Return Value</span></span>  
 <span data-ttu-id="fc518-110">S_OK, wenn die Methode erfolgreich ist; andernfalls ein Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="fc518-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc518-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc518-111">See also</span></span>
- [<span data-ttu-id="fc518-112">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fc518-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

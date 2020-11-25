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
ms.openlocfilehash: c862b6d3bfa415b622b68898db1ff30c6759e8f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726937"
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="087fe-102">ISymUnmanagedDocument::GetURL-Methode</span><span class="sxs-lookup"><span data-stu-id="087fe-102">ISymUnmanagedDocument::GetURL Method</span></span>

<span data-ttu-id="087fe-103">Gibt die URL (Uniform Resource Serverlocatorpunkt) für dieses Dokument zurück.</span><span class="sxs-lookup"><span data-stu-id="087fe-103">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="087fe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="087fe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="087fe-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="087fe-105">Parameters</span></span>  

 `cchUrl`  
 <span data-ttu-id="087fe-106">[in] Die Größe des `szURL`-Puffers in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="087fe-106">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="087fe-107">vorgenommen Ein Zeiger auf eine Variable, die die Größe der URL erhält, einschließlich der NULL-Beendigung.</span><span class="sxs-lookup"><span data-stu-id="087fe-107">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="087fe-108">vorgenommen Der Puffer, der die URL enthält.</span><span class="sxs-lookup"><span data-stu-id="087fe-108">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="087fe-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="087fe-109">Return Value</span></span>  

 <span data-ttu-id="087fe-110">S_OK, wenn die Methode erfolgreich ist. andernfalls ein Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="087fe-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="087fe-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="087fe-111">See also</span></span>

- [<span data-ttu-id="087fe-112">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="087fe-112">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)

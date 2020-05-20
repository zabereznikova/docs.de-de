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
ms.openlocfilehash: 3685707f1983ffec413e9cea2df5034ac53f643a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615591"
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="f5ad5-102">ISymUnmanagedDocument::GetURL-Methode</span><span class="sxs-lookup"><span data-stu-id="f5ad5-102">ISymUnmanagedDocument::GetURL Method</span></span>
<span data-ttu-id="f5ad5-103">Gibt die URL (Uniform Resource Serverlocatorpunkt) für dieses Dokument zurück.</span><span class="sxs-lookup"><span data-stu-id="f5ad5-103">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5ad5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5ad5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5ad5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f5ad5-105">Parameters</span></span>  
 `cchUrl`  
 <span data-ttu-id="f5ad5-106">[in] Die Größe des `szURL`-Puffers in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f5ad5-106">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="f5ad5-107">vorgenommen Ein Zeiger auf eine Variable, die die Größe der URL erhält, einschließlich der NULL-Beendigung.</span><span class="sxs-lookup"><span data-stu-id="f5ad5-107">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="f5ad5-108">vorgenommen Der Puffer, der die URL enthält.</span><span class="sxs-lookup"><span data-stu-id="f5ad5-108">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5ad5-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f5ad5-109">Return Value</span></span>  
 <span data-ttu-id="f5ad5-110">S_OK, wenn die Methode erfolgreich ist. andernfalls ein Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="f5ad5-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5ad5-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5ad5-111">See also</span></span>

- [<span data-ttu-id="f5ad5-112">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5ad5-112">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)

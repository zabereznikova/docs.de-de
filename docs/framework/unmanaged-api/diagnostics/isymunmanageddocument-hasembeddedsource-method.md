---
title: ISymUnmanagedDocument::HasEmbeddedSource-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.HasEmbeddedSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type:
- apiref
ms.openlocfilehash: 09bc0f87cd35f12a15566fb525c2ce42990ac69b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688197"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="7abdd-102">ISymUnmanagedDocument::HasEmbeddedSource-Methode</span><span class="sxs-lookup"><span data-stu-id="7abdd-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>

<span data-ttu-id="7abdd-103">Gibt zurück, `true` Wenn das Dokument in die Debugsymbole eingebettet ist; andernfalls wird zurückgegeben `false` .</span><span class="sxs-lookup"><span data-stu-id="7abdd-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7abdd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7abdd-104">Syntax</span></span>  
  
```cpp  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7abdd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7abdd-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="7abdd-106">vorgenommen Ein Zeiger auf eine Variable, die angibt, ob das Dokument in die Debugsymbole eingebettet ist.</span><span class="sxs-lookup"><span data-stu-id="7abdd-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7abdd-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7abdd-107">Return Value</span></span>  

 <span data-ttu-id="7abdd-108">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="7abdd-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7abdd-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7abdd-109">See also</span></span>

- [<span data-ttu-id="7abdd-110">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7abdd-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)

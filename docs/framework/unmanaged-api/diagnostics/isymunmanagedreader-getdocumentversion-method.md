---
title: ISymUnmanagedReader::GetDocumentVersion-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocumentVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type:
- apiref
ms.openlocfilehash: fc38c167b47ea72c7bc7ad81074f9cb1a0d217d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707567"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="6e4de-102">ISymUnmanagedReader::GetDocumentVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="6e4de-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>

<span data-ttu-id="6e4de-103">Ruft die angegebene Version des angegebenen Dokuments ab.</span><span class="sxs-lookup"><span data-stu-id="6e4de-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="6e4de-104">Die Dokument Version beginnt bei 1 und wird jedes Mal um 1 erhöht, wenn das Dokument mithilfe der [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) -Methode aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="6e4de-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="6e4de-105">Wenn der- `pbCurrent` Parameter ist `true` , ist dies die neueste Version des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="6e4de-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e4de-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e4de-106">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e4de-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="6e4de-107">Parameters</span></span>  

 `pDoc`  
 <span data-ttu-id="6e4de-108">in Das angegebene Dokument.</span><span class="sxs-lookup"><span data-stu-id="6e4de-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="6e4de-109">vorgenommen Ein Zeiger auf eine Variable, die die Version des angegebenen Dokuments empfängt.</span><span class="sxs-lookup"><span data-stu-id="6e4de-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="6e4de-110">vorgenommen Ein Zeiger auf eine Variable, die empfängt `true` , wenn dies die neueste Version des Dokuments ist, oder, `false` Wenn Sie nicht die neueste Version ist.</span><span class="sxs-lookup"><span data-stu-id="6e4de-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e4de-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6e4de-111">Return Value</span></span>  

 <span data-ttu-id="6e4de-112">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="6e4de-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e4de-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6e4de-113">Requirements</span></span>  

 <span data-ttu-id="6e4de-114">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="6e4de-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e4de-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e4de-115">See also</span></span>

- [<span data-ttu-id="6e4de-116">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e4de-116">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)

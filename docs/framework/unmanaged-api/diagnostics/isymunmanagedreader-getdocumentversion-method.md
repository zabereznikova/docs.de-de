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
ms.openlocfilehash: c2cc541b2a78f16d5ca6b19405794faa825a9d72
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615032"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="adbbd-102">ISymUnmanagedReader::GetDocumentVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="adbbd-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>
<span data-ttu-id="adbbd-103">Ruft die angegebene Version des angegebenen Dokuments ab.</span><span class="sxs-lookup"><span data-stu-id="adbbd-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="adbbd-104">Die Dokument Version beginnt bei 1 und wird jedes Mal um 1 erhöht, wenn das Dokument mithilfe der [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) -Methode aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="adbbd-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="adbbd-105">Wenn der- `pbCurrent` Parameter ist `true` , ist dies die neueste Version des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="adbbd-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adbbd-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="adbbd-106">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="adbbd-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="adbbd-107">Parameters</span></span>  
 `pDoc`  
 <span data-ttu-id="adbbd-108">in Das angegebene Dokument.</span><span class="sxs-lookup"><span data-stu-id="adbbd-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="adbbd-109">vorgenommen Ein Zeiger auf eine Variable, die die Version des angegebenen Dokuments empfängt.</span><span class="sxs-lookup"><span data-stu-id="adbbd-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="adbbd-110">vorgenommen Ein Zeiger auf eine Variable, die empfängt `true` , wenn dies die neueste Version des Dokuments ist, oder, `false` Wenn Sie nicht die neueste Version ist.</span><span class="sxs-lookup"><span data-stu-id="adbbd-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="adbbd-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="adbbd-111">Return Value</span></span>  
 <span data-ttu-id="adbbd-112">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="adbbd-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adbbd-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="adbbd-113">Requirements</span></span>  
 <span data-ttu-id="adbbd-114">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="adbbd-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adbbd-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="adbbd-115">See also</span></span>

- [<span data-ttu-id="adbbd-116">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="adbbd-116">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)

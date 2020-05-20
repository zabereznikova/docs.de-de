---
title: ISymUnmanagedReader::GetMethodFromDocumentPosition-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodFromDocumentPosition
helpviewer_keywords:
- GetMethodFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 55773dbc-9053-46e3-8a3c-86caa9d91fb4
topic_type:
- apiref
ms.openlocfilehash: 8015056b110fe8a5b5122b1bc81143980b780047
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614980"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="d7b4c-102">ISymUnmanagedReader::GetMethodFromDocumentPosition-Methode</span><span class="sxs-lookup"><span data-stu-id="d7b4c-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>
<span data-ttu-id="d7b4c-103">Gibt die Methode zurück, die den Breakpoint an der angegebenen Position in einem Dokument enthält.</span><span class="sxs-lookup"><span data-stu-id="d7b4c-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7b4c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7b4c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7b4c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d7b4c-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="d7b4c-106">in Das angegebene Dokument.</span><span class="sxs-lookup"><span data-stu-id="d7b4c-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="d7b4c-107">in Die Zeile des angegebenen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="d7b4c-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="d7b4c-108">in Die Spalte des angegebenen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="d7b4c-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="d7b4c-109">vorgenommen Ein Zeiger auf die Adresse eines [ISymUnmanagedMethod-Schnittstellen](isymunmanagedmethod-interface.md) Objekts, das die Methode darstellt, die den Breakpoint enthält.</span><span class="sxs-lookup"><span data-stu-id="d7b4c-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7b4c-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d7b4c-110">Return Value</span></span>  
 <span data-ttu-id="d7b4c-111">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="d7b4c-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7b4c-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d7b4c-112">Requirements</span></span>  
 <span data-ttu-id="d7b4c-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="d7b4c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7b4c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7b4c-114">See also</span></span>

- [<span data-ttu-id="d7b4c-115">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d7b4c-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)

---
title: ISymUnmanagedReader::GetMethodsFromDocumentPosition-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type:
- apiref
ms.openlocfilehash: bba0fc039c403d45e8a5b60f2b0231eb24226280
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614954"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="a7fed-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition-Methode</span><span class="sxs-lookup"><span data-stu-id="a7fed-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>
<span data-ttu-id="a7fed-103">Gibt ein Array von-Methoden zurück, von denen jede den Haltepunkt an der angegebenen Position in einem Dokument enthält.</span><span class="sxs-lookup"><span data-stu-id="a7fed-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7fed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7fed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7fed-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a7fed-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="a7fed-106">in Das angegebene Dokument.</span><span class="sxs-lookup"><span data-stu-id="a7fed-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="a7fed-107">in Die Zeile des angegebenen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="a7fed-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="a7fed-108">in Die Spalte des angegebenen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="a7fed-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="a7fed-109">[in] Die Größe des `pRetVal`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="a7fed-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="a7fed-110">vorgenommen Ein Zeiger auf eine Variable, die die Anzahl der im Array zurückgegebenen Elemente empfängt `pRetVal` .</span><span class="sxs-lookup"><span data-stu-id="a7fed-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="a7fed-111">vorgenommen Ein Array von Zeigern, von denen jedes auf ein [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) -Objekt verweist, das eine Methode darstellt, die den Breakpoint enthält.</span><span class="sxs-lookup"><span data-stu-id="a7fed-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7fed-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a7fed-112">Return Value</span></span>  
 <span data-ttu-id="a7fed-113">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="a7fed-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7fed-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7fed-114">Requirements</span></span>  
 <span data-ttu-id="a7fed-115">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="a7fed-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7fed-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7fed-116">See also</span></span>

- [<span data-ttu-id="a7fed-117">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7fed-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)

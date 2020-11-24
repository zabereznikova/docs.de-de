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
ms.openlocfilehash: 5298dd0f53693d96b748f6c839660838fdfad4ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689549"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="ca3b4-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition-Methode</span><span class="sxs-lookup"><span data-stu-id="ca3b4-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>

<span data-ttu-id="ca3b4-103">Gibt ein Array von-Methoden zurück, von denen jede den Haltepunkt an der angegebenen Position in einem Dokument enthält.</span><span class="sxs-lookup"><span data-stu-id="ca3b4-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca3b4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca3b4-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ca3b4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ca3b4-105">Parameters</span></span>  

 `document`  
 <span data-ttu-id="ca3b4-106">in Das angegebene Dokument.</span><span class="sxs-lookup"><span data-stu-id="ca3b4-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="ca3b4-107">in Die Zeile des angegebenen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="ca3b4-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="ca3b4-108">in Die Spalte des angegebenen Dokuments.</span><span class="sxs-lookup"><span data-stu-id="ca3b4-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="ca3b4-109">[in] Die Größe des `pRetVal`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="ca3b4-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="ca3b4-110">vorgenommen Ein Zeiger auf eine Variable, die die Anzahl der im Array zurückgegebenen Elemente empfängt `pRetVal` .</span><span class="sxs-lookup"><span data-stu-id="ca3b4-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="ca3b4-111">vorgenommen Ein Array von Zeigern, von denen jedes auf ein [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) -Objekt verweist, das eine Methode darstellt, die den Breakpoint enthält.</span><span class="sxs-lookup"><span data-stu-id="ca3b4-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca3b4-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ca3b4-112">Return Value</span></span>  

 <span data-ttu-id="ca3b4-113">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="ca3b4-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca3b4-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ca3b4-114">Requirements</span></span>  

 <span data-ttu-id="ca3b4-115">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="ca3b4-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca3b4-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ca3b4-116">See also</span></span>

- [<span data-ttu-id="ca3b4-117">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ca3b4-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)

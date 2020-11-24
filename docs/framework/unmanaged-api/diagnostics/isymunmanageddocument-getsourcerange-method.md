---
title: ISymUnmanagedDocument::GetSourceRange-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type:
- apiref
ms.openlocfilehash: f5d7df60a7b9c728b73fe6592226a8b6734b1e66
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692149"
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a><span data-ttu-id="f3b49-102">ISymUnmanagedDocument::GetSourceRange-Methode</span><span class="sxs-lookup"><span data-stu-id="f3b49-102">ISymUnmanagedDocument::GetSourceRange Method</span></span>

<span data-ttu-id="f3b49-103">Gibt den angegebenen Bereich der eingebetteten Quelle in den angegebenen Puffer zurück.</span><span class="sxs-lookup"><span data-stu-id="f3b49-103">Returns the specified range of the embedded source into the given buffer.</span></span> <span data-ttu-id="f3b49-104">Der Puffer muss groß genug sein, um die Quelle zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f3b49-104">The buffer must be large enough to hold the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3b49-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3b49-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3b49-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f3b49-106">Parameters</span></span>  

 `startLine`  
 <span data-ttu-id="f3b49-107">in Die Anfangs Zeile im aktuellen Dokument.</span><span class="sxs-lookup"><span data-stu-id="f3b49-107">[in] The starting line in the current document.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="f3b49-108">in Die Anfangs Spalte im aktuellen Dokument.</span><span class="sxs-lookup"><span data-stu-id="f3b49-108">[in] The starting column in the current document.</span></span>  
  
 `endLine`  
 <span data-ttu-id="f3b49-109">in Die letzte Zeile im aktuellen Dokument.</span><span class="sxs-lookup"><span data-stu-id="f3b49-109">[in] The final line in the current document.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="f3b49-110">in Die letzte Spalte im aktuellen Dokument.</span><span class="sxs-lookup"><span data-stu-id="f3b49-110">[in] The final column in the current document.</span></span>  
  
 `cSourceBytes`  
 <span data-ttu-id="f3b49-111">in Die Größe der Quelle in Bytes.</span><span class="sxs-lookup"><span data-stu-id="f3b49-111">[in] The size of the source, in bytes.</span></span>  
  
 `pcSourceBytes`  
 <span data-ttu-id="f3b49-112">vorgenommen Ein Zeiger auf eine Variable, die die Quellgröße empfängt.</span><span class="sxs-lookup"><span data-stu-id="f3b49-112">[out] A pointer to a variable that receives the source size.</span></span>  
  
 `source`  
 <span data-ttu-id="f3b49-113">vorgenommen Die Größe und die Länge des angegebenen Bereichs des Quelldokuments in Bytes.</span><span class="sxs-lookup"><span data-stu-id="f3b49-113">[out] The size and length of the specified range of the source document, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3b49-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f3b49-114">Return Value</span></span>  

 <span data-ttu-id="f3b49-115">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="f3b49-115">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3b49-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3b49-116">See also</span></span>

- [<span data-ttu-id="f3b49-117">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3b49-117">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)

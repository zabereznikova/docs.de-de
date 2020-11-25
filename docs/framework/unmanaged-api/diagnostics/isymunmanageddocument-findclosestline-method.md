---
title: ISymUnmanagedDocument::FindClosestLine-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
ms.openlocfilehash: 5ec67758e3174493cbd5cec1de0dcce30013ac43
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698584"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="41e7c-102">ISymUnmanagedDocument::FindClosestLine-Methode</span><span class="sxs-lookup"><span data-stu-id="41e7c-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>

<span data-ttu-id="41e7c-103">Gibt die nächste Zeile zurück, bei der es sich um einen Sequenz Punkt handelt, bei dem eine Zeile in diesem Dokument angegeben ist, die ein Sequenz Punkt sein kann.</span><span class="sxs-lookup"><span data-stu-id="41e7c-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41e7c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="41e7c-104">Syntax</span></span>  
  
```cpp  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41e7c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="41e7c-105">Parameters</span></span>  

 `line`  
 <span data-ttu-id="41e7c-106">in Eine Zeile in diesem Dokument.</span><span class="sxs-lookup"><span data-stu-id="41e7c-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="41e7c-107">vorgenommen Ein Zeiger auf eine Variable, die die Zeile empfängt.</span><span class="sxs-lookup"><span data-stu-id="41e7c-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41e7c-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="41e7c-108">Return Value</span></span>  

 <span data-ttu-id="41e7c-109">S_OK, wenn die Methode erfolgreich ist. andernfalls ein Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="41e7c-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41e7c-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="41e7c-110">See also</span></span>

- [<span data-ttu-id="41e7c-111">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41e7c-111">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)

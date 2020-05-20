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
ms.openlocfilehash: 9e6134d39096c4ab157aa545646d83339f92a0b8
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441031"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="29a34-102">ISymUnmanagedDocument::FindClosestLine-Methode</span><span class="sxs-lookup"><span data-stu-id="29a34-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="29a34-103">Gibt die nächste Zeile zurück, bei der es sich um einen Sequenz Punkt handelt, bei dem eine Zeile in diesem Dokument angegeben ist, die ein Sequenz Punkt sein kann.</span><span class="sxs-lookup"><span data-stu-id="29a34-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29a34-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="29a34-104">Syntax</span></span>  
  
```cpp  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29a34-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="29a34-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="29a34-106">in Eine Zeile in diesem Dokument.</span><span class="sxs-lookup"><span data-stu-id="29a34-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="29a34-107">vorgenommen Ein Zeiger auf eine Variable, die die Zeile empfängt.</span><span class="sxs-lookup"><span data-stu-id="29a34-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29a34-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="29a34-108">Return Value</span></span>  
 <span data-ttu-id="29a34-109">S_OK, wenn die Methode erfolgreich ist. andernfalls ein Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="29a34-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29a34-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29a34-110">See also</span></span>

- [<span data-ttu-id="29a34-111">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29a34-111">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)

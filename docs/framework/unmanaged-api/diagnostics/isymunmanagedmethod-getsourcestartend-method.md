---
title: ISymUnmanagedMethod::GetSourceStartEnd-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSourceStartEnd
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSourceStartEnd
helpviewer_keywords:
- GetSourceStartEnd method [.NET Framework debugging]
- ISymUnmanagedMethod::GetSourceStartEnd method [.NET Framework debugging]
ms.assetid: 2a420900-01f1-4461-8777-3a34a6dc1426
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a75fed4c46ea7e31177ac0446c8fae7805535323
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759425"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="d56e1-102">ISymUnmanagedMethod::GetSourceStartEnd-Methode</span><span class="sxs-lookup"><span data-stu-id="d56e1-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>
<span data-ttu-id="d56e1-103">Ruft die Dokumentpositionen für Start- und Endzeit für die Quelle dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="d56e1-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="d56e1-104">Die Arrayposition des erste ist der Anfang und die zweite Arrayposition ist.</span><span class="sxs-lookup"><span data-stu-id="d56e1-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d56e1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d56e1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d56e1-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d56e1-106">Parameters</span></span>  
 `docs`  
 <span data-ttu-id="d56e1-107">[in] Das Anfangs- und Endquelldokumente.</span><span class="sxs-lookup"><span data-stu-id="d56e1-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="d56e1-108">[in] Die Anfangs- und Endzeilen in den entsprechenden Quelldokumenten.</span><span class="sxs-lookup"><span data-stu-id="d56e1-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="d56e1-109">[in] Die Anfangs- und Endspalten in den entsprechenden Quelldokumenten.</span><span class="sxs-lookup"><span data-stu-id="d56e1-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="d56e1-110">[out] `true` wäre Positionen definiert ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="d56e1-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d56e1-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d56e1-111">Return Value</span></span>  
 <span data-ttu-id="d56e1-112">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="d56e1-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d56e1-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d56e1-113">Requirements</span></span>  
 <span data-ttu-id="d56e1-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d56e1-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d56e1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d56e1-115">See also</span></span>

- [<span data-ttu-id="d56e1-116">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d56e1-116">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)

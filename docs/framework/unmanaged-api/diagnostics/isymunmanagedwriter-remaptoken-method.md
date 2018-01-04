---
title: ISymUnmanagedWriter::RemapToken-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.RemapToken
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 86d6c78a49c55bdc9093241952bee00ee331696e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="35ba6-102">ISymUnmanagedWriter::RemapToken-Methode</span><span class="sxs-lookup"><span data-stu-id="35ba6-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="35ba6-103">Benachrichtigt dem Symbolwriter über ein Metadatentoken neu zugeordnet wurde, als die Metadaten ausgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="35ba6-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="35ba6-104">Wenn Sie der Symbolwriter das alte Token im Symbolspeicher gespeichert ist, muss er entweder aktualisieren das gespeicherte Token mit den neuen Wert, oder es muss die Zuordnung für den entsprechenden Symbolreader read Phase neu zuordnen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="35ba6-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35ba6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="35ba6-105">Syntax</span></span>  
  
```  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35ba6-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="35ba6-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="35ba6-107">[in] Das Metadatentoken, das neu zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="35ba6-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="35ba6-108">[in] Das neue Metadatentoken, `oldToken` neu zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="35ba6-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35ba6-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="35ba6-109">Return Value</span></span>  
 <span data-ttu-id="35ba6-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="35ba6-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35ba6-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="35ba6-111">Requirements</span></span>  
 <span data-ttu-id="35ba6-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="35ba6-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35ba6-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35ba6-113">See Also</span></span>  
 [<span data-ttu-id="35ba6-114">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="35ba6-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

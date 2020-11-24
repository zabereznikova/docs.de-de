---
title: ISymUnmanagedWriter::RemapToken-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.RemapToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type:
- apiref
ms.openlocfilehash: 8799815f7c6c6aefc7081f3583e6fd174cd478f7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683556"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="e4c1d-102">ISymUnmanagedWriter::RemapToken-Methode</span><span class="sxs-lookup"><span data-stu-id="e4c1d-102">ISymUnmanagedWriter::RemapToken Method</span></span>

<span data-ttu-id="e4c1d-103">Benachrichtigt den Symbolwriter, dass ein Metadatentoken neu zugeordnet wurde, während die Metadaten ausgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="e4c1d-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="e4c1d-104">Wenn der Symbolwriter das alte Token im Symbol Speicher gespeichert hat, muss entweder das gespeicherte Token mit dem neuen Wert aktualisiert werden, oder es muss die Zuordnung gespeichert werden, damit der entsprechende Symbol Reader während der Lese Phase neu zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e4c1d-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4c1d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4c1d-105">Syntax</span></span>  
  
```cpp  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4c1d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e4c1d-106">Parameters</span></span>  

 `oldToken`  
 <span data-ttu-id="e4c1d-107">in Das Metadatentoken, das neu zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="e4c1d-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="e4c1d-108">in Das neue Metadatentoken, dem neu zugeordnet `oldToken` wurde.</span><span class="sxs-lookup"><span data-stu-id="e4c1d-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e4c1d-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e4c1d-109">Return Value</span></span>  

 <span data-ttu-id="e4c1d-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e4c1d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4c1d-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e4c1d-111">Requirements</span></span>  

 <span data-ttu-id="e4c1d-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="e4c1d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4c1d-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e4c1d-113">See also</span></span>

- [<span data-ttu-id="e4c1d-114">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4c1d-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)

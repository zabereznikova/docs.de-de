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
ms.openlocfilehash: 53cc908e0dc8cc5cc980ec365ccac0df4e620cac
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609767"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="cfd63-102">ISymUnmanagedWriter::RemapToken-Methode</span><span class="sxs-lookup"><span data-stu-id="cfd63-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="cfd63-103">Benachrichtigt den Symbolwriter, dass ein Metadatentoken neu zugeordnet wurde, während die Metadaten ausgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="cfd63-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="cfd63-104">Wenn der Symbolwriter das alte Token im Symbol Speicher gespeichert hat, muss entweder das gespeicherte Token mit dem neuen Wert aktualisiert werden, oder es muss die Zuordnung gespeichert werden, damit der entsprechende Symbol Reader während der Lese Phase neu zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="cfd63-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfd63-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cfd63-105">Syntax</span></span>  
  
```cpp  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfd63-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="cfd63-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="cfd63-107">in Das Metadatentoken, das neu zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="cfd63-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="cfd63-108">in Das neue Metadatentoken, dem neu zugeordnet `oldToken` wurde.</span><span class="sxs-lookup"><span data-stu-id="cfd63-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cfd63-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cfd63-109">Return Value</span></span>  
 <span data-ttu-id="cfd63-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="cfd63-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfd63-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cfd63-111">Requirements</span></span>  
 <span data-ttu-id="cfd63-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="cfd63-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfd63-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfd63-113">See also</span></span>

- [<span data-ttu-id="cfd63-114">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cfd63-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)

---
title: ISymUnmanagedENCUpdate::GetLocalVariableCount-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariableCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount method [.NET Framework debugging]
- GetLocalVariableCount method [.NET Framework debugging]
ms.assetid: 9777d8bb-4abc-4be8-aa7c-34f853eceb9c
topic_type:
- apiref
ms.openlocfilehash: d04c9865d8272bf8d04080f6049ddfb1d4c643bb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614577"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="406a1-102">ISymUnmanagedENCUpdate::GetLocalVariableCount-Methode</span><span class="sxs-lookup"><span data-stu-id="406a1-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>
<span data-ttu-id="406a1-103">Ruft die Anzahl der lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="406a1-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="406a1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="406a1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
## <a name="parameters"></a><span data-ttu-id="406a1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="406a1-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="406a1-106">in Das Metadatentoken der Methoden.</span><span class="sxs-lookup"><span data-stu-id="406a1-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="406a1-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers in Zeichen empfängt, der die Anzahl der lokalen Variablen enthalten muss.</span><span class="sxs-lookup"><span data-stu-id="406a1-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="406a1-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="406a1-108">Return Value</span></span>  
 <span data-ttu-id="406a1-109">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="406a1-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="406a1-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="406a1-110">Requirements</span></span>  
 <span data-ttu-id="406a1-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="406a1-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="406a1-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="406a1-112">See also</span></span>

- [<span data-ttu-id="406a1-113">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="406a1-113">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)

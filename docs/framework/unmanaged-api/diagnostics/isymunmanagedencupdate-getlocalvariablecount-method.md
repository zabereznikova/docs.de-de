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
ms.openlocfilehash: 19e07fb181f631335a0c56bd59b6fc8e14e2f36d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726924"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="6f1bd-102">ISymUnmanagedENCUpdate::GetLocalVariableCount-Methode</span><span class="sxs-lookup"><span data-stu-id="6f1bd-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>

<span data-ttu-id="6f1bd-103">Ruft die Anzahl der lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="6f1bd-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f1bd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f1bd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f1bd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6f1bd-105">Parameters</span></span>  

 `mdMethodToken`  
 <span data-ttu-id="6f1bd-106">in Das Metadatentoken der Methoden.</span><span class="sxs-lookup"><span data-stu-id="6f1bd-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="6f1bd-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers in Zeichen empfängt, der die Anzahl der lokalen Variablen enthalten muss.</span><span class="sxs-lookup"><span data-stu-id="6f1bd-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f1bd-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6f1bd-108">Return Value</span></span>  

 <span data-ttu-id="6f1bd-109">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="6f1bd-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f1bd-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6f1bd-110">Requirements</span></span>  

 <span data-ttu-id="6f1bd-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="6f1bd-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f1bd-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f1bd-112">See also</span></span>

- [<span data-ttu-id="6f1bd-113">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f1bd-113">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)

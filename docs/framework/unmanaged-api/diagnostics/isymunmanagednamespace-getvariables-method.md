---
title: ISymUnmanagedNamespace::GetVariables-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type:
- apiref
ms.openlocfilehash: f554fa95f552285ad92d9f780a8d77f53e6890b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707697"
---
# <a name="isymunmanagednamespacegetvariables-method"></a><span data-ttu-id="76b5e-102">ISymUnmanagedNamespace::GetVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="76b5e-102">ISymUnmanagedNamespace::GetVariables Method</span></span>

<span data-ttu-id="76b5e-103">Gibt alle Variablen zurück, die im globalen Gültigkeitsbereich innerhalb dieses Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="76b5e-103">Returns all variables defined at global scope within this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76b5e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="76b5e-104">Syntax</span></span>  
  
```cpp
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76b5e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="76b5e-105">Parameters</span></span>  

 `cVars`  
 <span data-ttu-id="76b5e-106">in Ein-Wert `ULONG32` , der die Größe des `pVars` Arrays angibt.</span><span class="sxs-lookup"><span data-stu-id="76b5e-106">[in] A `ULONG32` that indicates the size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="76b5e-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers empfängt, der zum enthalten der Namespaces erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="76b5e-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `pVars`  
 <span data-ttu-id="76b5e-108">vorgenommen Ein Zeiger auf einen Puffer, der die Namespaces enthält.</span><span class="sxs-lookup"><span data-stu-id="76b5e-108">[out] A pointer to a buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76b5e-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="76b5e-109">Return Value</span></span>  

 <span data-ttu-id="76b5e-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="76b5e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76b5e-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="76b5e-111">Requirements</span></span>  

 <span data-ttu-id="76b5e-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="76b5e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76b5e-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76b5e-113">See also</span></span>

- [<span data-ttu-id="76b5e-114">ISymUnmanagedNamespace-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="76b5e-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)

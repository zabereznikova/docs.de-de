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
ms.openlocfilehash: 091f497024b48589953456e1ea6daf6635738240
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615084"
---
# <a name="isymunmanagednamespacegetvariables-method"></a><span data-ttu-id="a0265-102">ISymUnmanagedNamespace::GetVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="a0265-102">ISymUnmanagedNamespace::GetVariables Method</span></span>
<span data-ttu-id="a0265-103">Gibt alle Variablen zurück, die im globalen Gültigkeitsbereich innerhalb dieses Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="a0265-103">Returns all variables defined at global scope within this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0265-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0265-104">Syntax</span></span>  
  
```cpp
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0265-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a0265-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="a0265-106">in Ein-Wert `ULONG32` , der die Größe des `pVars` Arrays angibt.</span><span class="sxs-lookup"><span data-stu-id="a0265-106">[in] A `ULONG32` that indicates the size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="a0265-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers empfängt, der zum enthalten der Namespaces erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a0265-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `pVars`  
 <span data-ttu-id="a0265-108">vorgenommen Ein Zeiger auf einen Puffer, der die Namespaces enthält.</span><span class="sxs-lookup"><span data-stu-id="a0265-108">[out] A pointer to a buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0265-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a0265-109">Return Value</span></span>  
 <span data-ttu-id="a0265-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="a0265-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0265-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a0265-111">Requirements</span></span>  
 <span data-ttu-id="a0265-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="a0265-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0265-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0265-113">See also</span></span>

- [<span data-ttu-id="a0265-114">ISymUnmanagedNamespace-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0265-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)

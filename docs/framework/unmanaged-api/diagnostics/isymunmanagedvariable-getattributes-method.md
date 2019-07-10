---
title: ISymUnmanagedVariable::GetAttributes-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAttributes
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAttributes
helpviewer_keywords:
- GetAttributes method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAttributes method [.NET Framework debugging]
ms.assetid: 80f168af-a6a6-4c8f-b9e6-8a82dc834ed5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7e71315b5ff99a550ae4a59f3b0d444093dac01
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778279"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="cc496-102">ISymUnmanagedVariable::GetAttributes-Methode</span><span class="sxs-lookup"><span data-stu-id="cc496-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="cc496-103">Ruft die Attributflags für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="cc496-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc496-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc496-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc496-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cc496-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="cc496-106">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Attribute.</span><span class="sxs-lookup"><span data-stu-id="cc496-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="cc496-107">Der zurückgegebene Wert werden die Werte in definierten die [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="cc496-107">The returned value will be one of the values defined in the [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc496-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cc496-108">Return Value</span></span>  
 <span data-ttu-id="cc496-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="cc496-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc496-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cc496-110">Requirements</span></span>  
 <span data-ttu-id="cc496-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cc496-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc496-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc496-112">See also</span></span>

- [<span data-ttu-id="cc496-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cc496-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)

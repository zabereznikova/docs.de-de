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
ms.openlocfilehash: dc0f72168e076f661bfefc17c851d7d353e5e742
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426751"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="65365-102">ISymUnmanagedVariable::GetAttributes-Methode</span><span class="sxs-lookup"><span data-stu-id="65365-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="65365-103">Ruft die Attributflags für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="65365-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65365-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="65365-104">Syntax</span></span>  
  
```  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65365-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="65365-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="65365-106">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Attribute.</span><span class="sxs-lookup"><span data-stu-id="65365-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="65365-107">Der zurückgegebene Wert werden die Werte definiert, der [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="65365-107">The returned value will be one of the values defined in the [CorSymVarFlag](../../../../docs/framework/unmanaged-api/diagnostics/corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65365-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="65365-108">Return Value</span></span>  
 <span data-ttu-id="65365-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="65365-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65365-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="65365-110">Requirements</span></span>  
 <span data-ttu-id="65365-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="65365-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65365-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65365-112">See Also</span></span>  
 [<span data-ttu-id="65365-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65365-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)

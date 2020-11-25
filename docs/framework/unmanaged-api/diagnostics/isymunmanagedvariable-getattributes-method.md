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
ms.openlocfilehash: 1142dbb83693f6104ba6e22e174ce02fb92997a6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726898"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="34f2b-102">ISymUnmanagedVariable::GetAttributes-Methode</span><span class="sxs-lookup"><span data-stu-id="34f2b-102">ISymUnmanagedVariable::GetAttributes Method</span></span>

<span data-ttu-id="34f2b-103">Ruft die Attributflags für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="34f2b-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34f2b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="34f2b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34f2b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="34f2b-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="34f2b-106">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Attribute empfängt.</span><span class="sxs-lookup"><span data-stu-id="34f2b-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="34f2b-107">Der zurückgegebene Wert ist einer der Werte, die in der [CorSymVarFlag](corsymvarflag-enumeration.md) -Enumeration definiert sind.</span><span class="sxs-lookup"><span data-stu-id="34f2b-107">The returned value will be one of the values defined in the [CorSymVarFlag](corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34f2b-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="34f2b-108">Return Value</span></span>  

 <span data-ttu-id="34f2b-109">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="34f2b-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34f2b-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="34f2b-110">Requirements</span></span>  

 <span data-ttu-id="34f2b-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="34f2b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34f2b-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="34f2b-112">See also</span></span>

- [<span data-ttu-id="34f2b-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="34f2b-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)

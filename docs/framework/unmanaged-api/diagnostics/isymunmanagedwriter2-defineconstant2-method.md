---
title: ISymUnmanagedWriter2::DefineConstant2-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineConstant2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineConstant2
helpviewer_keywords:
- DefineConstant2 method [.NET Framework debugging]
- ISymUnmanagedWriter2::DefineConstant2 method [.NET Framework debugging]
ms.assetid: dd2bc956-7dbe-49fc-a646-daa0d267f2df
topic_type:
- apiref
ms.openlocfilehash: 70ee853ff657a75dcc4df1454c4354f9d3f8202f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614720"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="cdd68-102">ISymUnmanagedWriter2::DefineConstant2-Methode</span><span class="sxs-lookup"><span data-stu-id="cdd68-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>
<span data-ttu-id="cdd68-103">Definiert einen Namen für einen konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="cdd68-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdd68-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cdd68-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdd68-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cdd68-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="cdd68-106">in Der Konstantenname.</span><span class="sxs-lookup"><span data-stu-id="cdd68-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="cdd68-107">in Der Wert der Konstanten.</span><span class="sxs-lookup"><span data-stu-id="cdd68-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="cdd68-108">in Das Metadatentoken der Konstanten.</span><span class="sxs-lookup"><span data-stu-id="cdd68-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cdd68-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cdd68-109">Return Value</span></span>  
 <span data-ttu-id="cdd68-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="cdd68-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdd68-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cdd68-111">Requirements</span></span>  
 <span data-ttu-id="cdd68-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="cdd68-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdd68-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cdd68-113">See also</span></span>

- [<span data-ttu-id="cdd68-114">ISymUnmanagedWriter2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cdd68-114">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="cdd68-115">DefineConstant-Methode</span><span class="sxs-lookup"><span data-stu-id="cdd68-115">DefineConstant Method</span></span>](isymunmanagedwriter-defineconstant-method.md)

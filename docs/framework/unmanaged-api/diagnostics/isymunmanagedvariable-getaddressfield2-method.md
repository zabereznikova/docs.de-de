---
title: ISymUnmanagedVariable::GetAddressField2-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField2
helpviewer_keywords:
- GetAddressField2 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField2 method [.NET Framework debugging]
ms.assetid: 1f25b294-72b6-4882-a49b-6c9d364b6008
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 463416165d2dbd7724d5cf0d29e40d8243ade34b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778318"
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a><span data-ttu-id="d60fa-102">ISymUnmanagedVariable::GetAddressField2-Methode</span><span class="sxs-lookup"><span data-stu-id="d60fa-102">ISymUnmanagedVariable::GetAddressField2 Method</span></span>
<span data-ttu-id="d60fa-103">Ruft das zweite Adressfeld für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="d60fa-103">Gets the second address field for this variable.</span></span> <span data-ttu-id="d60fa-104">Die Bedeutung, hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="d60fa-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d60fa-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d60fa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d60fa-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d60fa-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="d60fa-107">[out] Ein Zeiger auf eine `ULONG32` , der das zweite Adressfeld empfängt.</span><span class="sxs-lookup"><span data-stu-id="d60fa-107">[out] A pointer to a `ULONG32` that receives the second address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d60fa-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d60fa-108">Return Value</span></span>  
 <span data-ttu-id="d60fa-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="d60fa-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d60fa-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d60fa-110">Requirements</span></span>  
 <span data-ttu-id="d60fa-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d60fa-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d60fa-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d60fa-112">See also</span></span>

- [<span data-ttu-id="d60fa-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d60fa-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="d60fa-114">GetAddressField1-Methode</span><span class="sxs-lookup"><span data-stu-id="d60fa-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="d60fa-115">GetAddressField3-Methode</span><span class="sxs-lookup"><span data-stu-id="d60fa-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="d60fa-116">GetAddressKind-Methode</span><span class="sxs-lookup"><span data-stu-id="d60fa-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)

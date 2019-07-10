---
title: ISymUnmanagedVariable::GetAddressField1-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField1
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField1
helpviewer_keywords:
- GetAddressField1 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField1 method [.NET Framework debugging]
ms.assetid: 25788ed1-0ce3-4b97-96fc-88f8997812a3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8a035e8dd7bd880c4ead500eede5e1b095d701f2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778072"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="d0941-102">ISymUnmanagedVariable::GetAddressField1-Methode</span><span class="sxs-lookup"><span data-stu-id="d0941-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>
<span data-ttu-id="d0941-103">Ruft das erste Adressfeld für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="d0941-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="d0941-104">Die Bedeutung, hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="d0941-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0941-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0941-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0941-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d0941-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="d0941-107">[out] Ein Zeiger auf eine `ULONG32` , der das erste Adressfeld empfängt.</span><span class="sxs-lookup"><span data-stu-id="d0941-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0941-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d0941-108">Return Value</span></span>  
 <span data-ttu-id="d0941-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="d0941-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0941-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d0941-110">Requirements</span></span>  
 <span data-ttu-id="d0941-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d0941-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0941-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0941-112">See also</span></span>

- [<span data-ttu-id="d0941-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d0941-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="d0941-114">GetAddressField2-Methode</span><span class="sxs-lookup"><span data-stu-id="d0941-114">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="d0941-115">GetAddressField3-Methode</span><span class="sxs-lookup"><span data-stu-id="d0941-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="d0941-116">GetAddressKind-Methode</span><span class="sxs-lookup"><span data-stu-id="d0941-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)

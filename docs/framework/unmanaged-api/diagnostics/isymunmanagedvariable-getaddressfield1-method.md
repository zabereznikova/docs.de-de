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
ms.openlocfilehash: f9e0e234a8f77ef35ad93302fe8fc676cf9dbaeb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427489"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="bb642-102">ISymUnmanagedVariable::GetAddressField1-Methode</span><span class="sxs-lookup"><span data-stu-id="bb642-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>
<span data-ttu-id="bb642-103">Ruft das Feld für die erste Adresse für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="bb642-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="bb642-104">Seiner Bedeutung hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="bb642-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb642-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb642-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb642-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="bb642-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="bb642-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt das Feld für die erste Adresse.</span><span class="sxs-lookup"><span data-stu-id="bb642-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb642-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bb642-108">Return Value</span></span>  
 <span data-ttu-id="bb642-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="bb642-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb642-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb642-110">Requirements</span></span>  
 <span data-ttu-id="bb642-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bb642-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb642-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb642-112">See Also</span></span>  
 [<span data-ttu-id="bb642-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb642-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="bb642-114">GetAddressField2-Methode</span><span class="sxs-lookup"><span data-stu-id="bb642-114">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)  
 [<span data-ttu-id="bb642-115">GetAddressField3-Methode</span><span class="sxs-lookup"><span data-stu-id="bb642-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)  
 [<span data-ttu-id="bb642-116">GetAddressKind-Methode</span><span class="sxs-lookup"><span data-stu-id="bb642-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)

---
title: ISymUnmanagedVariable::GetAddressField3-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd474c7f149b8eff542b674c2ba6527b6a0cbcb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426997"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="b0262-102">ISymUnmanagedVariable::GetAddressField3-Methode</span><span class="sxs-lookup"><span data-stu-id="b0262-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="b0262-103">Ruft das Feld für die dritte Adresse für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="b0262-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="b0262-104">Seiner Bedeutung hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="b0262-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0262-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0262-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b0262-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b0262-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="b0262-107">[out] Ein Zeiger auf eine `ULONG32` , die Feld für die dritte Adresse empfängt.</span><span class="sxs-lookup"><span data-stu-id="b0262-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0262-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b0262-108">Return Value</span></span>  
 <span data-ttu-id="b0262-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="b0262-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0262-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b0262-110">Requirements</span></span>  
 <span data-ttu-id="b0262-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b0262-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0262-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0262-112">See Also</span></span>  
 [<span data-ttu-id="b0262-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b0262-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="b0262-114">GetAddressField1-Methode</span><span class="sxs-lookup"><span data-stu-id="b0262-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)  
 [<span data-ttu-id="b0262-115">GetAddressField2-Methode</span><span class="sxs-lookup"><span data-stu-id="b0262-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)  
 [<span data-ttu-id="b0262-116">GetAddressKind-Methode</span><span class="sxs-lookup"><span data-stu-id="b0262-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)

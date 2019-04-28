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
ms.openlocfilehash: c8b03b96c8cab43046d109d0dd11ae135cb70c9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797591"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="b8079-102">ISymUnmanagedVariable::GetAddressField3-Methode</span><span class="sxs-lookup"><span data-stu-id="b8079-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="b8079-103">Ruft das dritte Adressfeld für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="b8079-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="b8079-104">Die Bedeutung, hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="b8079-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8079-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8079-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8079-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b8079-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="b8079-107">[out] Ein Zeiger auf eine `ULONG32` , das das dritte Adressfeld empfängt.</span><span class="sxs-lookup"><span data-stu-id="b8079-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8079-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b8079-108">Return Value</span></span>  
 <span data-ttu-id="b8079-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="b8079-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8079-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8079-110">Requirements</span></span>  
 <span data-ttu-id="b8079-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b8079-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8079-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8079-112">See also</span></span>

- [<span data-ttu-id="b8079-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8079-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="b8079-114">GetAddressField1-Methode</span><span class="sxs-lookup"><span data-stu-id="b8079-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="b8079-115">GetAddressField2-Methode</span><span class="sxs-lookup"><span data-stu-id="b8079-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="b8079-116">GetAddressKind-Methode</span><span class="sxs-lookup"><span data-stu-id="b8079-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)

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
ms.openlocfilehash: 796a71ac941497801c749295fb2f6bb201547bd7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478309"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="218c7-102">ISymUnmanagedVariable::GetAddressField1-Methode</span><span class="sxs-lookup"><span data-stu-id="218c7-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>
<span data-ttu-id="218c7-103">Ruft das erste Adressfeld für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="218c7-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="218c7-104">Die Bedeutung, hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="218c7-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="218c7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="218c7-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="218c7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="218c7-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="218c7-107">[out] Ein Zeiger auf eine `ULONG32` , der das erste Adressfeld empfängt.</span><span class="sxs-lookup"><span data-stu-id="218c7-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="218c7-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="218c7-108">Return Value</span></span>  
 <span data-ttu-id="218c7-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="218c7-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="218c7-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="218c7-110">Requirements</span></span>  
 <span data-ttu-id="218c7-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="218c7-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="218c7-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="218c7-112">See also</span></span>
- [<span data-ttu-id="218c7-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="218c7-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
- [<span data-ttu-id="218c7-114">GetAddressField2-Methode</span><span class="sxs-lookup"><span data-stu-id="218c7-114">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="218c7-115">GetAddressField3-Methode</span><span class="sxs-lookup"><span data-stu-id="218c7-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="218c7-116">GetAddressKind-Methode</span><span class="sxs-lookup"><span data-stu-id="218c7-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)

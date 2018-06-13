---
title: ISymUnmanagedVariable::GetAddressKind-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressKind
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressKind
helpviewer_keywords:
- GetAddressKind method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressKind method [.NET Framework debugging]
ms.assetid: a71563c0-62f2-4eb4-970c-825d61827613
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 18e83582a73ba3b2eb2538bcdf60984c46131768
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426950"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="9affa-102">ISymUnmanagedVariable::GetAddressKind-Methode</span><span class="sxs-lookup"><span data-stu-id="9affa-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>
<span data-ttu-id="9affa-103">Ruft die Art der Adresse dieser Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="9affa-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9affa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9affa-104">Syntax</span></span>  
  
```  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9affa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9affa-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="9affa-106">[out] Ein Zeiger auf eine `ULONG32` , die den Wert empfängt.</span><span class="sxs-lookup"><span data-stu-id="9affa-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="9affa-107">Die möglichen Werte werden definiert, der [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="9affa-107">The possible values are defined in the [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9affa-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9affa-108">Return Value</span></span>  
 <span data-ttu-id="9affa-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="9affa-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9affa-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9affa-110">Requirements</span></span>  
 <span data-ttu-id="9affa-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9affa-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9affa-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9affa-112">See Also</span></span>  
 [<span data-ttu-id="9affa-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9affa-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)

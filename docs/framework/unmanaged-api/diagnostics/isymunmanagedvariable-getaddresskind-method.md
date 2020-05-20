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
ms.openlocfilehash: 093c5e3e64395c8946acd9201990d132e8111fc7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610586"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="4b86a-102">ISymUnmanagedVariable::GetAddressKind-Methode</span><span class="sxs-lookup"><span data-stu-id="4b86a-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>
<span data-ttu-id="4b86a-103">Ruft die Art der Adresse dieser Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="4b86a-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b86a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b86a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b86a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4b86a-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="4b86a-106">vorgenommen Ein Zeiger auf einen `ULONG32` , der den Wert empfängt.</span><span class="sxs-lookup"><span data-stu-id="4b86a-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="4b86a-107">Die möglichen Werte werden in der [CorSymAddrKind](corsymaddrkind-enumeration.md) -Enumeration definiert.</span><span class="sxs-lookup"><span data-stu-id="4b86a-107">The possible values are defined in the [CorSymAddrKind](corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b86a-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4b86a-108">Return Value</span></span>  
 <span data-ttu-id="4b86a-109">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="4b86a-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b86a-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4b86a-110">Requirements</span></span>  
 <span data-ttu-id="4b86a-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="4b86a-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b86a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b86a-112">See also</span></span>

- [<span data-ttu-id="4b86a-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4b86a-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)

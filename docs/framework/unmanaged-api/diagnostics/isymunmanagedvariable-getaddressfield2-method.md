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
ms.openlocfilehash: 858341d5b8b1b3ecbe9dd5bd39a38f9cfd0d08dc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714171"
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a><span data-ttu-id="eb5a5-102">ISymUnmanagedVariable::GetAddressField2-Methode</span><span class="sxs-lookup"><span data-stu-id="eb5a5-102">ISymUnmanagedVariable::GetAddressField2 Method</span></span>

<span data-ttu-id="eb5a5-103">Ruft das zweite Adressfeld für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="eb5a5-103">Gets the second address field for this variable.</span></span> <span data-ttu-id="eb5a5-104">Ihre Bedeutung hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="eb5a5-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb5a5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb5a5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb5a5-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="eb5a5-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="eb5a5-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der das zweite Adressfeld empfängt.</span><span class="sxs-lookup"><span data-stu-id="eb5a5-107">[out] A pointer to a `ULONG32` that receives the second address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb5a5-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="eb5a5-108">Return Value</span></span>  

 <span data-ttu-id="eb5a5-109">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="eb5a5-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb5a5-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="eb5a5-110">Requirements</span></span>  

 <span data-ttu-id="eb5a5-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="eb5a5-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb5a5-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb5a5-112">See also</span></span>

- [<span data-ttu-id="eb5a5-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eb5a5-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="eb5a5-114">GetAddressField1-Methode</span><span class="sxs-lookup"><span data-stu-id="eb5a5-114">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="eb5a5-115">GetAddressField3-Methode</span><span class="sxs-lookup"><span data-stu-id="eb5a5-115">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="eb5a5-116">GetAddressKind-Methode</span><span class="sxs-lookup"><span data-stu-id="eb5a5-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)

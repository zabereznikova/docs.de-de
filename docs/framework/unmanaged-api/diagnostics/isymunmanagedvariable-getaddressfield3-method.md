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
ms.openlocfilehash: 13746c4ac6322a401e547c1c7acc99c0eda9accf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723336"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="16045-102">ISymUnmanagedVariable::GetAddressField3-Methode</span><span class="sxs-lookup"><span data-stu-id="16045-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>

<span data-ttu-id="16045-103">Ruft das dritte Adressfeld für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="16045-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="16045-104">Ihre Bedeutung hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="16045-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16045-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="16045-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16045-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="16045-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="16045-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der das dritte Adressfeld empfängt.</span><span class="sxs-lookup"><span data-stu-id="16045-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16045-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="16045-108">Return Value</span></span>  

 <span data-ttu-id="16045-109">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="16045-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16045-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="16045-110">Requirements</span></span>  

 <span data-ttu-id="16045-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="16045-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16045-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="16045-112">See also</span></span>

- [<span data-ttu-id="16045-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="16045-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="16045-114">GetAddressField1-Methode</span><span class="sxs-lookup"><span data-stu-id="16045-114">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="16045-115">GetAddressField2-Methode</span><span class="sxs-lookup"><span data-stu-id="16045-115">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="16045-116">GetAddressKind-Methode</span><span class="sxs-lookup"><span data-stu-id="16045-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)

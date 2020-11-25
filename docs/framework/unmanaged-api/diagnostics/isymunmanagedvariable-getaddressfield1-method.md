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
ms.openlocfilehash: e3ea3c0fd65750d52c0cfb10edbe18b1512f724b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729017"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="95fb4-102">ISymUnmanagedVariable::GetAddressField1-Methode</span><span class="sxs-lookup"><span data-stu-id="95fb4-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>

<span data-ttu-id="95fb4-103">Ruft das erste Adressfeld für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="95fb4-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="95fb4-104">Ihre Bedeutung hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="95fb4-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95fb4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="95fb4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95fb4-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="95fb4-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="95fb4-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der das erste Adressfeld empfängt.</span><span class="sxs-lookup"><span data-stu-id="95fb4-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95fb4-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="95fb4-108">Return Value</span></span>  

 <span data-ttu-id="95fb4-109">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="95fb4-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95fb4-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="95fb4-110">Requirements</span></span>  

 <span data-ttu-id="95fb4-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="95fb4-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95fb4-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="95fb4-112">See also</span></span>

- [<span data-ttu-id="95fb4-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95fb4-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="95fb4-114">GetAddressField2-Methode</span><span class="sxs-lookup"><span data-stu-id="95fb4-114">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="95fb4-115">GetAddressField3-Methode</span><span class="sxs-lookup"><span data-stu-id="95fb4-115">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="95fb4-116">GetAddressKind-Methode</span><span class="sxs-lookup"><span data-stu-id="95fb4-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)

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
ms.openlocfilehash: ff888d3e2b86efeea3f4e3d33528f731d85886bf
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615266"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="0aeea-102">ISymUnmanagedVariable::GetAddressField3-Methode</span><span class="sxs-lookup"><span data-stu-id="0aeea-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="0aeea-103">Ruft das dritte Adressfeld für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="0aeea-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="0aeea-104">Ihre Bedeutung hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="0aeea-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0aeea-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0aeea-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0aeea-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0aeea-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="0aeea-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der das dritte Adressfeld empfängt.</span><span class="sxs-lookup"><span data-stu-id="0aeea-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0aeea-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0aeea-108">Return Value</span></span>  
 <span data-ttu-id="0aeea-109">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="0aeea-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0aeea-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0aeea-110">Requirements</span></span>  
 <span data-ttu-id="0aeea-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="0aeea-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aeea-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0aeea-112">See also</span></span>

- [<span data-ttu-id="0aeea-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0aeea-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="0aeea-114">GetAddressField1-Methode</span><span class="sxs-lookup"><span data-stu-id="0aeea-114">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="0aeea-115">GetAddressField2-Methode</span><span class="sxs-lookup"><span data-stu-id="0aeea-115">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="0aeea-116">GetAddressKind-Methode</span><span class="sxs-lookup"><span data-stu-id="0aeea-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)

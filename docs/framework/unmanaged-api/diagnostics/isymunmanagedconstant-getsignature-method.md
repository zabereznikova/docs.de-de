---
title: ISymUnmanagedConstant::GetSignature-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetSignature method [.NET Framework debugging]
ms.assetid: 3eb41151-a228-43e3-ba8f-e6dd3ceb8542
topic_type:
- apiref
ms.openlocfilehash: 4436e4528c1dc486eb5c443c5a9467ac69a26c7d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706930"
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="642c8-102">ISymUnmanagedConstant::GetSignature-Methode</span><span class="sxs-lookup"><span data-stu-id="642c8-102">ISymUnmanagedConstant::GetSignature Method</span></span>

<span data-ttu-id="642c8-103">Ruft die Signatur der Konstante ab.</span><span class="sxs-lookup"><span data-stu-id="642c8-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="642c8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="642c8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="642c8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="642c8-105">Parameters</span></span>  

 `cSig`  
 <span data-ttu-id="642c8-106">in Die Länge des Puffers, auf den der- `pcSig` Parameter verweist.</span><span class="sxs-lookup"><span data-stu-id="642c8-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="642c8-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers, der die Signatur enthalten muss, in Zeichen empfängt.</span><span class="sxs-lookup"><span data-stu-id="642c8-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="642c8-108">vorgenommen Der Puffer, in dem die Signatur gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="642c8-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="642c8-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="642c8-109">Return Value</span></span>  

 <span data-ttu-id="642c8-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="642c8-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="642c8-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="642c8-111">Requirements</span></span>  

 <span data-ttu-id="642c8-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="642c8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="642c8-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="642c8-113">See also</span></span>

- [<span data-ttu-id="642c8-114">ISymUnmanagedConstant-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="642c8-114">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="642c8-115">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="642c8-115">GetName Method</span></span>](isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="642c8-116">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="642c8-116">GetValue Method</span></span>](isymunmanagedconstant-getvalue-method.md)

---
title: ISymUnmanagedConstant::GetName-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type:
- apiref
ms.openlocfilehash: 2dd70693528904459a34689dbad944c65c971254
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441642"
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="1eb3d-102">ISymUnmanagedConstant::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="1eb3d-102">ISymUnmanagedConstant::GetName Method</span></span>
<span data-ttu-id="1eb3d-103">Ruft den Namen der Konstante ab.</span><span class="sxs-lookup"><span data-stu-id="1eb3d-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eb3d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1eb3d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1eb3d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1eb3d-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="1eb3d-106">in Die Länge des Puffers, auf den der- `szName` Parameter verweist.</span><span class="sxs-lookup"><span data-stu-id="1eb3d-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="1eb3d-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe (in Zeichen) des Puffers erhält, der den Namen enthalten muss, einschließlich der NULL-Beendigung.</span><span class="sxs-lookup"><span data-stu-id="1eb3d-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="1eb3d-108">vorgenommen Der Puffer, in dem der Name gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="1eb3d-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1eb3d-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1eb3d-109">Return Value</span></span>  
 <span data-ttu-id="1eb3d-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="1eb3d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eb3d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1eb3d-111">Requirements</span></span>  
 <span data-ttu-id="1eb3d-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="1eb3d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eb3d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1eb3d-113">See also</span></span>

- [<span data-ttu-id="1eb3d-114">ISymUnmanagedConstant-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1eb3d-114">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="1eb3d-115">GetSignature-Methode</span><span class="sxs-lookup"><span data-stu-id="1eb3d-115">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
- [<span data-ttu-id="1eb3d-116">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="1eb3d-116">GetValue Method</span></span>](isymunmanagedconstant-getvalue-method.md)

---
title: ISymUnmanagedVariable::GetName-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetName
helpviewer_keywords:
- GetName method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetName method [.NET Framework debugging]
ms.assetid: eedf1ef0-9d4a-4847-a201-4e99572dfe5e
topic_type:
- apiref
ms.openlocfilehash: f9da3ca8684da3bbc87146b3b52effdc4f91393d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726885"
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="c9f33-102">ISymUnmanagedVariable::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="c9f33-102">ISymUnmanagedVariable::GetName Method</span></span>

<span data-ttu-id="c9f33-103">Ruft den Namen dieser Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="c9f33-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9f33-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9f33-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9f33-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c9f33-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="c9f33-106">in Die Länge des Puffers, auf den der- `pcchName` Parameter verweist.</span><span class="sxs-lookup"><span data-stu-id="c9f33-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="c9f33-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe (in Zeichen) des Puffers erhält, der den Namen enthalten muss, einschließlich der NULL-Beendigung.</span><span class="sxs-lookup"><span data-stu-id="c9f33-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="c9f33-108">vorgenommen Der Puffer, in dem der Name gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="c9f33-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9f33-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c9f33-109">Return Value</span></span>  

 <span data-ttu-id="c9f33-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="c9f33-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9f33-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c9f33-111">Requirements</span></span>  

 <span data-ttu-id="c9f33-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="c9f33-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9f33-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9f33-113">See also</span></span>

- [<span data-ttu-id="c9f33-114">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c9f33-114">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)

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
ms.openlocfilehash: b48d131fa99b65d38856d2b635bf59145db9157e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615240"
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="8000b-102">ISymUnmanagedVariable::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="8000b-102">ISymUnmanagedVariable::GetName Method</span></span>
<span data-ttu-id="8000b-103">Ruft den Namen dieser Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="8000b-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8000b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8000b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8000b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8000b-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="8000b-106">in Die Länge des Puffers, auf den der- `pcchName` Parameter verweist.</span><span class="sxs-lookup"><span data-stu-id="8000b-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="8000b-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe (in Zeichen) des Puffers erhält, der den Namen enthalten muss, einschließlich der NULL-Beendigung.</span><span class="sxs-lookup"><span data-stu-id="8000b-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="8000b-108">vorgenommen Der Puffer, in dem der Name gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="8000b-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8000b-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8000b-109">Return Value</span></span>  
 <span data-ttu-id="8000b-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="8000b-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8000b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8000b-111">Requirements</span></span>  
 <span data-ttu-id="8000b-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="8000b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8000b-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8000b-113">See also</span></span>

- [<span data-ttu-id="8000b-114">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8000b-114">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)

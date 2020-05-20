---
title: ISymUnmanagedReader::GetMethodVersion-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
ms.openlocfilehash: 8ee4c1bffccb44d15fa53eb3d4d6c0fcdc3e7697
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614967"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="4b40f-102">ISymUnmanagedReader::GetMethodVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="4b40f-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="4b40f-103">Ruft die Methoden Version ab.</span><span class="sxs-lookup"><span data-stu-id="4b40f-103">Gets the method version.</span></span> <span data-ttu-id="4b40f-104">Die Methoden Version beginnt bei 1 und wird bei jeder erneuten Kompilierung der Methode inkrementiert.</span><span class="sxs-lookup"><span data-stu-id="4b40f-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="4b40f-105">Die Neukompilierung kann ohne Änderungen an der-Methode erfolgen.</span><span class="sxs-lookup"><span data-stu-id="4b40f-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b40f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b40f-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b40f-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="4b40f-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="4b40f-108">in Die Methode, für die die Version zu erhalten ist.</span><span class="sxs-lookup"><span data-stu-id="4b40f-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="4b40f-109">vorgenommen Ein Zeiger auf eine Variable, die die Methoden Version empfängt.</span><span class="sxs-lookup"><span data-stu-id="4b40f-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b40f-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4b40f-110">Return Value</span></span>  
 <span data-ttu-id="4b40f-111">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="4b40f-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b40f-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4b40f-112">Requirements</span></span>  
 <span data-ttu-id="4b40f-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="4b40f-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b40f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b40f-114">See also</span></span>

- [<span data-ttu-id="4b40f-115">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4b40f-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)

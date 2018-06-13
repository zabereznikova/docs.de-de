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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9abbfa14777c5a5f5a77fa91db0fbafee095ba9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429236"
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="244a0-102">ISymUnmanagedVariable::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="244a0-102">ISymUnmanagedVariable::GetName Method</span></span>
<span data-ttu-id="244a0-103">Ruft den Namen der Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="244a0-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="244a0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="244a0-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="244a0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="244a0-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="244a0-106">[in] Die Länge des Puffers, der `pcchName` -Parameter zeigt.</span><span class="sxs-lookup"><span data-stu-id="244a0-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="244a0-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe Puffers in Zeichen, die erforderlich sind, um den Namen, einschließlich der null-Terminierung aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="244a0-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="244a0-108">[out] Der Puffer, der den Namen speichert.</span><span class="sxs-lookup"><span data-stu-id="244a0-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="244a0-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="244a0-109">Return Value</span></span>  
 <span data-ttu-id="244a0-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="244a0-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="244a0-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="244a0-111">Requirements</span></span>  
 <span data-ttu-id="244a0-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="244a0-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="244a0-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="244a0-113">See Also</span></span>  
 [<span data-ttu-id="244a0-114">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="244a0-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)

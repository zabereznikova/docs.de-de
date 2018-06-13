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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ae532b20ec3486fe56e2dff340a5ad89941a8df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424374"
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="3ca33-102">ISymUnmanagedConstant::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="3ca33-102">ISymUnmanagedConstant::GetName Method</span></span>
<span data-ttu-id="3ca33-103">Ruft den Namen der Konstanten ab.</span><span class="sxs-lookup"><span data-stu-id="3ca33-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ca33-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ca33-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3ca33-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3ca33-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="3ca33-106">[in] Die Länge des Puffers, der `szName` -Parameter zeigt.</span><span class="sxs-lookup"><span data-stu-id="3ca33-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="3ca33-107">[out] Ein Zeiger auf eine `ULONG32` , empfängt die Größe Puffers in Zeichen, die erforderlich sind, um den Namen, einschließlich der null-Terminierung aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="3ca33-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="3ca33-108">[out] Der Puffer, der den Namen speichert.</span><span class="sxs-lookup"><span data-stu-id="3ca33-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ca33-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3ca33-109">Return Value</span></span>  
 <span data-ttu-id="3ca33-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="3ca33-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ca33-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ca33-111">Requirements</span></span>  
 <span data-ttu-id="3ca33-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3ca33-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ca33-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ca33-113">See Also</span></span>  
 [<span data-ttu-id="3ca33-114">ISymUnmanagedConstant-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ca33-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 [<span data-ttu-id="3ca33-115">GetSignature-Methode</span><span class="sxs-lookup"><span data-stu-id="3ca33-115">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)  
 [<span data-ttu-id="3ca33-116">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="3ca33-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)

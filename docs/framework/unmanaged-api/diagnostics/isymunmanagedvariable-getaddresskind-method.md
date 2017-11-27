---
title: ISymUnmanagedVariable::GetAddressKind-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetAddressKind
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetAddressKind
helpviewer_keywords:
- GetAddressKind method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressKind method [.NET Framework debugging]
ms.assetid: a71563c0-62f2-4eb4-970c-825d61827613
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 930b55c98609e5f3bc33f30da766c4556fbe5512
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="7d0b8-102">ISymUnmanagedVariable::GetAddressKind-Methode</span><span class="sxs-lookup"><span data-stu-id="7d0b8-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>
<span data-ttu-id="7d0b8-103">Ruft die Art der Adresse dieser Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="7d0b8-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d0b8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d0b8-104">Syntax</span></span>  
  
```  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7d0b8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7d0b8-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="7d0b8-106">[out] Ein Zeiger auf eine `ULONG32` , die den Wert empfängt.</span><span class="sxs-lookup"><span data-stu-id="7d0b8-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="7d0b8-107">Die möglichen Werte werden definiert, der [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="7d0b8-107">The possible values are defined in the [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d0b8-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7d0b8-108">Return Value</span></span>  
 <span data-ttu-id="7d0b8-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="7d0b8-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d0b8-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7d0b8-110">Requirements</span></span>  
 <span data-ttu-id="7d0b8-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7d0b8-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d0b8-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d0b8-112">See Also</span></span>  
 [<span data-ttu-id="7d0b8-113">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d0b8-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)

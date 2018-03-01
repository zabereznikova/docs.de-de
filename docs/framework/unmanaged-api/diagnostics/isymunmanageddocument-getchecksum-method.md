---
title: ISymUnmanagedDocument::GetCheckSum-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedDocument.GetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 19cd8881bdbd482cb420717855593d7b9583ae51
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="95aa8-102">ISymUnmanagedDocument::GetCheckSum-Methode</span><span class="sxs-lookup"><span data-stu-id="95aa8-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="95aa8-103">Ruft die Prüfsumme ab.</span><span class="sxs-lookup"><span data-stu-id="95aa8-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95aa8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="95aa8-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95aa8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="95aa8-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="95aa8-106">[in] Die Länge des Puffers gebotenen der `data` Parameter</span><span class="sxs-lookup"><span data-stu-id="95aa8-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="95aa8-107">[out] Die Größe und die Länge der Prüfsumme in Bytes.</span><span class="sxs-lookup"><span data-stu-id="95aa8-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="95aa8-108">[out] Der Puffer, der die Prüfsumme empfängt.</span><span class="sxs-lookup"><span data-stu-id="95aa8-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95aa8-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="95aa8-109">Return Value</span></span>  
 <span data-ttu-id="95aa8-110">S_OK, wenn die Methode erfolgreich ist; andernfalls ein Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="95aa8-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95aa8-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95aa8-111">See Also</span></span>  
 [<span data-ttu-id="95aa8-112">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95aa8-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

---
title: ISymUnmanagedDocument::GetCheckSum-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a60bf279c143559e7410d8dfd8213d3da1d05a6d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127556"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="c892e-102">ISymUnmanagedDocument::GetCheckSum-Methode</span><span class="sxs-lookup"><span data-stu-id="c892e-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="c892e-103">Ruft die Prüfsumme ab.</span><span class="sxs-lookup"><span data-stu-id="c892e-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c892e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c892e-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c892e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c892e-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="c892e-106">[in] Die Länge des Puffers bereitgestellt. durch die `data` Parameter</span><span class="sxs-lookup"><span data-stu-id="c892e-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="c892e-107">[out] Die Größe und die Länge der Prüfsumme in Bytes.</span><span class="sxs-lookup"><span data-stu-id="c892e-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="c892e-108">[out] Der Puffer, der die Prüfsumme empfängt.</span><span class="sxs-lookup"><span data-stu-id="c892e-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c892e-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c892e-109">Return Value</span></span>  
 <span data-ttu-id="c892e-110">S_OK, wenn die Methode erfolgreich ist; andernfalls ein Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="c892e-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c892e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c892e-111">See also</span></span>

- [<span data-ttu-id="c892e-112">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c892e-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

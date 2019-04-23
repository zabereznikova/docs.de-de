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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127556"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="b4b7e-102">ISymUnmanagedDocument::GetCheckSum-Methode</span><span class="sxs-lookup"><span data-stu-id="b4b7e-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="b4b7e-103">Ruft die Prüfsumme ab.</span><span class="sxs-lookup"><span data-stu-id="b4b7e-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4b7e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4b7e-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4b7e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b4b7e-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="b4b7e-106">[in] Die Länge des Puffers bereitgestellt. durch die `data` Parameter</span><span class="sxs-lookup"><span data-stu-id="b4b7e-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="b4b7e-107">[out] Die Größe und die Länge der Prüfsumme in Bytes.</span><span class="sxs-lookup"><span data-stu-id="b4b7e-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="b4b7e-108">[out] Der Puffer, der die Prüfsumme empfängt.</span><span class="sxs-lookup"><span data-stu-id="b4b7e-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4b7e-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b4b7e-109">Return Value</span></span>  
 <span data-ttu-id="b4b7e-110">S_OK, wenn die Methode erfolgreich ist; andernfalls ein Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="b4b7e-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4b7e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4b7e-111">See also</span></span>

- [<span data-ttu-id="b4b7e-112">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4b7e-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

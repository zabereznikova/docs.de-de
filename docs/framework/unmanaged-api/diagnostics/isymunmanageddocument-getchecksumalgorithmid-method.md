---
title: ISymUnmanagedDocument::GetCheckSumAlgorithmId-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSumAlgorithmId
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId method [.NET Framework debugging]
- GetCheckSumAlgorithmId method [.NET Framework debugging]
ms.assetid: c7f941cd-e25b-4b85-b1ce-5f77c9208fa9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 116792c6a669f31b0c69dcc0b25134af7e72f9f2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501031"
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a><span data-ttu-id="098b8-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId-Methode</span><span class="sxs-lookup"><span data-stu-id="098b8-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId Method</span></span>
<span data-ttu-id="098b8-103">Ruft die Bezeichner für den Prüfsummenalgorithmus ab, oder gibt eine GUID mit ausschließlich Nullen zurück, wenn keine Prüfsumme vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="098b8-103">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="098b8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="098b8-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="098b8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="098b8-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="098b8-106">[out] Ein Zeiger auf eine Variable, die den Bezeichner des Prüfsummenalgorithmus empfängt.</span><span class="sxs-lookup"><span data-stu-id="098b8-106">[out] A pointer to a variable that receives the checksum algorithm identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="098b8-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="098b8-107">Return Value</span></span>  
 <span data-ttu-id="098b8-108">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="098b8-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="098b8-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="098b8-109">See also</span></span>
- [<span data-ttu-id="098b8-110">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="098b8-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

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
ms.openlocfilehash: f2df98728eec28ffca05b2e246575fc5c882a078
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939879"
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a><span data-ttu-id="cf2c1-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId-Methode</span><span class="sxs-lookup"><span data-stu-id="cf2c1-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId Method</span></span>
<span data-ttu-id="cf2c1-103">Ruft die Bezeichner für den Prüfsummenalgorithmus ab, oder gibt eine GUID mit ausschließlich Nullen zurück, wenn keine Prüfsumme vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="cf2c1-103">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf2c1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf2c1-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf2c1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cf2c1-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="cf2c1-106">[out] Ein Zeiger auf eine Variable, die den Bezeichner des Prüfsummenalgorithmus empfängt.</span><span class="sxs-lookup"><span data-stu-id="cf2c1-106">[out] A pointer to a variable that receives the checksum algorithm identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf2c1-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cf2c1-107">Return Value</span></span>  
 <span data-ttu-id="cf2c1-108">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="cf2c1-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf2c1-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf2c1-109">See also</span></span>

- [<span data-ttu-id="cf2c1-110">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cf2c1-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

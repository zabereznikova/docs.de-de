---
title: ISymUnmanagedDocument::GetLanguage-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguage
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguage
helpviewer_keywords:
- ISymUnmanagedDocument::GetLanguage method [.NET Framework debugging]
- GetLanguage method [.NET Framework debugging]
ms.assetid: c6639418-e9f2-4a99-8ce2-ec9876e0bc79
topic_type:
- apiref
ms.openlocfilehash: 075d46b0bbc68add0203daf7430afb712c998fe0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700976"
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="d7ea0-102">ISymUnmanagedDocument::GetLanguage-Methode</span><span class="sxs-lookup"><span data-stu-id="d7ea0-102">ISymUnmanagedDocument::GetLanguage Method</span></span>

<span data-ttu-id="d7ea0-103">Ruft den sprach Bezeichner für dieses Dokument ab.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7ea0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7ea0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7ea0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d7ea0-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="d7ea0-106">vorgenommen Ein Zeiger auf eine Variable, die den sprach Bezeichner empfängt.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7ea0-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d7ea0-107">Return Value</span></span>  

 <span data-ttu-id="d7ea0-108">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="d7ea0-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7ea0-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d7ea0-109">See also</span></span>

- [<span data-ttu-id="d7ea0-110">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d7ea0-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)

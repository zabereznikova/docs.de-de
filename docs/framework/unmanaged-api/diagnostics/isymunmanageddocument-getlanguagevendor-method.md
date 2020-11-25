---
title: ISymUnmanagedDocument::GetLanguageVendor-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguageVendor
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type:
- apiref
ms.openlocfilehash: bac0f187409a191dda1ef635ec9b2da1aee25981
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700950"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="32b59-102">ISymUnmanagedDocument::GetLanguageVendor-Methode</span><span class="sxs-lookup"><span data-stu-id="32b59-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>

<span data-ttu-id="32b59-103">Ruft den Hersteller der Sprache dieses Dokuments ab.</span><span class="sxs-lookup"><span data-stu-id="32b59-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32b59-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="32b59-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32b59-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="32b59-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="32b59-106">vorgenommen Ein Zeiger auf eine Variable, die den Anbieter der-Sprache empfängt.</span><span class="sxs-lookup"><span data-stu-id="32b59-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32b59-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="32b59-107">Return Value</span></span>  

 <span data-ttu-id="32b59-108">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="32b59-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32b59-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="32b59-109">See also</span></span>

- [<span data-ttu-id="32b59-110">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="32b59-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)

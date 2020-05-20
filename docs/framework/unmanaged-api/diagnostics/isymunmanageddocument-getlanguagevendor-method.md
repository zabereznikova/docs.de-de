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
ms.openlocfilehash: e0a4c190f0f8e91886563477500c0e57e3516dfa
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614564"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="a445e-102">ISymUnmanagedDocument::GetLanguageVendor-Methode</span><span class="sxs-lookup"><span data-stu-id="a445e-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="a445e-103">Ruft den Hersteller der Sprache dieses Dokuments ab.</span><span class="sxs-lookup"><span data-stu-id="a445e-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a445e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a445e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a445e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a445e-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="a445e-106">vorgenommen Ein Zeiger auf eine Variable, die den Anbieter der-Sprache empfängt.</span><span class="sxs-lookup"><span data-stu-id="a445e-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a445e-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a445e-107">Return Value</span></span>  
 <span data-ttu-id="a445e-108">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="a445e-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a445e-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a445e-109">See also</span></span>

- [<span data-ttu-id="a445e-110">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a445e-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)

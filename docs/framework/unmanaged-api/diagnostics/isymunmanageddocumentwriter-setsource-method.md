---
title: ISymUnmanagedDocumentWriter::SetSource-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetSource
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetSource method [.NET Framework debugging]
- SetSource method [.NET Framework debugging]
ms.assetid: ea5b9d9f-ff06-4bd3-8de5-6435343aba59
topic_type:
- apiref
ms.openlocfilehash: 31475b08b569b925aab9cab869545f0912c4ecf8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691590"
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="3a973-102">ISymUnmanagedDocumentWriter::SetSource-Methode</span><span class="sxs-lookup"><span data-stu-id="3a973-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>

<span data-ttu-id="3a973-103">Legt die eingebettete Quelle für ein Dokument fest, das geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="3a973-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a973-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a973-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a973-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3a973-105">Parameters</span></span>  

 `sourceSize`  
 <span data-ttu-id="3a973-106">in Ein-Wert `ULONG32` , der die Größe des `source` Puffers enthält.</span><span class="sxs-lookup"><span data-stu-id="3a973-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="3a973-107">in Der Puffer, in dem die eingebettete Quelle gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="3a973-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a973-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3a973-108">Return Value</span></span>  

 <span data-ttu-id="3a973-109">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="3a973-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a973-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3a973-110">Requirements</span></span>  

 <span data-ttu-id="3a973-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="3a973-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a973-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3a973-112">See also</span></span>

- [<span data-ttu-id="3a973-113">ISymUnmanagedDocumentWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3a973-113">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)

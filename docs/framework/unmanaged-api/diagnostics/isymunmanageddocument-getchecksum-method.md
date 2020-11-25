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
ms.openlocfilehash: 4030da31400b7075952d146e5d6740306863e9ad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721087"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="7d0c3-102">ISymUnmanagedDocument::GetCheckSum-Methode</span><span class="sxs-lookup"><span data-stu-id="7d0c3-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>

<span data-ttu-id="7d0c3-103">Ruft die Prüfsumme ab.</span><span class="sxs-lookup"><span data-stu-id="7d0c3-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d0c3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d0c3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d0c3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7d0c3-105">Parameters</span></span>  

 `cData`  
 <span data-ttu-id="7d0c3-106">in Die Länge des Puffers, der vom-Parameter bereitgestellt wird. `data`</span><span class="sxs-lookup"><span data-stu-id="7d0c3-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="7d0c3-107">vorgenommen Die Größe und Länge der Prüfsumme in Bytes.</span><span class="sxs-lookup"><span data-stu-id="7d0c3-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="7d0c3-108">vorgenommen Der Puffer, der die Prüfsumme empfängt.</span><span class="sxs-lookup"><span data-stu-id="7d0c3-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7d0c3-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7d0c3-109">Return Value</span></span>  

 <span data-ttu-id="7d0c3-110">S_OK, wenn die Methode erfolgreich ist. andernfalls ein Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="7d0c3-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d0c3-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d0c3-111">See also</span></span>

- [<span data-ttu-id="7d0c3-112">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d0c3-112">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)

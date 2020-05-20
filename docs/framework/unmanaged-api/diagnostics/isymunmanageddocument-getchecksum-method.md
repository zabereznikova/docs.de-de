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
ms.openlocfilehash: 543bd208e5492460435663c32f276472a763f613
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441096"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="4e60b-102">ISymUnmanagedDocument::GetCheckSum-Methode</span><span class="sxs-lookup"><span data-stu-id="4e60b-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="4e60b-103">Ruft die Prüfsumme ab.</span><span class="sxs-lookup"><span data-stu-id="4e60b-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e60b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e60b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e60b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4e60b-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="4e60b-106">in Die Länge des Puffers, der vom-Parameter bereitgestellt wird. `data`</span><span class="sxs-lookup"><span data-stu-id="4e60b-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="4e60b-107">vorgenommen Die Größe und Länge der Prüfsumme in Bytes.</span><span class="sxs-lookup"><span data-stu-id="4e60b-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="4e60b-108">vorgenommen Der Puffer, der die Prüfsumme empfängt.</span><span class="sxs-lookup"><span data-stu-id="4e60b-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e60b-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4e60b-109">Return Value</span></span>  
 <span data-ttu-id="4e60b-110">S_OK, wenn die Methode erfolgreich ist. andernfalls ein Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="4e60b-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e60b-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e60b-111">See also</span></span>

- [<span data-ttu-id="4e60b-112">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e60b-112">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)

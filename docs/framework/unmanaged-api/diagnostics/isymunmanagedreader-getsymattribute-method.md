---
title: ISymUnmanagedReader::GetSymAttribute-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type:
- apiref
ms.openlocfilehash: aa3b742babe4a94a43e4e6168dea67c0a0245eb0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720580"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="a8230-102">ISymUnmanagedReader::GetSymAttribute-Methode</span><span class="sxs-lookup"><span data-stu-id="a8230-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>

<span data-ttu-id="a8230-103">Ruft ein benutzerdefiniertes Attribut basierend auf seinem Namen ab.</span><span class="sxs-lookup"><span data-stu-id="a8230-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="a8230-104">Im Gegensatz zu benutzerdefinierten Metadaten-Attributen werden diese benutzerdefinierten Attribute im Symbol Speicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a8230-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8230-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a8230-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8230-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a8230-106">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="a8230-107">in Das Metadatentoken für das-Objekt, für das das Attribut angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="a8230-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="a8230-108">in Ein Zeiger auf die Variable, die das abzurufende Attribut angibt.</span><span class="sxs-lookup"><span data-stu-id="a8230-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="a8230-109">[in] Die Größe des `buffer`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="a8230-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="a8230-110">vorgenommen Ein Zeiger auf die Variable, die die Länge der Attributdaten empfängt.</span><span class="sxs-lookup"><span data-stu-id="a8230-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="a8230-111">vorgenommen Ein Zeiger auf die Variable, die die Attributdaten empfängt.</span><span class="sxs-lookup"><span data-stu-id="a8230-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8230-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a8230-112">Return Value</span></span>  

 <span data-ttu-id="a8230-113">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="a8230-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8230-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a8230-114">Requirements</span></span>  

 <span data-ttu-id="a8230-115">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="a8230-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8230-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a8230-116">See also</span></span>

- [<span data-ttu-id="a8230-117">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a8230-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)

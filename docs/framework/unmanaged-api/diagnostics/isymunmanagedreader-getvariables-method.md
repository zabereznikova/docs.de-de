---
title: ISymUnmanagedReader::GetVariables-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetVariables
helpviewer_keywords:
- ISymUnmanagedReader::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 16dc49cb-2c60-4ac8-9c35-020e9afba3f8
topic_type:
- apiref
ms.openlocfilehash: c4341a5ffe557694473ae505590b57d39a27a721
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675892"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="84dfb-102">ISymUnmanagedReader::GetVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="84dfb-102">ISymUnmanagedReader::GetVariables Method</span></span>

<span data-ttu-id="84dfb-103">Gibt eine nicht lokale Variable zurück, wenn Ihr übergeordnetes Element und der Name angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="84dfb-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84dfb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84dfb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84dfb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="84dfb-105">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="84dfb-106">in Das übergeordnete Element der Variablen.</span><span class="sxs-lookup"><span data-stu-id="84dfb-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="84dfb-107">[in] Die Größe des `pVars`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="84dfb-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="84dfb-108">vorgenommen Ein Zeiger auf die Variable, die die Anzahl der in zurückgegebenen Variablen empfängt `pVars` .</span><span class="sxs-lookup"><span data-stu-id="84dfb-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="84dfb-109">vorgenommen Ein Zeiger auf die Variable, die die Variablen empfängt.</span><span class="sxs-lookup"><span data-stu-id="84dfb-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84dfb-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="84dfb-110">Return Value</span></span>  

 <span data-ttu-id="84dfb-111">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="84dfb-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84dfb-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="84dfb-112">Requirements</span></span>  

 <span data-ttu-id="84dfb-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="84dfb-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84dfb-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="84dfb-114">See also</span></span>

- [<span data-ttu-id="84dfb-115">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84dfb-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)

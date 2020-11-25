---
title: ISymUnmanagedScope::GetNamespaces-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetNamespaces
helpviewer_keywords:
- GetNamespaces method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetNamespaces method [.NET Framework debugging]
ms.assetid: c44b0440-04bd-460a-84fb-41afecf44503
topic_type:
- apiref
ms.openlocfilehash: 026ba35044bc7573dc54617dcade9cf3918a76ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725923"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="8e07f-102">ISymUnmanagedScope::GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="8e07f-102">ISymUnmanagedScope::GetNamespaces Method</span></span>

<span data-ttu-id="8e07f-103">Ruft die Namespaces ab, die in diesem Bereich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8e07f-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e07f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e07f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e07f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8e07f-105">Parameters</span></span>  

 `cNameSpaces`  
 <span data-ttu-id="8e07f-106">[in] Die Größe des `namespaces`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="8e07f-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="8e07f-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe des Puffers empfängt, der zum enthalten der Namespaces erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8e07f-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="8e07f-108">vorgenommen Das Array, das die Namespaces empfängt.</span><span class="sxs-lookup"><span data-stu-id="8e07f-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e07f-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8e07f-109">Return Value</span></span>  

 <span data-ttu-id="8e07f-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="8e07f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e07f-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8e07f-111">Requirements</span></span>  

 <span data-ttu-id="8e07f-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="8e07f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e07f-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8e07f-113">See also</span></span>

- [<span data-ttu-id="8e07f-114">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e07f-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)

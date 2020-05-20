---
title: ISymUnmanagedReader::GetUserEntryPoint-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetUserEntryPoint
helpviewer_keywords:
- GetUserEntryPoint method [.NET Framework debugging]
- ISymUnmanagedReader::GetUserEntryPoint method [.NET Framework debugging]
ms.assetid: 3fd3a34c-d176-46e9-9996-fb1646cff9b0
topic_type:
- apiref
ms.openlocfilehash: d465f830fa73016c3cf3f7df3a4a4d0c42bc0980
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615500"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="123d0-102">ISymUnmanagedReader::GetUserEntryPoint-Methode</span><span class="sxs-lookup"><span data-stu-id="123d0-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="123d0-103">Gibt die Methode zurück, die ggf. als Benutzer Einstiegspunkt für das Modul angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="123d0-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="123d0-104">Diese Methode kann z. b. die Hauptmethode des Benutzers anstelle der vom Compiler generierten Stub vor der Main-Methode sein.</span><span class="sxs-lookup"><span data-stu-id="123d0-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="123d0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="123d0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="123d0-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="123d0-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="123d0-107">vorgenommen Ein Zeiger auf eine Variable, die den Einstiegspunkt empfängt.</span><span class="sxs-lookup"><span data-stu-id="123d0-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="123d0-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="123d0-108">Return Value</span></span>  
 <span data-ttu-id="123d0-109">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="123d0-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="123d0-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="123d0-110">Requirements</span></span>  
 <span data-ttu-id="123d0-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="123d0-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="123d0-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="123d0-112">See also</span></span>

- [<span data-ttu-id="123d0-113">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="123d0-113">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)

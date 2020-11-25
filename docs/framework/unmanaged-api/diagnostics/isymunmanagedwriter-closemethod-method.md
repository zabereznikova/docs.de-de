---
title: ISymUnmanagedWriter::CloseMethod-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type:
- apiref
ms.openlocfilehash: fcf250f10baf4c65cd1c8c918655e4b9f4f5cc4b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731734"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="f871a-102">ISymUnmanagedWriter::CloseMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="f871a-102">ISymUnmanagedWriter::CloseMethod Method</span></span>

<span data-ttu-id="f871a-103">Schließt die aktuelle Methode.</span><span class="sxs-lookup"><span data-stu-id="f871a-103">Closes the current method.</span></span> <span data-ttu-id="f871a-104">Nachdem eine Methode geschlossen wurde, können darin keine weiteren Symbole definiert werden.</span><span class="sxs-lookup"><span data-stu-id="f871a-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f871a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f871a-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f871a-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f871a-106">Return Value</span></span>  

 <span data-ttu-id="f871a-107">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="f871a-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f871a-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f871a-108">Requirements</span></span>  

 <span data-ttu-id="f871a-109">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="f871a-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f871a-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f871a-110">See also</span></span>

- [<span data-ttu-id="f871a-111">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f871a-111">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="f871a-112">OpenMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="f871a-112">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)

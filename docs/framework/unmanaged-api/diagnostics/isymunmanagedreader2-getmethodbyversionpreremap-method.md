---
title: ISymUnmanagedReader2::GetMethodByVersionPreRemap-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type:
- apiref
ms.openlocfilehash: b12ecfdaf7c90589ce2e96b39f7437444cb91b09
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615422"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a><span data-ttu-id="36d4e-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap-Methode</span><span class="sxs-lookup"><span data-stu-id="36d4e-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap Method</span></span>
<span data-ttu-id="36d4e-103">Ruft eine Symbol Lesemethode ab, wenn ein Methoden Token und eine Bearbeitungs-und Fortsetzung-Versionsnummer angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="36d4e-103">Gets a symbol reader method, given a method token and an edit-and-continue version number.</span></span> <span data-ttu-id="36d4e-104">Versionsnummern beginnen bei 1 und werden jedes Mal um 1 erhöht, wenn die Methode aufgrund eines Edit-and-Continue-Vorgangs geändert wird.</span><span class="sxs-lookup"><span data-stu-id="36d4e-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-continue operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36d4e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="36d4e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36d4e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="36d4e-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="36d4e-107">in Das Metadatentoken der Methode.</span><span class="sxs-lookup"><span data-stu-id="36d4e-107">[in] The method metadata token.</span></span>  
  
 `version`  
 <span data-ttu-id="36d4e-108">in Die Methoden Version.</span><span class="sxs-lookup"><span data-stu-id="36d4e-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="36d4e-109">vorgenommen Ein Zeiger auf die zurückgegebene [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="36d4e-109">[out] A pointer to the returned [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36d4e-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="36d4e-110">Return Value</span></span>  
 <span data-ttu-id="36d4e-111">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="36d4e-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36d4e-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="36d4e-112">Requirements</span></span>  
 <span data-ttu-id="36d4e-113">**Header:** "Corsym. idl".</span><span class="sxs-lookup"><span data-stu-id="36d4e-113">**Header:** CorSym.idl.</span></span> <span data-ttu-id="36d4e-114">Corsym. h</span><span class="sxs-lookup"><span data-stu-id="36d4e-114">CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36d4e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36d4e-115">See also</span></span>

- [<span data-ttu-id="36d4e-116">ISymUnmanagedReader2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="36d4e-116">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)

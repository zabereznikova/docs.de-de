---
title: ISymUnmanagedReader::GetMethodByVersion-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodByVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type:
- apiref
ms.openlocfilehash: 64e6b9a1942e9a69e43de3d2f09564814328ec08
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689614"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="98139-102">ISymUnmanagedReader::GetMethodByVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="98139-102">ISymUnmanagedReader::GetMethodByVersion Method</span></span>

<span data-ttu-id="98139-103">Ruft eine Symbol Lesemethode ab, wenn ein Methoden Token und eine Bearbeitungs-und Kopier Versionsnummer angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="98139-103">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="98139-104">Versionsnummern beginnen bei 1 und werden jedes Mal erhöht, wenn die Methode aufgrund eines Bearbeitungs-und Kopiervorgangs geändert wird.</span><span class="sxs-lookup"><span data-stu-id="98139-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98139-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="98139-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98139-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="98139-106">Parameters</span></span>  

 `token`  
 <span data-ttu-id="98139-107">in Das Methoden Token.</span><span class="sxs-lookup"><span data-stu-id="98139-107">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="98139-108">in Die Methoden Version.</span><span class="sxs-lookup"><span data-stu-id="98139-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="98139-109">vorgenommen Ein Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="98139-109">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98139-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="98139-110">Return Value</span></span>  

 <span data-ttu-id="98139-111">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="98139-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98139-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="98139-112">Requirements</span></span>  

 <span data-ttu-id="98139-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="98139-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98139-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="98139-114">See also</span></span>

- [<span data-ttu-id="98139-115">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="98139-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)

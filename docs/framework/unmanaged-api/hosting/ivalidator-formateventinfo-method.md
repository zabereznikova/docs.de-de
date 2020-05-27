---
title: IValidator::FormatEventInfo-Methode
ms.date: 03/30/2017
api_name:
- IValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FormatEventInfo
helpviewer_keywords:
- IValidator::FormatEventInfo method [.NET Framework hosting]
- FormatEventInfo method, IValidator interface [.NET Framework hosting]
ms.assetid: 4c0c7477-05ba-461b-b21b-cbfba95f1db1
topic_type:
- apiref
ms.openlocfilehash: 0c60631b5e034bc46d74412440d35d526359d043
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008572"
---
# <a name="ivalidatorformateventinfo-method"></a><span data-ttu-id="08148-102">IValidator::FormatEventInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="08148-102">IValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="08148-103">Ruft die Fehlermeldung ab, die dem angegebenen Validierungs Fehler entspricht.</span><span class="sxs-lookup"><span data-stu-id="08148-103">Gets the error message corresponding to the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08148-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08148-104">Syntax</span></span>  
  
```cpp  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08148-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="08148-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="08148-106">in Der HRESULT-Wert, der an den Validierungs Fehlerhandler übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="08148-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="08148-107">in Eine- `VEContext` Instanz, die Kontextinformationen über den Validierungs Fehler enthält.</span><span class="sxs-lookup"><span data-stu-id="08148-107">[in] A `VEContext` instance that contains context information about the validation error.</span></span>  
  
 `msg`  
 <span data-ttu-id="08148-108">[in, out] Eine Zeichenfolge, die die zurückgegebene Fehlermeldung enthält.</span><span class="sxs-lookup"><span data-stu-id="08148-108">[in, out] A string that contains the returned error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="08148-109">in Die maximale Länge der Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="08148-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="08148-110">in Ein sicheres Array, das zusätzliche Parameter enthält, die den Fehler beschreiben.</span><span class="sxs-lookup"><span data-stu-id="08148-110">[in] A safe array that contains additional parameters describing the error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08148-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="08148-111">Requirements</span></span>  
 <span data-ttu-id="08148-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08148-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08148-113">**Header:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="08148-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="08148-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="08148-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08148-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08148-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  

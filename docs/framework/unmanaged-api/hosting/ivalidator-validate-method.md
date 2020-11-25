---
title: IValidator::Validate-Methode
ms.date: 03/30/2017
api_name:
- IValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type:
- apiref
ms.openlocfilehash: 3c59114f78af1aa8705318af093e47d4f03a82ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699143"
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="f5d01-102">IValidator::Validate-Methode</span><span class="sxs-lookup"><span data-stu-id="f5d01-102">IValidator::Validate Method</span></span>

<span data-ttu-id="f5d01-103">Überprüft die angegebene PE-Datei (portable ausführbare Datei) oder die MSIL-Datei (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="f5d01-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5d01-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5d01-104">Syntax</span></span>  
  
```cpp  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5d01-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f5d01-105">Parameters</span></span>  

 `veh`  
 <span data-ttu-id="f5d01-106">in Ein Zeiger auf eine- `IVEHandler` Instanz, die Validierungs Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="f5d01-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="f5d01-107">in Ein Zeiger auf die Anwendungsdomäne, in der die Datei geladen wird.</span><span class="sxs-lookup"><span data-stu-id="f5d01-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="f5d01-108">in Eine bitweise Kombination von [ValidatorFlags](validatorflags-enumeration.md) -Werten, die die auszuführenden Validierungen angeben.</span><span class="sxs-lookup"><span data-stu-id="f5d01-108">[in] A bitwise combination of [ValidatorFlags](validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="f5d01-109">in Die maximal zulässige Anzahl von Fehlern, bevor die Überprüfung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="f5d01-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="f5d01-110">[in] Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="f5d01-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="f5d01-111">in Eine Zeichenfolge, die den Namen der zu validierenden Datei angibt.</span><span class="sxs-lookup"><span data-stu-id="f5d01-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="f5d01-112">in Ein Zeiger auf den Speicherpuffer, in dem die Datei gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="f5d01-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="f5d01-113">in Die Größe (in Bytes) der zu validierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="f5d01-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5d01-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f5d01-114">Requirements</span></span>  

 <span data-ttu-id="f5d01-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5d01-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5d01-116">**Header:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="f5d01-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="f5d01-117">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f5d01-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5d01-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5d01-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  

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
ms.openlocfilehash: 688abd210cca193bf03c40f000b74ecb66eb8ede
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008546"
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="72ba7-102">IValidator::Validate-Methode</span><span class="sxs-lookup"><span data-stu-id="72ba7-102">IValidator::Validate Method</span></span>
<span data-ttu-id="72ba7-103">Überprüft die angegebene PE-Datei (portable ausführbare Datei) oder die MSIL-Datei (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="72ba7-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72ba7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72ba7-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="72ba7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="72ba7-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="72ba7-106">in Ein Zeiger auf eine- `IVEHandler` Instanz, die Validierungs Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="72ba7-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="72ba7-107">in Ein Zeiger auf die Anwendungsdomäne, in der die Datei geladen wird.</span><span class="sxs-lookup"><span data-stu-id="72ba7-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="72ba7-108">in Eine bitweise Kombination von [ValidatorFlags](validatorflags-enumeration.md) -Werten, die die auszuführenden Validierungen angeben.</span><span class="sxs-lookup"><span data-stu-id="72ba7-108">[in] A bitwise combination of [ValidatorFlags](validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="72ba7-109">in Die maximal zulässige Anzahl von Fehlern, bevor die Überprüfung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="72ba7-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="72ba7-110">[in] Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="72ba7-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="72ba7-111">in Eine Zeichenfolge, die den Namen der zu validierenden Datei angibt.</span><span class="sxs-lookup"><span data-stu-id="72ba7-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="72ba7-112">in Ein Zeiger auf den Speicherpuffer, in dem die Datei gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="72ba7-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="72ba7-113">in Die Größe (in Bytes) der zu validierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="72ba7-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72ba7-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="72ba7-114">Requirements</span></span>  
 <span data-ttu-id="72ba7-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72ba7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72ba7-116">**Header:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="72ba7-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="72ba7-117">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="72ba7-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="72ba7-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72ba7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  

---
title: ValidatorFlags-Enumeration
ms.date: 03/30/2017
api_name:
- ValidatorFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ValidatorFlags
helpviewer_keywords:
- ValidatorFlags enumeration [.NET Framework hosting]
ms.assetid: a3f5c266-3fcc-4ad1-aaf5-4cdbe26304ad
topic_type:
- apiref
ms.openlocfilehash: 92c430cdb8b46cf75dde9a8395ce713116dc05a5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732855"
---
# <a name="validatorflags-enumeration"></a><span data-ttu-id="b6ddd-102">ValidatorFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b6ddd-102">ValidatorFlags Enumeration</span></span>

<span data-ttu-id="b6ddd-103">Enthält Werte, die den Validierungstyp angeben, der bei einem Rückruf der [ICLRValidator:: Validate](iclrvalidator-validate-method.md) -Methode ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b6ddd-103">Contains values that indicate the type of validation that should be performed in a call to the [ICLRValidator::Validate](iclrvalidator-validate-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6ddd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6ddd-104">Syntax</span></span>  
  
```cpp  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a><span data-ttu-id="b6ddd-105">Member</span><span class="sxs-lookup"><span data-stu-id="b6ddd-105">Members</span></span>  
  
|<span data-ttu-id="b6ddd-106">Member</span><span class="sxs-lookup"><span data-stu-id="b6ddd-106">Member</span></span>|<span data-ttu-id="b6ddd-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b6ddd-107">Description</span></span>|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|<span data-ttu-id="b6ddd-108">Gibt an, dass nur die Microsoft Intermediate Language (MSIL) in der ausführbaren Datei überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="b6ddd-108">Specifies that only the Microsoft intermediate language (MSIL) in the executable file should be validated.</span></span>|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|<span data-ttu-id="b6ddd-109">Gibt an, dass nur das Format der ausführbaren Datei überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="b6ddd-109">Specifies that only the format of the executable file should be validated.</span></span>|  
|`VALIDATOR_EXTRA_VERBOSE`|<span data-ttu-id="b6ddd-110">Gibt an, dass alle Validierungs Typen ausgeführt und gemeldet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b6ddd-110">Specifies that all types of validation should be performed and reported on.</span></span>|  
|`VALIDATOR_NOCHECK_PEFORMAT`|<span data-ttu-id="b6ddd-111">Gibt an, dass das Format der ausführbaren Datei nicht überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="b6ddd-111">Specifies that the format of the executable file should not be validated.</span></span>|  
|`VALIDATOR_SHOW_SOURCE_LINES`|<span data-ttu-id="b6ddd-112">Gibt an, dass Validierungs Fehlermeldungen die Zeilen des Quellcodes einschließen sollen, durch die Validierungs Fehler ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b6ddd-112">Specifies that validation error messages should include the lines of source code that raise validation errors.</span></span> <span data-ttu-id="b6ddd-113">Dieser Feldwert ist in der .NET Framework-Version 2,0 ungültig.</span><span class="sxs-lookup"><span data-stu-id="b6ddd-113">This field value is not valid in the .NET Framework version 2.0.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b6ddd-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b6ddd-114">Requirements</span></span>  

 <span data-ttu-id="b6ddd-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6ddd-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6ddd-116">**Header:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="b6ddd-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="b6ddd-117">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b6ddd-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6ddd-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6ddd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6ddd-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6ddd-119">See also</span></span>

- [<span data-ttu-id="b6ddd-120">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b6ddd-120">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="b6ddd-121">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="b6ddd-121">Hosting Enumerations</span></span>](hosting-enumerations.md)

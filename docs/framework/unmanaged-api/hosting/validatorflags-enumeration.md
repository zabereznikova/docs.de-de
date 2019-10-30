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
ms.openlocfilehash: 61aafb8dc99bb908fc603945ff6ea74054f812c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141423"
---
# <a name="validatorflags-enumeration"></a><span data-ttu-id="e82b8-102">ValidatorFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e82b8-102">ValidatorFlags Enumeration</span></span>
<span data-ttu-id="e82b8-103">Enthält Werte, die den Validierungstyp angeben, der bei einem Rückruf der [ICLRValidator:: Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) -Methode ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e82b8-103">Contains values that indicate the type of validation that should be performed in a call to the [ICLRValidator::Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e82b8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e82b8-104">Syntax</span></span>  
  
```cpp  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a><span data-ttu-id="e82b8-105">Member</span><span class="sxs-lookup"><span data-stu-id="e82b8-105">Members</span></span>  
  
|<span data-ttu-id="e82b8-106">Member</span><span class="sxs-lookup"><span data-stu-id="e82b8-106">Member</span></span>|<span data-ttu-id="e82b8-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e82b8-107">Description</span></span>|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|<span data-ttu-id="e82b8-108">Gibt an, dass nur die Microsoft Intermediate Language (MSIL) in der ausführbaren Datei überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="e82b8-108">Specifies that only the Microsoft intermediate language (MSIL) in the executable file should be validated.</span></span>|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|<span data-ttu-id="e82b8-109">Gibt an, dass nur das Format der ausführbaren Datei überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="e82b8-109">Specifies that only the format of the executable file should be validated.</span></span>|  
|`VALIDATOR_EXTRA_VERBOSE`|<span data-ttu-id="e82b8-110">Gibt an, dass alle Validierungs Typen ausgeführt und gemeldet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e82b8-110">Specifies that all types of validation should be performed and reported on.</span></span>|  
|`VALIDATOR_NOCHECK_PEFORMAT`|<span data-ttu-id="e82b8-111">Gibt an, dass das Format der ausführbaren Datei nicht überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="e82b8-111">Specifies that the format of the executable file should not be validated.</span></span>|  
|`VALIDATOR_SHOW_SOURCE_LINES`|<span data-ttu-id="e82b8-112">Gibt an, dass Validierungs Fehlermeldungen die Zeilen des Quellcodes einschließen sollen, durch die Validierungs Fehler ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e82b8-112">Specifies that validation error messages should include the lines of source code that raise validation errors.</span></span> <span data-ttu-id="e82b8-113">Dieser Feldwert ist in der .NET Framework-Version 2,0 ungültig.</span><span class="sxs-lookup"><span data-stu-id="e82b8-113">This field value is not valid in the .NET Framework version 2.0.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e82b8-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e82b8-114">Requirements</span></span>  
 <span data-ttu-id="e82b8-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e82b8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e82b8-116">**Header:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="e82b8-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="e82b8-117">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e82b8-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e82b8-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e82b8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e82b8-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e82b8-119">See also</span></span>

- [<span data-ttu-id="e82b8-120">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e82b8-120">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="e82b8-121">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="e82b8-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

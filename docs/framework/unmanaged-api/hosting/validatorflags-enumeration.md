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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20ce52108c1024ad3e07051b226aa65612580e2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441387"
---
# <a name="validatorflags-enumeration"></a><span data-ttu-id="f4452-102">ValidatorFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="f4452-102">ValidatorFlags Enumeration</span></span>
<span data-ttu-id="f4452-103">Enthält Werte, die den Typ der Überprüfung angeben, die in einem Aufruf ausgeführt werden, sollten die [ICLRValidator:: Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="f4452-103">Contains values that indicate the type of validation that should be performed in a call to the [ICLRValidator::Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4452-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f4452-104">Syntax</span></span>  
  
```  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a><span data-ttu-id="f4452-105">Member</span><span class="sxs-lookup"><span data-stu-id="f4452-105">Members</span></span>  
  
|<span data-ttu-id="f4452-106">Member</span><span class="sxs-lookup"><span data-stu-id="f4452-106">Member</span></span>|<span data-ttu-id="f4452-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4452-107">Description</span></span>|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|<span data-ttu-id="f4452-108">Gibt an, dass nur die Microsoft intermediate Language (MSIL) in der ausführbaren Datei überprüft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f4452-108">Specifies that only the Microsoft intermediate language (MSIL) in the executable file should be validated.</span></span>|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|<span data-ttu-id="f4452-109">Gibt an, dass nur das Format der ausführbaren Datei überprüft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f4452-109">Specifies that only the format of the executable file should be validated.</span></span>|  
|`VALIDATOR_EXTRA_VERBOSE`|<span data-ttu-id="f4452-110">Gibt an, dass alle Typen der Überprüfung ausgeführt und auf gemeldet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f4452-110">Specifies that all types of validation should be performed and reported on.</span></span>|  
|`VALIDATOR_NOCHECK_PEFORMAT`|<span data-ttu-id="f4452-111">Gibt an, dass das Format der ausführbaren Datei nicht überprüft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f4452-111">Specifies that the format of the executable file should not be validated.</span></span>|  
|`VALIDATOR_SHOW_SOURCE_LINES`|<span data-ttu-id="f4452-112">Gibt an, dass es sich bei Überprüfungsfehlermeldungen die Quellcodezeilen enthalten soll, die Validierungsfehler auslösen.</span><span class="sxs-lookup"><span data-stu-id="f4452-112">Specifies that validation error messages should include the lines of source code that raise validation errors.</span></span> <span data-ttu-id="f4452-113">Der Wert dieses Felds ist ungültig in .NET Framework, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="f4452-113">This field value is not valid in the .NET Framework version 2.0.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f4452-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f4452-114">Requirements</span></span>  
 <span data-ttu-id="f4452-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4452-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4452-116">**Header:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="f4452-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="f4452-117">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="f4452-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f4452-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4452-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4452-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4452-119">See Also</span></span>  
 [<span data-ttu-id="f4452-120">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f4452-120">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [<span data-ttu-id="f4452-121">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="f4452-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)

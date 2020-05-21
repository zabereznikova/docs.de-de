---
title: ICLRValidator-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator
helpviewer_keywords:
- ICLRValidator interface [.NET Framework hosting]
ms.assetid: 2edd0a10-77fb-4173-91eb-f2970cc364d0
topic_type:
- apiref
ms.openlocfilehash: e071f9cba7e991c59bf697647e0e4badea57573a
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762039"
---
# <a name="iclrvalidator-interface"></a><span data-ttu-id="159fd-102">ICLRValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="159fd-102">ICLRValidator Interface</span></span>
<span data-ttu-id="159fd-103">Stellt Methoden zum Überprüfen von PE-Images (portable ausführbare Dateien) und zum Melden von Validierungs Fehlern bereit.</span><span class="sxs-lookup"><span data-stu-id="159fd-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="159fd-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="159fd-104">Methods</span></span>  
  
|<span data-ttu-id="159fd-105">Methode</span><span class="sxs-lookup"><span data-stu-id="159fd-105">Method</span></span>|<span data-ttu-id="159fd-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="159fd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="159fd-107">FormatEventInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="159fd-107">FormatEventInfo Method</span></span>](iclrvalidator-formateventinfo-method.md)|<span data-ttu-id="159fd-108">Ruft eine ausführliche Meldung über den angegebenen Validierungs Fehler ab.</span><span class="sxs-lookup"><span data-stu-id="159fd-108">Gets a detailed message about the specified validation error.</span></span>|  
|[<span data-ttu-id="159fd-109">Validate-Methode</span><span class="sxs-lookup"><span data-stu-id="159fd-109">Validate Method</span></span>](iclrvalidator-validate-method.md)|<span data-ttu-id="159fd-110">Überprüft die portable ausführbare Datei oder Microsoft Intermediate Language (MSIL) in der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="159fd-110">Validates the portable executable or Microsoft intermediate language (MSIL) in the specified file.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="159fd-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="159fd-111">Requirements</span></span>  
 <span data-ttu-id="159fd-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="159fd-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="159fd-113">**Header:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="159fd-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="159fd-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="159fd-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="159fd-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="159fd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="159fd-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="159fd-116">See also</span></span>

- [<span data-ttu-id="159fd-117">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="159fd-117">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="159fd-118">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="159fd-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="159fd-119">CLRRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="159fd-119">CLRRuntimeHost Coclass</span></span>](clrruntimehost-coclass.md)

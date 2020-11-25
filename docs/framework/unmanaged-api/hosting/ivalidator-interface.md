---
title: IValidator-Schnittstelle
ms.date: 03/30/2017
api_name:
- IValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IValidator
helpviewer_keywords:
- IValidator interface [.NET Framework hosting]
ms.assetid: b297e3b0-20f9-478f-b707-5e2eecb2b5b2
topic_type:
- apiref
ms.openlocfilehash: ce417402231d03828243bfb8bb7543c0a644a882
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700989"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="26ec4-102">IValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="26ec4-102">IValidator Interface</span></span>

<span data-ttu-id="26ec4-103">Stellt Methoden zum Überprüfen von PE-Images (portable ausführbare Dateien) und zum Melden von Validierungs Fehlern bereit.</span><span class="sxs-lookup"><span data-stu-id="26ec4-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="26ec4-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="26ec4-104">Methods</span></span>  
  
|<span data-ttu-id="26ec4-105">Methode</span><span class="sxs-lookup"><span data-stu-id="26ec4-105">Method</span></span>|<span data-ttu-id="26ec4-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="26ec4-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="26ec4-107">Überprüfen</span><span class="sxs-lookup"><span data-stu-id="26ec4-107">Validate</span></span>|<span data-ttu-id="26ec4-108">Überprüft die angegebene PE-oder MSIL-Datei (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="26ec4-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="26ec4-109">Format Event Info</span><span class="sxs-lookup"><span data-stu-id="26ec4-109">FormatEventInfo</span></span>|<span data-ttu-id="26ec4-110">Ruft die Fehlermeldung ab, die dem angegebenen Validierungs Fehler entspricht.</span><span class="sxs-lookup"><span data-stu-id="26ec4-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="26ec4-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="26ec4-111">Requirements</span></span>  

 <span data-ttu-id="26ec4-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26ec4-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26ec4-113">**Header:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="26ec4-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="26ec4-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="26ec4-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="26ec4-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26ec4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26ec4-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26ec4-116">See also</span></span>

- [<span data-ttu-id="26ec4-117">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="26ec4-117">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="26ec4-118">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="26ec4-118">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)

---
title: CreateALink-Funktion
ms.date: 03/30/2017
api_name:
- CreateALink
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b494b8b776f4cb0eb534233c5a03ab2d34a698ef
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115621"
---
# <a name="createalink-function"></a><span data-ttu-id="6d2f7-102">CreateALink-Funktion</span><span class="sxs-lookup"><span data-stu-id="6d2f7-102">CreateALink Function</span></span>
<span data-ttu-id="6d2f7-103">Erstellt eine Instanz der Assembly Linker und setzt einen Zeiger auf die angegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6d2f7-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d2f7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d2f7-104">Syntax</span></span>  
  
```  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d2f7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6d2f7-105">Parameters</span></span>  
  
|<span data-ttu-id="6d2f7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6d2f7-106">Parameter</span></span>|<span data-ttu-id="6d2f7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d2f7-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="6d2f7-108">Der physische Name einer Assemblylinker-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="6d2f7-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="6d2f7-109">Das Verzeichnis, bei erfolgreichem Abschluss einen Zeiger auf die `riid` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6d2f7-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6d2f7-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6d2f7-110">Requirements</span></span>  
 <span data-ttu-id="6d2f7-111">**Bibliothek**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="6d2f7-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d2f7-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d2f7-112">See also</span></span>

- [<span data-ttu-id="6d2f7-113">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="6d2f7-113">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)

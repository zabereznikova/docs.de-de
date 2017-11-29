---
title: CreateALink-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateALink
api_location: alink.dll
api_type: DLLExport
f1_keywords: CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a102e9601f751ee8c7e325293e83467b1314ff41
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="createalink-function"></a><span data-ttu-id="91a93-102">CreateALink-Funktion</span><span class="sxs-lookup"><span data-stu-id="91a93-102">CreateALink Function</span></span>
<span data-ttu-id="91a93-103">Erstellt eine Instanz der Assembly Linker aus, und legt einen Zeiger auf die angegebene Schnittstelle fest.</span><span class="sxs-lookup"><span data-stu-id="91a93-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91a93-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="91a93-104">Syntax</span></span>  
  
```  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="91a93-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="91a93-105">Parameters</span></span>  
  
|<span data-ttu-id="91a93-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="91a93-106">Parameter</span></span>|<span data-ttu-id="91a93-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91a93-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="91a93-108">Der physische Name einer Assembly Linker-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="91a93-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="91a93-109">Das Verzeichnis, bei erfolgreichem Abschluss einen Zeiger auf die `riid` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="91a93-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="91a93-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="91a93-110">Requirements</span></span>  
 <span data-ttu-id="91a93-111">**Bibliothek**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="91a93-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a93-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91a93-112">See Also</span></span>  
 [<span data-ttu-id="91a93-113">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="91a93-113">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)

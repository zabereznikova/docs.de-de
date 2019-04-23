---
title: GetALinkMessageDll-Funktion
ms.date: 03/30/2017
api_name:
- GetALinkMessageDll
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: edd83e62b08aa7892c01577cd8c46f9d965c0894
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163019"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="00918-102">GetALinkMessageDll-Funktion</span><span class="sxs-lookup"><span data-stu-id="00918-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="00918-103">Sucht und lädt die Meldungs-DLL.</span><span class="sxs-lookup"><span data-stu-id="00918-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="00918-104">Gibt 0 zurück, wenn die Meldungs-DLL nicht gefunden oder geladen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="00918-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="00918-105">Die Meldungs-DLL muss in einem Unterverzeichnis, deren Name eine Sprachen-ID ist, oder im aktuellen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="00918-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00918-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="00918-106">Syntax</span></span>  
  
```  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="00918-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00918-107">Requirements</span></span>  
 <span data-ttu-id="00918-108">**Header:** alink.h</span><span class="sxs-lookup"><span data-stu-id="00918-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="00918-109">**Bibliothek**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="00918-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00918-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00918-110">See also</span></span>

- [<span data-ttu-id="00918-111">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="00918-111">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)

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
ms.openlocfilehash: 554bd32ae965b21a88a09577749bbd7975f5ec7e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684745"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="cb698-102">GetALinkMessageDll-Funktion</span><span class="sxs-lookup"><span data-stu-id="cb698-102">GetALinkMessageDll Function</span></span>

<span data-ttu-id="cb698-103">Sucht und lädt die Nachrichten-dll.</span><span class="sxs-lookup"><span data-stu-id="cb698-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="cb698-104">Gibt 0 zurück, wenn die Nachrichten-DLL nicht gefunden oder geladen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="cb698-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="cb698-105">Die Nachrichten-DLL muss sich entweder in einem Unterverzeichnis befinden, dessen Name eine Sprach-ID oder im aktuellen Verzeichnis ist.</span><span class="sxs-lookup"><span data-stu-id="cb698-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb698-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb698-106">Syntax</span></span>  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="cb698-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cb698-107">Requirements</span></span>  

 <span data-ttu-id="cb698-108">**Header:** Alink. h</span><span class="sxs-lookup"><span data-stu-id="cb698-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="cb698-109">**Bibliothek**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="cb698-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb698-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb698-110">See also</span></span>

- [<span data-ttu-id="cb698-111">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="cb698-111">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)

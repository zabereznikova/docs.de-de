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
ms.openlocfilehash: 323e53c45a26d5703548ebe9863978f6d3929f0b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787477"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="c2dbb-102">GetALinkMessageDll-Funktion</span><span class="sxs-lookup"><span data-stu-id="c2dbb-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="c2dbb-103">Sucht und lädt die Nachrichten-dll.</span><span class="sxs-lookup"><span data-stu-id="c2dbb-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="c2dbb-104">Gibt 0 zurück, wenn die Nachrichten-DLL nicht gefunden oder geladen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="c2dbb-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="c2dbb-105">Die Nachrichten-DLL muss sich entweder in einem Unterverzeichnis befinden, dessen Name eine Sprach-ID oder im aktuellen Verzeichnis ist.</span><span class="sxs-lookup"><span data-stu-id="c2dbb-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2dbb-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2dbb-106">Syntax</span></span>  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="c2dbb-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c2dbb-107">Requirements</span></span>  
 <span data-ttu-id="c2dbb-108">**Header:** Alink. h</span><span class="sxs-lookup"><span data-stu-id="c2dbb-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="c2dbb-109">**Bibliothek**: Alink. dll</span><span class="sxs-lookup"><span data-stu-id="c2dbb-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2dbb-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2dbb-110">See also</span></span>

- [<span data-ttu-id="c2dbb-111">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="c2dbb-111">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)

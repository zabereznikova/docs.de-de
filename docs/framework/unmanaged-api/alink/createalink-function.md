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
ms.openlocfilehash: 9165a4db7e65fb0f409a902b06d32e9c2988aa69
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446554"
---
# <a name="createalink-function"></a><span data-ttu-id="69a16-102">CreateALink-Funktion</span><span class="sxs-lookup"><span data-stu-id="69a16-102">CreateALink Function</span></span>
<span data-ttu-id="69a16-103">Erstellt eine Instanz des Assemblylinkers und legt einen Zeiger auf die angegebene-Schnittstelle fest.</span><span class="sxs-lookup"><span data-stu-id="69a16-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69a16-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="69a16-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69a16-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="69a16-105">Parameters</span></span>  
  
|<span data-ttu-id="69a16-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="69a16-106">Parameter</span></span>|<span data-ttu-id="69a16-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69a16-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="69a16-108">Der physische Name einer der Assembly Linker-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="69a16-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="69a16-109">Der Speicherort nach erfolgreichem Abschluss enthält einen Zeiger auf die `riid`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="69a16-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="69a16-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="69a16-110">Requirements</span></span>  
 <span data-ttu-id="69a16-111">**Bibliothek**: Alink. dll</span><span class="sxs-lookup"><span data-stu-id="69a16-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69a16-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69a16-112">See also</span></span>

- [<span data-ttu-id="69a16-113">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="69a16-113">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)

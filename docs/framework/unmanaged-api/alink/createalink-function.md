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
ms.openlocfilehash: 98c6ed4657dc69554a9fcca27145f65c621492f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683730"
---
# <a name="createalink-function"></a><span data-ttu-id="ae0d8-102">CreateALink-Funktion</span><span class="sxs-lookup"><span data-stu-id="ae0d8-102">CreateALink Function</span></span>

<span data-ttu-id="ae0d8-103">Erstellt eine Instanz des Assemblylinkers und legt einen Zeiger auf die angegebene-Schnittstelle fest.</span><span class="sxs-lookup"><span data-stu-id="ae0d8-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae0d8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae0d8-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae0d8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ae0d8-105">Parameters</span></span>  
  
|<span data-ttu-id="ae0d8-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ae0d8-106">Parameter</span></span>|<span data-ttu-id="ae0d8-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ae0d8-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="ae0d8-108">Der physische Name einer der Assembly Linker-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="ae0d8-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="ae0d8-109">Der Speicherort nach erfolgreichem Abschluss enthält einen Zeiger auf die- `riid` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ae0d8-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ae0d8-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ae0d8-110">Requirements</span></span>  

 <span data-ttu-id="ae0d8-111">**Bibliothek**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="ae0d8-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae0d8-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ae0d8-112">See also</span></span>

- [<span data-ttu-id="ae0d8-113">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="ae0d8-113">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)

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
ms.openlocfilehash: 24f7e2d5a547b78ceb4808feaf581c6f49807cf7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787619"
---
# <a name="createalink-function"></a><span data-ttu-id="c50cc-102">CreateALink-Funktion</span><span class="sxs-lookup"><span data-stu-id="c50cc-102">CreateALink Function</span></span>
<span data-ttu-id="c50cc-103">Erstellt eine Instanz des Assemblylinkers und legt einen Zeiger auf die angegebene-Schnittstelle fest.</span><span class="sxs-lookup"><span data-stu-id="c50cc-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c50cc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c50cc-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c50cc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c50cc-105">Parameters</span></span>  
  
|<span data-ttu-id="c50cc-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c50cc-106">Parameter</span></span>|<span data-ttu-id="c50cc-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c50cc-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="c50cc-108">Der physische Name einer der Assembly Linker-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="c50cc-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="c50cc-109">Der Speicherort nach erfolgreichem Abschluss enthält einen Zeiger auf `riid` die-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c50cc-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c50cc-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c50cc-110">Requirements</span></span>  
 <span data-ttu-id="c50cc-111">**Bibliothek**: Alink. dll</span><span class="sxs-lookup"><span data-stu-id="c50cc-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c50cc-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c50cc-112">See also</span></span>

- [<span data-ttu-id="c50cc-113">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="c50cc-113">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)

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
ms.openlocfilehash: 993848711f41c9e03b969a3c611982a5c8bc860d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742215"
---
# <a name="createalink-function"></a><span data-ttu-id="19e56-102">CreateALink-Funktion</span><span class="sxs-lookup"><span data-stu-id="19e56-102">CreateALink Function</span></span>
<span data-ttu-id="19e56-103">Erstellt eine Instanz der Assembly Linker und setzt einen Zeiger auf die angegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="19e56-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19e56-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="19e56-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19e56-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="19e56-105">Parameters</span></span>  
  
|<span data-ttu-id="19e56-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="19e56-106">Parameter</span></span>|<span data-ttu-id="19e56-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="19e56-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="19e56-108">Der physische Name einer Assemblylinker-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="19e56-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="19e56-109">Das Verzeichnis, bei erfolgreichem Abschluss einen Zeiger auf die `riid` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="19e56-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="19e56-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="19e56-110">Requirements</span></span>  
 <span data-ttu-id="19e56-111">**Bibliothek**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="19e56-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19e56-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19e56-112">See also</span></span>

- [<span data-ttu-id="19e56-113">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="19e56-113">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)

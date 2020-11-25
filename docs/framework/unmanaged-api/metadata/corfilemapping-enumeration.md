---
title: CorFileMapping-Enumeration
ms.date: 03/30/2017
api_name:
- CorFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileMapping
helpviewer_keywords:
- CorFileMapping enumeration [.NET Framework metadata]
ms.assetid: 3ca41592-b8da-475a-8032-a15627730003
topic_type:
- apiref
ms.openlocfilehash: 63e27a62e176a92b03c10b59a55d9da3192918f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726115"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="ca055-102">CorFileMapping-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ca055-102">CorFileMapping Enumeration</span></span>

<span data-ttu-id="ca055-103">Enthält Werte, die den Typ der Datei Zuordnung beschreiben, der von einem Aufrufen der [IMetaDataInfo:: GetFileMapping](imetadatainfo-getfilemapping-method.md) -Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ca055-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca055-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca055-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="ca055-105">Member</span><span class="sxs-lookup"><span data-stu-id="ca055-105">Members</span></span>  
  
|<span data-ttu-id="ca055-106">Member</span><span class="sxs-lookup"><span data-stu-id="ca055-106">Member</span></span>|<span data-ttu-id="ca055-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ca055-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="ca055-108">Die Datei wird als Datendatei zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ca055-108">The file is mapped as a data file.</span></span> <span data-ttu-id="ca055-109">Das heißt, dass das `SEC_IMAGE` Flag nicht an die Microsoft Win32-Funktion übermittelt wurde `CreateFileMapping` .</span><span class="sxs-lookup"><span data-stu-id="ca055-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="ca055-110">Die Datei wird für die Ausführung zugeordnet, entweder mithilfe der- `LoadLibrary` Funktion oder der- `CreateFileMapping` Funktion mit dem- `SEC_IMAGE` Flag.</span><span class="sxs-lookup"><span data-stu-id="ca055-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ca055-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ca055-111">Requirements</span></span>  

 <span data-ttu-id="ca055-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca055-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca055-113">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="ca055-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ca055-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca055-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca055-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ca055-115">See also</span></span>

- [<span data-ttu-id="ca055-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="ca055-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="ca055-117">GetFileMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="ca055-117">GetFileMapping Method</span></span>](imetadatainfo-getfilemapping-method.md)

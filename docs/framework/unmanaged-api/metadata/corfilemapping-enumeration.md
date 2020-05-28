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
ms.openlocfilehash: 0ed1579886f1682348a136be3391f6bdc2543d26
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007389"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="87a38-102">CorFileMapping-Enumeration</span><span class="sxs-lookup"><span data-stu-id="87a38-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="87a38-103">Enthält Werte, die den Typ der Datei Zuordnung beschreiben, der von einem Aufrufen der [IMetaDataInfo:: GetFileMapping](imetadatainfo-getfilemapping-method.md) -Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="87a38-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87a38-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="87a38-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="87a38-105">Member</span><span class="sxs-lookup"><span data-stu-id="87a38-105">Members</span></span>  
  
|<span data-ttu-id="87a38-106">Member</span><span class="sxs-lookup"><span data-stu-id="87a38-106">Member</span></span>|<span data-ttu-id="87a38-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87a38-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="87a38-108">Die Datei wird als Datendatei zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="87a38-108">The file is mapped as a data file.</span></span> <span data-ttu-id="87a38-109">Das heißt, dass das `SEC_IMAGE` Flag nicht an die Microsoft Win32-Funktion übermittelt wurde `CreateFileMapping` .</span><span class="sxs-lookup"><span data-stu-id="87a38-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="87a38-110">Die Datei wird für die Ausführung zugeordnet, entweder mithilfe der- `LoadLibrary` Funktion oder der- `CreateFileMapping` Funktion mit dem- `SEC_IMAGE` Flag.</span><span class="sxs-lookup"><span data-stu-id="87a38-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="87a38-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="87a38-111">Requirements</span></span>  
 <span data-ttu-id="87a38-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87a38-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87a38-113">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="87a38-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="87a38-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87a38-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87a38-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87a38-115">See also</span></span>

- [<span data-ttu-id="87a38-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="87a38-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="87a38-117">GetFileMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="87a38-117">GetFileMapping Method</span></span>](imetadatainfo-getfilemapping-method.md)

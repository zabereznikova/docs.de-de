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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 719f0522cc43625a4d6cc8afa838d869e47b40d1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781834"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="38da9-102">CorFileMapping-Enumeration</span><span class="sxs-lookup"><span data-stu-id="38da9-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="38da9-103">Enthält Werte, die den Typ der dateizuordnung zu beschreiben, die von einem Aufruf zurückgegeben wird, die [IMetaDataInfo:: GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="38da9-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38da9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="38da9-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="38da9-105">Member</span><span class="sxs-lookup"><span data-stu-id="38da9-105">Members</span></span>  
  
|<span data-ttu-id="38da9-106">Member</span><span class="sxs-lookup"><span data-stu-id="38da9-106">Member</span></span>|<span data-ttu-id="38da9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38da9-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="38da9-108">Die Datei wird als eine Datendatei zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="38da9-108">The file is mapped as a data file.</span></span> <span data-ttu-id="38da9-109">D. h. die `SEC_IMAGE` Flag wurde nicht übergeben, der Microsoft Win32 `CreateFileMapping` Funktion.</span><span class="sxs-lookup"><span data-stu-id="38da9-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="38da9-110">Die Datei wird für die Ausführung zugeordnet, indem Sie entweder die `LoadLibrary` Funktion oder die `CreateFileMapping` -Funktion mit den `SEC_IMAGE` Flag.</span><span class="sxs-lookup"><span data-stu-id="38da9-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38da9-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="38da9-111">Requirements</span></span>  
 <span data-ttu-id="38da9-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38da9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38da9-113">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="38da9-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="38da9-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38da9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38da9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38da9-115">See also</span></span>

- [<span data-ttu-id="38da9-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="38da9-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="38da9-117">GetFileMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="38da9-117">GetFileMapping Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)

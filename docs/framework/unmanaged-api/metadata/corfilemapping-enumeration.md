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
ms.openlocfilehash: 3c8864aa604b0483130eac5aa0d7c0640abbac99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443722"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="e44a1-102">CorFileMapping-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e44a1-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="e44a1-103">Enthält Werte, die den Dateizuordnungstyp beschreiben, die von einem Aufruf zurückgegeben wird, das [IMetaDataInfo:: GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="e44a1-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e44a1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e44a1-104">Syntax</span></span>  
  
```  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="e44a1-105">Member</span><span class="sxs-lookup"><span data-stu-id="e44a1-105">Members</span></span>  
  
|<span data-ttu-id="e44a1-106">Member</span><span class="sxs-lookup"><span data-stu-id="e44a1-106">Member</span></span>|<span data-ttu-id="e44a1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e44a1-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="e44a1-108">Die Datei wird als Datendatei zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e44a1-108">The file is mapped as a data file.</span></span> <span data-ttu-id="e44a1-109">D. h. die `SEC_IMAGE` Flag wurde nicht übergeben, um die Microsoft Win32 `CreateFileMapping` Funktion.</span><span class="sxs-lookup"><span data-stu-id="e44a1-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="e44a1-110">Die Datei wird zur Ausführung zugeordnet, indem Sie entweder die `LoadLibrary` Funktion oder die `CreateFileMapping` -Funktion mit dem `SEC_IMAGE` Flag.</span><span class="sxs-lookup"><span data-stu-id="e44a1-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e44a1-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e44a1-111">Requirements</span></span>  
 <span data-ttu-id="e44a1-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e44a1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e44a1-113">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="e44a1-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e44a1-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e44a1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e44a1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e44a1-115">See Also</span></span>  
 [<span data-ttu-id="e44a1-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="e44a1-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="e44a1-117">GetFileMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="e44a1-117">GetFileMapping Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)

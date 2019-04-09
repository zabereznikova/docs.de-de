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
ms.openlocfilehash: a3056836d289383161f9fa538c3c6349f88b6ba6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175616"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="6e626-102">CorFileMapping-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6e626-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="6e626-103">Enthält Werte, die den Typ der dateizuordnung zu beschreiben, die von einem Aufruf zurückgegeben wird, die [IMetaDataInfo:: GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="6e626-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e626-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e626-104">Syntax</span></span>  
  
```  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="6e626-105">Member</span><span class="sxs-lookup"><span data-stu-id="6e626-105">Members</span></span>  
  
|<span data-ttu-id="6e626-106">Member</span><span class="sxs-lookup"><span data-stu-id="6e626-106">Member</span></span>|<span data-ttu-id="6e626-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e626-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="6e626-108">Die Datei wird als eine Datendatei zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="6e626-108">The file is mapped as a data file.</span></span> <span data-ttu-id="6e626-109">D. h. die `SEC_IMAGE` Flag wurde nicht übergeben, der Microsoft Win32 `CreateFileMapping` Funktion.</span><span class="sxs-lookup"><span data-stu-id="6e626-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="6e626-110">Die Datei wird für die Ausführung zugeordnet, indem Sie entweder die `LoadLibrary` Funktion oder die `CreateFileMapping` -Funktion mit den `SEC_IMAGE` Flag.</span><span class="sxs-lookup"><span data-stu-id="6e626-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6e626-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6e626-111">Requirements</span></span>  
 <span data-ttu-id="6e626-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e626-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e626-113">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="6e626-113">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="6e626-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="6e626-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6e626-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e626-115">See also</span></span>

- [<span data-ttu-id="6e626-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="6e626-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="6e626-117">GetFileMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="6e626-117">GetFileMapping Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)

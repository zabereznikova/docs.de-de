---
title: AddFile-Methode1
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 84b68638ed0f7a86156cf7e5fcc98d3c02cba18a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662607"
---
# <a name="addfile-method1"></a><span data-ttu-id="7c865-102">AddFile-Methode1</span><span class="sxs-lookup"><span data-stu-id="7c865-102">AddFile Method1</span></span>
<span data-ttu-id="7c865-103">Dateien hinzugefügt der Assembly.</span><span class="sxs-lookup"><span data-stu-id="7c865-103">Adds files to the assembly.</span></span> <span data-ttu-id="7c865-104">Kann auch zum Erstellen von ungebundener Modules verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c865-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c865-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c865-105">Syntax</span></span>  
  
```  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c865-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="7c865-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="7c865-107">Eindeutige ID der Assembly, die erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="7c865-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="7c865-108">Voll gekennzeichnete Name der hinzuzufügenden Datei um.</span><span class="sxs-lookup"><span data-stu-id="7c865-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7c865-109">COM+ FileDef-flags, z. B. `ffContainsNoMetaData` und `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="7c865-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="7c865-110">`dwFlags` wird zum übergeben [DefineFile-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="7c865-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="7c865-111">[IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) Schnittstelle, die zum Ausgeben von Metadaten verwendet werden, bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="7c865-111">[IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="7c865-112">Zeiger auf, wo die eindeutige ID der hinzugefügten Datei gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7c865-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c865-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7c865-113">Return Value</span></span>  
 <span data-ttu-id="7c865-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="7c865-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c865-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7c865-115">Requirements</span></span>  
 <span data-ttu-id="7c865-116">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="7c865-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c865-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c865-117">See also</span></span>
- [<span data-ttu-id="7c865-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c865-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="7c865-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c865-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="7c865-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="7c865-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

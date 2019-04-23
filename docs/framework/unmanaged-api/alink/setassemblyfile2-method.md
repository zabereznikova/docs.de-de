---
title: SetAssemblyFile2-Methode
ms.date: 03/30/2017
api_name:
- IALink2.SetAssemblyFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile2
helpviewer_keywords:
- SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 59bfc6785d3ad195e219afc323b7fdb513d8fefc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092564"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="3673e-102">SetAssemblyFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="3673e-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="3673e-103">Legt fest, den Namen und die Optionen für eine neue Assembly.</span><span class="sxs-lookup"><span data-stu-id="3673e-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="3673e-104">Rufen Sie diese Methode nicht, wenn Sie die ungebundene Modulen erstellen.</span><span class="sxs-lookup"><span data-stu-id="3673e-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3673e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3673e-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3673e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="3673e-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="3673e-107">Der Name der Manifestdatei.</span><span class="sxs-lookup"><span data-stu-id="3673e-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="3673e-108">[IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) -Schnittstelle für diese Datei.</span><span class="sxs-lookup"><span data-stu-id="3673e-108">[IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="3673e-109">Optionen durch dargestellt [AssemblyFlags-Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="3673e-109">Options represented by [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="3673e-110">Empfängt die eindeutige ID für die Assembly, die erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="3673e-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3673e-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3673e-111">Return Value</span></span>  
 <span data-ttu-id="3673e-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="3673e-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3673e-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3673e-113">Requirements</span></span>  
 <span data-ttu-id="3673e-114">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="3673e-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3673e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3673e-115">See also</span></span>

- [<span data-ttu-id="3673e-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3673e-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="3673e-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3673e-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="3673e-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="3673e-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

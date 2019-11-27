---
title: ImportFile2-Methode
ms.date: 03/30/2017
api_name:
- IALink.ImportFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile2
helpviewer_keywords:
- ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type:
- apiref
ms.openlocfilehash: 17f158167d4075783d1aa594fb61cc9e28d30dd7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446983"
---
# <a name="importfile2-method"></a><span data-ttu-id="4b7e9-102">ImportFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="4b7e9-102">ImportFile2 Method</span></span>
<span data-ttu-id="4b7e9-103">Importiert Assemblys und ungebundene Module.</span><span class="sxs-lookup"><span data-stu-id="4b7e9-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="4b7e9-104">Diese Methode verhält sich wie die [ImportFile-Methode](importfile-method.md), funktioniert aber auch dann, wenn die zu importierende Datei nicht auf dem Datenträger vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4b7e9-104">This method is like [ImportFile Method](importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b7e9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b7e9-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b7e9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4b7e9-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="4b7e9-107">Der Name der zu importierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="4b7e9-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="4b7e9-108">Optionaler Name der Ausgabedatei, die verwendet werden kann, um die Datei umzubenennen, wenn Sie mit der Assembly verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="4b7e9-108">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="4b7e9-109">Optionaler Bereich der [IMetaDataAssemblyImport-Schnittstelle](../metadata/imetadataassemblyimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4b7e9-109">Optional scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="4b7e9-110">TRUE gibt an, dass ImportTypes verwendet wird. andernfalls muss der Import manuell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4b7e9-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="4b7e9-111">Empfängt die ID für die Datei oder Assembly.</span><span class="sxs-lookup"><span data-stu-id="4b7e9-111">Receives the ID for the file or assembly.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="4b7e9-112">Empfängt die Schnittstelle der [IMetaDataAssemblyImport-Schnittstelle](../metadata/imetadataassemblyimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4b7e9-112">Receives the [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="4b7e9-113">NULL, wenn die Datei keine Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="4b7e9-113">NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="4b7e9-114">Empfängt die gefundenen Dateien und/oder Bereiche, die importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="4b7e9-114">Receives the found of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b7e9-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4b7e9-115">Return Value</span></span>  
 <span data-ttu-id="4b7e9-116">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="4b7e9-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b7e9-117">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4b7e9-117">Requirements</span></span>  
 <span data-ttu-id="4b7e9-118">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="4b7e9-118">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b7e9-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b7e9-119">See also</span></span>

- [<span data-ttu-id="4b7e9-120">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4b7e9-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="4b7e9-121">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4b7e9-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="4b7e9-122">Alink-API</span><span class="sxs-lookup"><span data-stu-id="4b7e9-122">ALink API</span></span>](index.md)

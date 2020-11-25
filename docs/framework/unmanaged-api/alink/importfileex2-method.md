---
title: ImportFileEx2-Methode
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx2
helpviewer_keywords:
- ImportFileEx2 method
ms.assetid: 02c789fd-16fc-48c6-9619-56e87e2a37ca
topic_type:
- apiref
ms.openlocfilehash: 59149e79e926a0b9a3e549e013bf178e54ddf6fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705175"
---
# <a name="importfileex2-method"></a><span data-ttu-id="69c0e-102">ImportFileEx2-Methode</span><span class="sxs-lookup"><span data-stu-id="69c0e-102">ImportFileEx2 Method</span></span>

<span data-ttu-id="69c0e-103">Importiert Assemblys und ungebundene Module.</span><span class="sxs-lookup"><span data-stu-id="69c0e-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="69c0e-104">Diese Methode verhält sich wie die [ImportFile-Methode](importfile-method.md), funktioniert aber auch dann, wenn die zu importierende Datei nicht auf dem Datenträger vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="69c0e-104">This method is like [ImportFile Method](importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69c0e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="69c0e-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportFileEx2(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="69c0e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="69c0e-106">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="69c0e-107">Der Name der zu importierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="69c0e-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="69c0e-108">Optionaler Name der Zieldatei.</span><span class="sxs-lookup"><span data-stu-id="69c0e-108">Optional name of target file.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="69c0e-109">Optionaler Import Bereich [IMetaDataAssemblyImport Schnittstellen](../metadata/imetadataassemblyimport-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="69c0e-109">Optional import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="69c0e-110">TRUE gibt an, dass ImportTypes verwendet wird. andernfalls muss der Import manuell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="69c0e-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="69c0e-111">Flags, die an die [OpenScope-Methode](../metadata/imetadatadispenser-openscope-method.md)weitergegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="69c0e-111">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="69c0e-112">Empfängt eine eindeutige ID für die Assembly oder Datei.</span><span class="sxs-lookup"><span data-stu-id="69c0e-112">Receives unique ID for the assembly or file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="69c0e-113">Empfängt assemblyimportierungsbereich [IMetaDataAssemblyImport Schnittstellen](../metadata/imetadataassemblyimport-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="69c0e-113">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="69c0e-114">Kann NULL sein, wenn die Datei keine Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="69c0e-114">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="69c0e-115">Empfängt die Anzahl der importierten Dateien und/oder Bereiche.</span><span class="sxs-lookup"><span data-stu-id="69c0e-115">Receives the number of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="69c0e-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="69c0e-116">Return Value</span></span>  

 <span data-ttu-id="69c0e-117">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="69c0e-117">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69c0e-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="69c0e-118">Requirements</span></span>  

 <span data-ttu-id="69c0e-119">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="69c0e-119">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69c0e-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69c0e-120">See also</span></span>

- [<span data-ttu-id="69c0e-121">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="69c0e-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="69c0e-122">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="69c0e-122">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="69c0e-123">ALink-API</span><span class="sxs-lookup"><span data-stu-id="69c0e-123">ALink API</span></span>](index.md)

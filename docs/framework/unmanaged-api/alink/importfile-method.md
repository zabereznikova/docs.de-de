---
title: ImportFile-Methode
ms.date: 03/30/2017
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
ms.openlocfilehash: cda6d90865f8ad2b9d565f6a6378c35b03c65bf7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446995"
---
# <a name="importfile-method"></a><span data-ttu-id="28eec-102">ImportFile-Methode</span><span class="sxs-lookup"><span data-stu-id="28eec-102">ImportFile Method</span></span>
<span data-ttu-id="28eec-103">Importiert Assemblys und ungebundene Module.</span><span class="sxs-lookup"><span data-stu-id="28eec-103">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28eec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="28eec-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="28eec-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="28eec-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="28eec-106">Der voll qualifizierte Name der zu importierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="28eec-106">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="28eec-107">Optionaler Name der Ausgabedatei, die verwendet werden kann, um die Datei umzubenennen, wenn Sie mit der Assembly verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="28eec-107">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="28eec-108">TRUE gibt an, dass ImportTypes verwendet wird. andernfalls muss der Import manuell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="28eec-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="28eec-109">Zeiger auf das Token, in dem eine eindeutige Datei-ID gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="28eec-109">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="28eec-110">Bei der Datei kann es sich um eine Assembly oder eine Datei handeln.</span><span class="sxs-lookup"><span data-stu-id="28eec-110">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="28eec-111">Empfängt einen Zeiger auf die [IMetaDataAssemblyImport-Schnittstelle](../metadata/imetadataassemblyimport-interface.md).</span><span class="sxs-lookup"><span data-stu-id="28eec-111">Receives pointer to [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="28eec-112">Kann NULL sein, wenn die Datei keine Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="28eec-112">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="28eec-113">Zeiger auf die Anzahl der importierten Dateien und/oder Bereiche.</span><span class="sxs-lookup"><span data-stu-id="28eec-113">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28eec-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="28eec-114">Return Value</span></span>  
 <span data-ttu-id="28eec-115">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="28eec-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28eec-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="28eec-116">Requirements</span></span>  
 <span data-ttu-id="28eec-117">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="28eec-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28eec-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28eec-118">See also</span></span>

- [<span data-ttu-id="28eec-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="28eec-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="28eec-120">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="28eec-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="28eec-121">Alink-API</span><span class="sxs-lookup"><span data-stu-id="28eec-121">ALink API</span></span>](index.md)

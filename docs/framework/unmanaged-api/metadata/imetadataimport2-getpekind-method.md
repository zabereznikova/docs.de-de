---
title: IMetaDataImport2::GetPEKind-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetPEKind
helpviewer_keywords:
- GetPEKind method [.NET Framework metadata]
- IMetaDataImport2::GetPEKind method [.NET Framework metadata]
ms.assetid: d91c3d89-8022-4a4c-a2a2-a8af2c387507
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d9dda1fb38546138d52b5fe61754d5497e676c37
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113481"
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="3b672-102">IMetaDataImport2::GetPEKind-Methode</span><span class="sxs-lookup"><span data-stu-id="3b672-102">IMetaDataImport2::GetPEKind Method</span></span>
<span data-ttu-id="3b672-103">Ruft einen Wert, der das Bestimmen der Art des Codes in der portierbaren ausführbaren Datei (PE) Datei, in der Regel eine DLL oder EXE-Datei, die im aktuellen Metadatenbereich definiert ist.</span><span class="sxs-lookup"><span data-stu-id="3b672-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b672-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3b672-104">Syntax</span></span>  
  
```  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b672-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3b672-105">Parameters</span></span>  
 `pdwPEKind`  
 <span data-ttu-id="3b672-106">[out] Ein Zeiger auf den Wert der [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) -Enumeration, die PE-Datei beschreibt.</span><span class="sxs-lookup"><span data-stu-id="3b672-106">[out] A pointer to a value of the [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="3b672-107">[out] Ein Zeiger auf einen Wert ab, die Architektur des Computers identifiziert.</span><span class="sxs-lookup"><span data-stu-id="3b672-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="3b672-108">Finden Sie im nächsten Abschnitt Mögliche Werte.</span><span class="sxs-lookup"><span data-stu-id="3b672-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b672-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3b672-109">Remarks</span></span>  
 <span data-ttu-id="3b672-110">Der Wert, der auf die verwiesen wird durch die `pdwMachine` Parameter kann einen der folgenden sein.</span><span class="sxs-lookup"><span data-stu-id="3b672-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="3b672-111">Wert</span><span class="sxs-lookup"><span data-stu-id="3b672-111">Value</span></span>|<span data-ttu-id="3b672-112">Architektur des Computers</span><span class="sxs-lookup"><span data-stu-id="3b672-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="3b672-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="3b672-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="3b672-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="3b672-114">0x014C</span></span>|<span data-ttu-id="3b672-115">x86</span><span class="sxs-lookup"><span data-stu-id="3b672-115">x86</span></span>|  
|<span data-ttu-id="3b672-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="3b672-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="3b672-117">0x0200</span><span class="sxs-lookup"><span data-stu-id="3b672-117">0x0200</span></span>|<span data-ttu-id="3b672-118">Intel IPF</span><span class="sxs-lookup"><span data-stu-id="3b672-118">Intel IPF</span></span>|  
|<span data-ttu-id="3b672-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="3b672-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="3b672-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="3b672-120">0x8664</span></span>|<span data-ttu-id="3b672-121">x64</span><span class="sxs-lookup"><span data-stu-id="3b672-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3b672-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3b672-122">Requirements</span></span>  
 <span data-ttu-id="3b672-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b672-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b672-124">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3b672-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3b672-125">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="3b672-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3b672-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b672-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b672-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b672-127">See also</span></span>

- [<span data-ttu-id="3b672-128">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3b672-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="3b672-129">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3b672-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3b672-130">CorPEKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="3b672-130">CorPEKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)

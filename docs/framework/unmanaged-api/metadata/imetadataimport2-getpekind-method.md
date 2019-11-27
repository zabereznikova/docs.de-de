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
ms.openlocfilehash: 0464c61e4ff01483e10fb5708d5ed4b5f5ed63d0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445236"
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="6ddba-102">IMetaDataImport2::GetPEKind-Methode</span><span class="sxs-lookup"><span data-stu-id="6ddba-102">IMetaDataImport2::GetPEKind Method</span></span>
<span data-ttu-id="6ddba-103">Ruft einen Wert ab, der die Art des Codes in der Datei mit der portablen ausführbaren Datei (PE) identifiziert, in der Regel eine DLL-oder exe-Datei, die im aktuellen Metadatenbereich definiert ist.</span><span class="sxs-lookup"><span data-stu-id="6ddba-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ddba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ddba-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ddba-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6ddba-105">Parameters</span></span>  
 `pdwPEKind`  
 <span data-ttu-id="6ddba-106">vorgenommen Ein Zeiger auf einen Wert der [corpeer Kind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) -Enumeration, der die PE-Datei beschreibt.</span><span class="sxs-lookup"><span data-stu-id="6ddba-106">[out] A pointer to a value of the [CorPEKind](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="6ddba-107">vorgenommen Ein Zeiger auf einen Wert, der die Architektur des Computers identifiziert.</span><span class="sxs-lookup"><span data-stu-id="6ddba-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="6ddba-108">Mögliche Werte finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="6ddba-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ddba-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6ddba-109">Remarks</span></span>  
 <span data-ttu-id="6ddba-110">Der Wert, auf den der `pdwMachine`-Parameter verweist, kann einen der folgenden Werte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6ddba-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="6ddba-111">Wert</span><span class="sxs-lookup"><span data-stu-id="6ddba-111">Value</span></span>|<span data-ttu-id="6ddba-112">Computerarchitektur</span><span class="sxs-lookup"><span data-stu-id="6ddba-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="6ddba-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="6ddba-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="6ddba-114">0x014C</span><span class="sxs-lookup"><span data-stu-id="6ddba-114">0x014C</span></span>|<span data-ttu-id="6ddba-115">x86</span><span class="sxs-lookup"><span data-stu-id="6ddba-115">x86</span></span>|  
|<span data-ttu-id="6ddba-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="6ddba-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="6ddba-117">0x0200</span><span class="sxs-lookup"><span data-stu-id="6ddba-117">0x0200</span></span>|<span data-ttu-id="6ddba-118">Intel IPF</span><span class="sxs-lookup"><span data-stu-id="6ddba-118">Intel IPF</span></span>|  
|<span data-ttu-id="6ddba-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="6ddba-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="6ddba-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="6ddba-120">0x8664</span></span>|<span data-ttu-id="6ddba-121">x64</span><span class="sxs-lookup"><span data-stu-id="6ddba-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6ddba-122">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6ddba-122">Requirements</span></span>  
 <span data-ttu-id="6ddba-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ddba-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ddba-124">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6ddba-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6ddba-125">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="6ddba-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6ddba-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ddba-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ddba-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ddba-127">See also</span></span>

- [<span data-ttu-id="6ddba-128">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ddba-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="6ddba-129">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ddba-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6ddba-130">CorPEKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6ddba-130">CorPEKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)

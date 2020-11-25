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
ms.openlocfilehash: d335beecc12e0c1c895e42888ad7172f78062ff7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702536"
---
# <a name="imetadataimport2getpekind-method"></a><span data-ttu-id="45e4c-102">IMetaDataImport2::GetPEKind-Methode</span><span class="sxs-lookup"><span data-stu-id="45e4c-102">IMetaDataImport2::GetPEKind Method</span></span>

<span data-ttu-id="45e4c-103">Ruft einen Wert ab, der die Art des Codes in der Datei mit der portablen ausführbaren Datei (PE) identifiziert, in der Regel eine DLL-oder exe-Datei, die im aktuellen Metadatenbereich definiert ist.</span><span class="sxs-lookup"><span data-stu-id="45e4c-103">Gets a value identifying the nature of the code in the portable executable (PE) file, typically a DLL or EXE file, that is defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45e4c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45e4c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPEKind (  
   [out] DWORD *pdwPEKind,  
   [out] DWORD *pdwMachine  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45e4c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="45e4c-105">Parameters</span></span>  

 `pdwPEKind`  
 <span data-ttu-id="45e4c-106">vorgenommen Ein Zeiger auf einen Wert der [corpeer Kind](corpekind-enumeration.md) -Enumeration, der die PE-Datei beschreibt.</span><span class="sxs-lookup"><span data-stu-id="45e4c-106">[out] A pointer to a value of the [CorPEKind](corpekind-enumeration.md) enumeration that describes the PE file.</span></span>  
  
 `pdwMachine`  
 <span data-ttu-id="45e4c-107">vorgenommen Ein Zeiger auf einen Wert, der die Architektur des Computers identifiziert.</span><span class="sxs-lookup"><span data-stu-id="45e4c-107">[out] A pointer to a value that identifies the architecture of the machine.</span></span> <span data-ttu-id="45e4c-108">Mögliche Werte finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="45e4c-108">See the next section for possible values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45e4c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="45e4c-109">Remarks</span></span>  

 <span data-ttu-id="45e4c-110">Der Wert, auf den der-Parameter verweist, `pdwMachine` kann eines der folgenden sein.</span><span class="sxs-lookup"><span data-stu-id="45e4c-110">The value referenced by the `pdwMachine` parameter can be one of the following.</span></span>  
  
|<span data-ttu-id="45e4c-111">Wert</span><span class="sxs-lookup"><span data-stu-id="45e4c-111">Value</span></span>|<span data-ttu-id="45e4c-112">Computerarchitektur</span><span class="sxs-lookup"><span data-stu-id="45e4c-112">Machine architecture</span></span>|  
|-----------|--------------------------|  
|<span data-ttu-id="45e4c-113">IMAGE_FILE_MACHINE_I386</span><span class="sxs-lookup"><span data-stu-id="45e4c-113">IMAGE_FILE_MACHINE_I386</span></span><br /><br /> <span data-ttu-id="45e4c-114">0x014c</span><span class="sxs-lookup"><span data-stu-id="45e4c-114">0x014C</span></span>|<span data-ttu-id="45e4c-115">x86</span><span class="sxs-lookup"><span data-stu-id="45e4c-115">x86</span></span>|  
|<span data-ttu-id="45e4c-116">IMAGE_FILE_MACHINE_IA64</span><span class="sxs-lookup"><span data-stu-id="45e4c-116">IMAGE_FILE_MACHINE_IA64</span></span><br /><br /> <span data-ttu-id="45e4c-117">0x0200</span><span class="sxs-lookup"><span data-stu-id="45e4c-117">0x0200</span></span>|<span data-ttu-id="45e4c-118">Intel IPF</span><span class="sxs-lookup"><span data-stu-id="45e4c-118">Intel IPF</span></span>|  
|<span data-ttu-id="45e4c-119">IMAGE_FILE_MACHINE_AMD64</span><span class="sxs-lookup"><span data-stu-id="45e4c-119">IMAGE_FILE_MACHINE_AMD64</span></span><br /><br /> <span data-ttu-id="45e4c-120">0x8664</span><span class="sxs-lookup"><span data-stu-id="45e4c-120">0x8664</span></span>|<span data-ttu-id="45e4c-121">x64</span><span class="sxs-lookup"><span data-stu-id="45e4c-121">x64</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="45e4c-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="45e4c-122">Requirements</span></span>  

 <span data-ttu-id="45e4c-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45e4c-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45e4c-124">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="45e4c-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="45e4c-125">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="45e4c-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="45e4c-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45e4c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45e4c-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45e4c-127">See also</span></span>

- [<span data-ttu-id="45e4c-128">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45e4c-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="45e4c-129">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45e4c-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="45e4c-130">CorPEKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="45e4c-130">CorPEKind Enumeration</span></span>](corpekind-enumeration.md)

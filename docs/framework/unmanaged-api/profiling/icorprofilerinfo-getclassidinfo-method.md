---
title: ICorProfilerInfo::GetClassIDInfo-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassIDInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassIDInfo
helpviewer_keywords:
- GetClassIDInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetClassIDInfo method [.NET Framework profiling]
ms.assetid: 9e93b99e-5aca-415c-8e37-7f33753b612d
topic_type:
- apiref
ms.openlocfilehash: 7d19a43048da742e702636faaa46ecf1458556f5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722587"
---
# <a name="icorprofilerinfogetclassidinfo-method"></a><span data-ttu-id="a3720-102">ICorProfilerInfo::GetClassIDInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="a3720-102">ICorProfilerInfo::GetClassIDInfo Method</span></span>

<span data-ttu-id="a3720-103">Ruft das übergeordnete Modul und das Metadatentoken für die angegebene Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="a3720-103">Gets the parent module and the metadata token for the specified class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3720-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3720-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassIDInfo(  
    [in]  ClassID   classId,  
    [out] ModuleID  *pModuleId,  
    [out] mdTypeDef *pTypeDefToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3720-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a3720-105">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="a3720-106">in Die ID der Klasse, für die die Informationen zu erhalten sind.</span><span class="sxs-lookup"><span data-stu-id="a3720-106">[in] The ID of the class for which to get the information.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="a3720-107">vorgenommen Ein Zeiger auf die ID des übergeordneten Moduls der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="a3720-107">[out] A pointer to the ID of the parent module of the class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="a3720-108">vorgenommen Ein Zeiger auf das Metadatentoken für die-Klasse.</span><span class="sxs-lookup"><span data-stu-id="a3720-108">[out] A pointer to the metadata token for the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3720-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a3720-109">Remarks</span></span>  

 <span data-ttu-id="a3720-110">Der Profiler-Code kann [ICorProfilerInfo:: GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) aufrufen, um eine Metadatenschnittstelle für ein bestimmtes Modul zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a3720-110">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="a3720-111">Das Metadatentoken, das an den Speicherort zurückgegeben wird, auf den durch `pTypeDefToken` verwiesen wird, kann anschließend für den Zugriff auf die Metadaten für die Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a3720-111">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="a3720-112">Verwenden Sie [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md), um weitere Informationen zu generischen Typen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a3720-112">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3720-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a3720-113">Requirements</span></span>  

 <span data-ttu-id="a3720-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3720-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3720-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a3720-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a3720-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3720-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3720-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3720-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3720-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a3720-118">See also</span></span>

- [<span data-ttu-id="a3720-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a3720-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)

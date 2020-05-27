---
title: IMetaDataEmit::SetParamProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
ms.openlocfilehash: b710f966f519e2702607b7e186fff5986110d391
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007818"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="cb81f-102">IMetaDataEmit::SetParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="cb81f-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="cb81f-103">Legt die Features eines Methoden Parameters fest, der durch einen vorherigen [IMetaDataEmit::D efineparam](imetadataemit-defineparam-method.md)definiert wurde, oder ändert Sie.</span><span class="sxs-lookup"><span data-stu-id="cb81f-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb81f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb81f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParamProps (
    [in]  mdParamDef  pd,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb81f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cb81f-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="cb81f-106">in Das Token für den Zielparameter.</span><span class="sxs-lookup"><span data-stu-id="cb81f-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="cb81f-107">in Der Name des Parameters in Unicode.</span><span class="sxs-lookup"><span data-stu-id="cb81f-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="cb81f-108">in Die Flags für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="cb81f-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="cb81f-109">in Der ELEMENT_TYPE_ \* für den konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="cb81f-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="cb81f-110">in Der Konstante Wert für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="cb81f-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="cb81f-111">in Die Größe in (Unicode) Zeichen von `pValue` .</span><span class="sxs-lookup"><span data-stu-id="cb81f-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb81f-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cb81f-112">Requirements</span></span>  
 <span data-ttu-id="cb81f-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb81f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb81f-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cb81f-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cb81f-115">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="cb81f-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb81f-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb81f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb81f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb81f-117">See also</span></span>

- [<span data-ttu-id="cb81f-118">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cb81f-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="cb81f-119">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cb81f-119">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

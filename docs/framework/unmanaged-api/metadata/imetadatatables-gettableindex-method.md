---
title: IMetaDataTables::GetTableIndex-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableIndex
helpviewer_keywords:
- GetTableIndex method [.NET Framework metadata]
- IMetaDataTables::GetTableIndex method [.NET Framework metadata]
ms.assetid: c6ec3800-e0d9-4387-afb8-ddc0b818114c
topic_type:
- apiref
ms.openlocfilehash: 48c38288e960ff2e1fe21f30b6eceae8eeaac2da
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434857"
---
# <a name="imetadatatablesgettableindex-method"></a><span data-ttu-id="9cbcb-102">IMetaDataTables::GetTableIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="9cbcb-102">IMetaDataTables::GetTableIndex Method</span></span>
<span data-ttu-id="9cbcb-103">Ruft den Index für die Tabelle ab, auf die durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-103">Gets the index for the table referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cbcb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9cbcb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cbcb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9cbcb-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="9cbcb-106">in Das Token, das auf die Tabelle verweist.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-106">[in] The token that references the table.</span></span>  
  
 `pixTbl`  
 <span data-ttu-id="9cbcb-107">vorgenommen Ein Zeiger auf den zurückgegebenen Index für die Tabelle, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-107">[out] A pointer to the returned index for the referenced table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cbcb-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9cbcb-108">Remarks</span></span>  
 <span data-ttu-id="9cbcb-109">Die Verwendung dieser Methode wird nicht empfohlen, da Sie keine konsistenten Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="9cbcb-110">Weitere Informationen zur GUID-Tabelle finden Sie in der Common Language Infrastructure (CLI)-Dokumentation, insbesondere "Partition II: Metadatendefinition und Semantik".</span><span class="sxs-lookup"><span data-stu-id="9cbcb-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="9cbcb-111">Die Dokumentation ist online verfügbar. Sie finden sie unter [ECMA C# and Common Language Infrastructure Standards (Standards von ECMA C# und Common Language Infrastructure)](https://go.microsoft.com/fwlink/?LinkID=99212) auf MSDN und [Standard ECMA-335 - Common Language Infrastructure (CLI) (Standard ECMA-335 – Common Language Infrastructure (CLI))](https://go.microsoft.com/fwlink/?LinkID=65552) auf der Ecma International-Website.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cbcb-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9cbcb-112">Requirements</span></span>  
 <span data-ttu-id="9cbcb-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cbcb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cbcb-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9cbcb-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9cbcb-115">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="9cbcb-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9cbcb-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cbcb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cbcb-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9cbcb-117">See also</span></span>

- [<span data-ttu-id="9cbcb-118">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9cbcb-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="9cbcb-119">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9cbcb-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)

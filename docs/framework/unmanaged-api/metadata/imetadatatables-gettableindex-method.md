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
ms.openlocfilehash: d3e056bc93c2faf2b1509536b8d8d4df6886dd20
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937382"
---
# <a name="imetadatatablesgettableindex-method"></a><span data-ttu-id="586b4-102">IMetaDataTables::GetTableIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="586b4-102">IMetaDataTables::GetTableIndex Method</span></span>
<span data-ttu-id="586b4-103">Ruft den Index für die Tabelle ab, auf die durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="586b4-103">Gets the index for the table referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="586b4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="586b4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="586b4-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="586b4-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="586b4-106">in Das Token, das auf die Tabelle verweist.</span><span class="sxs-lookup"><span data-stu-id="586b4-106">[in] The token that references the table.</span></span>  
  
 `pixTbl`  
 <span data-ttu-id="586b4-107">vorgenommen Ein Zeiger auf den zurückgegebenen Index für die Tabelle, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="586b4-107">[out] A pointer to the returned index for the referenced table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="586b4-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="586b4-108">Remarks</span></span>  
 <span data-ttu-id="586b4-109">Die Verwendung dieser Methode wird nicht empfohlen, da Sie keine konsistenten Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="586b4-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="586b4-110">Weitere Informationen zur GUID-Tabelle finden Sie in der Common Language Infrastructure (CLI)-Dokumentation, insbesondere "Partition II: Metadatendefinition und Semantik".</span><span class="sxs-lookup"><span data-stu-id="586b4-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="586b4-111">Die Dokumentation ist online verfügbar. Weitere Informationen finden Sie unter [ECMA C# und Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) und [Standard-ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="586b4-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="586b4-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="586b4-112">Requirements</span></span>  
 <span data-ttu-id="586b4-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="586b4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="586b4-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="586b4-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="586b4-115">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="586b4-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="586b4-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="586b4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="586b4-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="586b4-117">See also</span></span>

- [<span data-ttu-id="586b4-118">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="586b4-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="586b4-119">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="586b4-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)

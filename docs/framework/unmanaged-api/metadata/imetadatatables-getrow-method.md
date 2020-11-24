---
title: IMetaDataTables::GetRow-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetRow
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type:
- apiref
ms.openlocfilehash: 01c4c1734aa0701f787a2b73787e9e4781901d42
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672642"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="e6f2b-102">IMetaDataTables::GetRow-Methode</span><span class="sxs-lookup"><span data-stu-id="e6f2b-102">IMetaDataTables::GetRow Method</span></span>

<span data-ttu-id="e6f2b-103">Ruft die Zeile am angegebenen Zeilen Index in der Tabelle am angegebenen Tabellenindex ab.</span><span class="sxs-lookup"><span data-stu-id="e6f2b-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6f2b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6f2b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6f2b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e6f2b-105">Parameters</span></span>  

 `ixTbl`  
 <span data-ttu-id="e6f2b-106">in Der Index der Tabelle, aus der die Zeile abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e6f2b-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="e6f2b-107">in Der Index der abzurufenden Zeile.</span><span class="sxs-lookup"><span data-stu-id="e6f2b-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="e6f2b-108">vorgenommen Ein Zeiger auf einen Zeiger auf die Zeile.</span><span class="sxs-lookup"><span data-stu-id="e6f2b-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6f2b-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e6f2b-109">Remarks</span></span>  

  <span data-ttu-id="e6f2b-110">Die Verwendung dieser Methode wird nicht empfohlen, da Sie keine konsistenten Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e6f2b-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="e6f2b-111">Weitere Informationen zur GUID-Tabelle finden Sie in der Common Language Infrastructure (CLI)-Dokumentation, insbesondere "Partition II: Metadatendefinition und Semantik".</span><span class="sxs-lookup"><span data-stu-id="e6f2b-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="e6f2b-112">Die Dokumentation ist online verfügbar. Weitere Informationen finden Sie unter [ECMA c# und Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) und [Standard-ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="e6f2b-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6f2b-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e6f2b-113">Requirements</span></span>  

 <span data-ttu-id="e6f2b-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6f2b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6f2b-115">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e6f2b-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e6f2b-116">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="e6f2b-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e6f2b-117">**.NET Framework Versionen**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6f2b-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6f2b-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e6f2b-118">See also</span></span>

- [<span data-ttu-id="e6f2b-119">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e6f2b-119">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="e6f2b-120">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e6f2b-120">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)

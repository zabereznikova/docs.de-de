---
title: IMetaDataTables::GetNextUserString-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextUserString
helpviewer_keywords:
- GetNextUserString method [.NET Framework metadata]
- IMetaDataTables::GetNextUserString method [.NET Framework metadata]
ms.assetid: b7cb40ee-67b7-4f4e-8dcc-ee7ac8bc986b
topic_type:
- apiref
ms.openlocfilehash: bb53d980a7b2121854748d5117bc539fed125163
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680364"
---
# <a name="imetadatatablesgetnextuserstring-method"></a><span data-ttu-id="d8bf1-102">IMetaDataTables::GetNextUserString-Methode</span><span class="sxs-lookup"><span data-stu-id="d8bf1-102">IMetaDataTables::GetNextUserString Method</span></span>

<span data-ttu-id="d8bf1-103">Ruft den Index der Zeile ab, die die nächste hart codierte Zeichenfolge in der aktuellen Tabellenspalte enthält.</span><span class="sxs-lookup"><span data-stu-id="d8bf1-103">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8bf1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8bf1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8bf1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d8bf1-105">Parameters</span></span>  

 `ixUserString`  
 <span data-ttu-id="d8bf1-106">in Ein Indexwert aus der aktuellen Zeichen folgen Spalte.</span><span class="sxs-lookup"><span data-stu-id="d8bf1-106">[in] An index value from the current string column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="d8bf1-107">vorgenommen Ein Zeiger auf den Zeilen Index der nächsten Zeichenfolge in der Spalte.</span><span class="sxs-lookup"><span data-stu-id="d8bf1-107">[out] A pointer to the row index of the next string in the column.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8bf1-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d8bf1-108">Remarks</span></span>  

 <span data-ttu-id="d8bf1-109">Die Verwendung dieser Methode wird nicht empfohlen, da Sie keine konsistenten Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d8bf1-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="d8bf1-110">Weitere Informationen zur GUID-Tabelle finden Sie in der Common Language Infrastructure (CLI)-Dokumentation, insbesondere "Partition II: Metadatendefinition und Semantik".</span><span class="sxs-lookup"><span data-stu-id="d8bf1-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="d8bf1-111">Die Dokumentation ist online verfügbar. Weitere Informationen finden Sie unter [ECMA c# und Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) und [Standard-ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="d8bf1-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8bf1-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d8bf1-112">Requirements</span></span>  

 <span data-ttu-id="d8bf1-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8bf1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8bf1-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d8bf1-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d8bf1-115">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="d8bf1-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d8bf1-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8bf1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8bf1-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d8bf1-117">See also</span></span>

- [<span data-ttu-id="d8bf1-118">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8bf1-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="d8bf1-119">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8bf1-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)

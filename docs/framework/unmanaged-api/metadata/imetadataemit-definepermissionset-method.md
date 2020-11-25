---
title: IMetaDataEmit::DefinePermissionSet-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePermissionSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type:
- apiref
ms.openlocfilehash: 3698525c139ed52b59ca577c598e675b6c26eef4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719514"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="4b036-102">IMetaDataEmit::DefinePermissionSet-Methode</span><span class="sxs-lookup"><span data-stu-id="4b036-102">IMetaDataEmit::DefinePermissionSet Method</span></span>

<span data-ttu-id="4b036-103">Erstellt eine Definition für einen Berechtigungs Satz mit der angegebenen Metadatensignatur und ruft ein Token für diese Berechtigungs Satz Definition ab.</span><span class="sxs-lookup"><span data-stu-id="4b036-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b036-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b036-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,
    [in]  DWORD          dwAction,
    [in]  void const     *pvPermission,
    [in]  ULONG          cbPermission,
    [out] mdPermission   *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b036-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4b036-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="4b036-106">in Das zu ergänzte-Objekt.</span><span class="sxs-lookup"><span data-stu-id="4b036-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="4b036-107">in Ein [CorDeclSecurity](cordeclsecurity-enumeration.md) -Wert, der den Typ der zu verwendenden deklarativen Sicherheit angibt.</span><span class="sxs-lookup"><span data-stu-id="4b036-107">[in] A [CorDeclSecurity](cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="4b036-108">in Das Berechtigungs-BLOB.</span><span class="sxs-lookup"><span data-stu-id="4b036-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="4b036-109">in Die Größe von in Bytes `pvPermission` .</span><span class="sxs-lookup"><span data-stu-id="4b036-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="4b036-110">vorgenommen Das zurückgegebene Berechtigungs Token.</span><span class="sxs-lookup"><span data-stu-id="4b036-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b036-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4b036-111">Requirements</span></span>  

 <span data-ttu-id="4b036-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b036-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b036-113">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4b036-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4b036-114">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="4b036-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4b036-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b036-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b036-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4b036-116">See also</span></span>

- [<span data-ttu-id="4b036-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4b036-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="4b036-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4b036-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

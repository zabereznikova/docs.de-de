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
ms.openlocfilehash: a069e2f4ec5d4114e9504fa5a58c5066fdfd7249
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008039"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="22999-102">IMetaDataEmit::DefinePermissionSet-Methode</span><span class="sxs-lookup"><span data-stu-id="22999-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="22999-103">Erstellt eine Definition für einen Berechtigungs Satz mit der angegebenen Metadatensignatur und ruft ein Token für diese Berechtigungs Satz Definition ab.</span><span class="sxs-lookup"><span data-stu-id="22999-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22999-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="22999-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,
    [in]  DWORD          dwAction,
    [in]  void const     *pvPermission,
    [in]  ULONG          cbPermission,
    [out] mdPermission   *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22999-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="22999-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="22999-106">in Das zu ergänzte-Objekt.</span><span class="sxs-lookup"><span data-stu-id="22999-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="22999-107">in Ein [CorDeclSecurity](cordeclsecurity-enumeration.md) -Wert, der den Typ der zu verwendenden deklarativen Sicherheit angibt.</span><span class="sxs-lookup"><span data-stu-id="22999-107">[in] A [CorDeclSecurity](cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="22999-108">in Das Berechtigungs-BLOB.</span><span class="sxs-lookup"><span data-stu-id="22999-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="22999-109">in Die Größe von in Bytes `pvPermission` .</span><span class="sxs-lookup"><span data-stu-id="22999-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="22999-110">vorgenommen Das zurückgegebene Berechtigungs Token.</span><span class="sxs-lookup"><span data-stu-id="22999-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22999-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="22999-111">Requirements</span></span>  
 <span data-ttu-id="22999-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22999-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22999-113">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="22999-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="22999-114">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="22999-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22999-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22999-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22999-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22999-116">See also</span></span>

- [<span data-ttu-id="22999-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22999-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="22999-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22999-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

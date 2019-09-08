---
title: IAssemblyName::GetName-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e471ee99af57ef980850c0a5d3e4f5f2973967ac
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796606"
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="330e3-102">IAssemblyName::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="330e3-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="330e3-103">Ruft den einfachen, unverschlüsselten Namen der Assembly ab, auf die von diesem [IAssemblyName](iassemblyname-interface.md) -Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="330e3-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="330e3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="330e3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="330e3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="330e3-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="330e3-106">[in, out] Die Größe von `pwzName` in breit Zeichen, einschließlich des NULL-Abschluss Zeichens.</span><span class="sxs-lookup"><span data-stu-id="330e3-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="330e3-107">vorgenommen Ein Puffer, der den Namen der Assembly enthalten soll, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="330e3-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="330e3-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="330e3-108">Requirements</span></span>  
 <span data-ttu-id="330e3-109">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="330e3-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="330e3-110">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="330e3-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="330e3-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="330e3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="330e3-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="330e3-112">See also</span></span>

- [<span data-ttu-id="330e3-113">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="330e3-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)

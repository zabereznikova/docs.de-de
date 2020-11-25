---
title: ICorDebugDataTarget2::GetSymbolProviderForImage-Methode
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: 5a5ccaeb36dcda82c0189026e19c6a7c023f3e1c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713768"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="7072e-102">ICorDebugDataTarget2::GetSymbolProviderForImage-Methode</span><span class="sxs-lookup"><span data-stu-id="7072e-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>

<span data-ttu-id="7072e-103">Gibt anhand der Basisadresse des Moduls den Symbol-Anbieter für ein Modul aus.</span><span class="sxs-lookup"><span data-stu-id="7072e-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7072e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7072e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7072e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7072e-105">Parameters</span></span>  

 `imageBaseAddress`  
 <span data-ttu-id="7072e-106">in Ein [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) Wert, der die Basisadresse eines Moduls darstellt.</span><span class="sxs-lookup"><span data-stu-id="7072e-106">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="7072e-107">vorgenommen Ein Zeiger auf die Adresse eines [icorentbugsymbolprovider](icordebugsymbolprovider-interface.md) -Objekts.</span><span class="sxs-lookup"><span data-stu-id="7072e-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7072e-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7072e-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7072e-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7072e-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7072e-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7072e-110">Requirements</span></span>  

 <span data-ttu-id="7072e-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7072e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7072e-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7072e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7072e-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7072e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7072e-114">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7072e-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7072e-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7072e-115">See also</span></span>

- [<span data-ttu-id="7072e-116">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7072e-116">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="7072e-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7072e-117">Debugging Interfaces</span></span>](debugging-interfaces.md)

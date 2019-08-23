---
title: CorDebugRecordFormat-Aufzählung
ms.date: 03/30/2017
api_name:
- CorDebugRecordFormat
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6ed7d25593f9dd5d5d01f8c06024dcf8acfcfea
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916478"
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="8d680-102">CorDebugRecordFormat-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="8d680-102">CorDebugRecordFormat Enumeration</span></span>
<span data-ttu-id="8d680-103">Beschreibt das Format der Daten in einem Byte-Array, das Informationen über ein systemeigenes Ausnahme-Debug-Ereignis enthält.</span><span class="sxs-lookup"><span data-stu-id="8d680-103">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d680-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8d680-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="8d680-105">Member</span><span class="sxs-lookup"><span data-stu-id="8d680-105">Members</span></span>  
  
|<span data-ttu-id="8d680-106">Member</span><span class="sxs-lookup"><span data-stu-id="8d680-106">Member</span></span>|<span data-ttu-id="8d680-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8d680-107">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="8d680-108">Die Daten stellen einen 32-Bit-Windows-Ausnahmedatensatz dar.</span><span class="sxs-lookup"><span data-stu-id="8d680-108">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="8d680-109">Die Daten stellen einen 64-Bit-Windows-Ausnahmedatensatz dar.</span><span class="sxs-lookup"><span data-stu-id="8d680-109">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d680-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8d680-110">Remarks</span></span>  
 <span data-ttu-id="8d680-111">Ein Member der `CorDebugRecordFormat` -Enumeration wird an die [decodeevent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) -Methode übermittelt, um das Format des Bytearrays `pRecord` in seinem Argument anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8d680-111">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d680-112">Diese Enumeration ist nur für die Verwendung in .NET Native-Debugszenarien vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="8d680-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d680-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8d680-113">Requirements</span></span>  
 <span data-ttu-id="8d680-114">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d680-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d680-115">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="8d680-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d680-116">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d680-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d680-117">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d680-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d680-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d680-118">See also</span></span>

- [<span data-ttu-id="8d680-119">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="8d680-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

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
ms.openlocfilehash: add1458bb3a50a5e5433e8cc7baaf47d750c927d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645707"
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="2d75c-102">CorDebugRecordFormat-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="2d75c-102">CorDebugRecordFormat Enumeration</span></span>
<span data-ttu-id="2d75c-103">Beschreibt das Format der Daten in einem Byte-Array, das Informationen über ein systemeigenes Ausnahme-Debug-Ereignis enthält.</span><span class="sxs-lookup"><span data-stu-id="2d75c-103">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d75c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d75c-104">Syntax</span></span>  
  
```  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="2d75c-105">Member</span><span class="sxs-lookup"><span data-stu-id="2d75c-105">Members</span></span>  
  
|<span data-ttu-id="2d75c-106">Member</span><span class="sxs-lookup"><span data-stu-id="2d75c-106">Member</span></span>|<span data-ttu-id="2d75c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d75c-107">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="2d75c-108">Die Daten stellen einen 32-Bit-Windows-Ausnahmedatensatz dar.</span><span class="sxs-lookup"><span data-stu-id="2d75c-108">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="2d75c-109">Die Daten stellen einen 64-Bit-Windows-Ausnahmedatensatz dar.</span><span class="sxs-lookup"><span data-stu-id="2d75c-109">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d75c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2d75c-110">Remarks</span></span>  
 <span data-ttu-id="2d75c-111">Ein Mitglied der `CorDebugRecordFormat` Enumeration wird zum Übergeben der [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) Methode an, dass das Format des Bytearrays in die `pRecord` Argument.</span><span class="sxs-lookup"><span data-stu-id="2d75c-111">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d75c-112">Diese Enumeration ist nur für die Verwendung in .NET Native-Debugszenarien vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="2d75c-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d75c-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2d75c-113">Requirements</span></span>  
 <span data-ttu-id="2d75c-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d75c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d75c-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d75c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d75c-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d75c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d75c-117">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d75c-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d75c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d75c-118">See also</span></span>

- [<span data-ttu-id="2d75c-119">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="2d75c-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
